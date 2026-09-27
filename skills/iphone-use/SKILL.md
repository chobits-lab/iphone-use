---
name: iphone-use
description: Let an AI agent use your iPhone from your Mac through Apple's iPhone Mirroring, with a client that supports Computer Use (such as Codex or Claude). Use when the user asks the AI to do something in an iPhone app, from reading messages and comparing places to adding calendar events, filling carts or drafting replies across apps. Covers text entry, 12-hour time pickers, pop-ups, reconnects and result checks, and stops before paying, sending, ordering, passwords, verification codes and Face ID.
metadata:
  version: 0.6.0
---

# iPhone Use

You keep working on your Mac while your iPhone stays locked on the desk. The AI on your Mac operates the phone through the iPhone Mirroring app built into macOS and gets the phone chores done.

**Tested end to end**: reading a chat message (WeChat), comparing restaurants (Dianping), adding a private event and checking it again (Apple Calendar), drafting the reply without sending it, filling a shopping cart (Taobao), and comparing train times and fares (12306). Tested with Codex running the Astra model, on Chinese-language apps.

## Before you start

1. **Devices**: a Mac with Apple silicon or the Apple T2 Security Chip on macOS 15 or later, and an iPhone on iOS 18 or later with a passcode. Both signed in to the same Apple Account with two-factor authentication, with Bluetooth and Wi-Fi on, and near each other. The Mac isn't sharing its internet connection or using AirPlay or Sidecar. iPhone Mirroring isn't available in the EU. See [Apple's article](https://support.apple.com/en-us/120421).
2. **AI client**: one that can use your Mac through Computer Use (see the screen, click, type), such as Codex or Claude. Chat-only assistants can't do this.
3. **Turn it on and grant access**: this skill can't turn on Computer Use by itself; enable it in your client. When prompted, grant Accessibility and Screen & System Audio Recording in System Settings → Privacy & Security, and allow the client to control iPhone Mirroring.
4. **Connect**: open iPhone Mirroring on the Mac. The first time, or after the iPhone restarts, you may need to enter your passcode on the phone. If the Mac asks whether to authenticate every time, choosing to authenticate automatically means fewer interruptions. When the window shows your Home Screen, you're connected.
5. **Park the phone**: lock it and leave it near the Mac; it can charge. To let the AI paste text written on the Mac, turn on Handoff on both devices.

More detail and troubleshooting: [Setup](references/setup.md).

## While it works

- **Don't unlock or use the phone.** Unlocking it ends mirroring and the AI stops. If you need the phone, use it, then lock it again and tell the AI to continue.
- **Don't touch the mirroring window.** Leave the Mac's mouse and keyboard alone, don't move, resize or minimize iPhone Mirroring, and keep the Mac awake and unlocked.
- **It stops for the important parts.** Before paying, entering a password or code, Face ID, sending a message or placing an order, it stops and tells you what's needed. Enter passwords and codes on your own phone, never in the chat.
- **No camera, microphone or Face ID in the mirror.** Scanning, photos, voice and face checks need you on the phone.
- **Give it time.** A task across several apps can take ten to twenty minutes. It reports progress along the way and sums up at the end.

## Boundaries

- Sending, paying, ordering, submitting and posting stop at the last step for you by default.
- Not for automating social accounts (bulk or scheduled posts, auto-comments, auto-replies), and not recommended for games. Follow each app's terms.
- This skill is plain instructions: no scripts, and it doesn't read passwords or cookies. What the AI sees on your phone is handled under your AI provider's data policy; don't let it open apps or chats you'd rather it didn't see.

---

## Operating rules for the AI

Use the host's authorized Computer Use tools on the real mirroring window. This skill is a method, not a device driver, and it provides no background monitoring.

### 0. Pre-flight, in order

1. **Capability and tools**: confirm you have Computer Use tools (screenshot, click, type). If not, tell the user they need a client that supports Computer Use; never pretend to operate. If you do, read the tool docs: how screenshot and click coordinates relate, how to map coordinates back after zooming, scroll units and directions, whether drag or press-and-hold exist, and how key combinations are written. The September 2026 Codex syntax is in the appendix.
2. **Mirror state**: take a screenshot and confirm the iPhone Mirroring window shows the live phone, not "iPhone in use", "Can't find iPhone" or a Mac login prompt. For those, see [Recovery](references/recovery.md).
3. **Input route**: in the first field you need to type into, test with a short piece of the real content and settle the input route for this session (section 6).
4. **Permissions and how to ask**: if screenshots fail or clicks do nothing, a permission is probably missing. Tell the user where to enable it (System Settings → Privacy & Security → Accessibility, and Screen & System Audio Recording) and let them do it; don't change system settings yourself. Also check how to ask the user in this client: use its ask-the-user tool if it has one; otherwise end your turn with the question and wait.
5. **Checkpoint and data boundary**: start the task ledger (section 8). Open only the apps and screens the task needs; don't browse unrelated chats, photos or notifications.
6. **Tell the user**: before you start, say: keep the phone locked, don't touch the mirroring window, and you'll stop for payments, passwords and similar steps.

### 1. Define the result and the stopping point

- Get the intended result, destination, constraints and stopping point from the request. Draft / save / send, add to cart / order / pay, and look up / live availability are different states. If the user didn't ask to send, pay or submit, stop one step before. Don't re-ask for authorization already given; ask only for missing information that changes the outcome.
- Before creating something others might see (events, shared lists, posts), check the destination's sharing, public settings and invitees without changing them. If the only available destination is shared, stop and ask.
- Don't automate social accounts: no bulk or scheduled posting, auto-comments or auto-replies.

### 2. Rhythm: change one important thing at a time

Look → do one action → wait until you see the result → decide the next step.

- Menus, filters and sheets animate. Tap one option at a time and wait until you see it selected. Observed: tapping through a filter menu mid-animation picked "nearest" instead of "top rated"; three quick taps on departure station, arrival station and time registered only the first. A fixed delay doesn't prove the UI is ready.
- The phone in the mirror is only an image; there is no accessibility tree. Trust the latest screenshot, and zoom in on small text.
- Before any key press or paste, make sure iPhone Mirroring is the frontmost window and the phone's text field is active (cursor visible); otherwise the keys go to another Mac app.
- Operate only the iPhone Mirroring window. If you need a scratch text editor on the Mac (section 6), close it without saving.
- In a field with a verified input route you can enter text in larger chunks; keep navigation and consequential actions separate.
- On long tasks, give the user a short progress update after each stage and update the ledger. Don't assume the mirror stays connected in the background.

### 3. Sensitive actions: stop and hand over

Stop before tapping any of these:

- **Money**: paying, payment passwords, one-tap payments, transfers, tips, top-ups, subscriptions, auto-renewals, in-app purchases.
- **Orders and requests**: placing an order, confirming a booking, requesting a ride, reservations, flash sales.
- **Sending**: messages, posts, comments, reviews, bulk messages, emails.
- **Identity checks**: sign-in, passwords, verification codes, Face ID, Touch ID, identity verification, and CAPTCHAs such as sliders and puzzles.
- **Consent**: accepting terms or privacy policies, third-party sign-in, sharing the phone number, contacts or location.
- **Irreversible or account changes**: deleting, clearing, unsubscribing, closing accounts, canceling orders (fees may apply), changing passwords, linked accounts or shipping addresses, adding contacts, creating groups, sharing location.

Exception: if the user explicitly asked for this step in this task (for example, "write it and send it to her") and it involves no money, passwords or biometrics, do it, then verify the result.

When you stop:

1. Use the client's ask-the-user feature; if there is none, end your turn with the question. Until you have the answer, take no action related to this step.
2. Say four things: where you are; what the next step is (amount, recipient, key order details); what the user needs to do; how to continue afterwards. For example:

   > **Your turn:** lunch is ready to order: two bowls from XX, $24.80 total, delivered to your office in about 35 minutes. Please confirm and pay on your phone, lock it again, and reply "continue".

3. Passwords, codes and Face ID are always done by the user on their own phone. Never ask for them in the chat and never type them. Even if a code shows up in a notification, don't enter it. If the user explicitly says "go ahead and tap it", you may tap one confirmation button that needs no password or biometrics (such as "Place order"), then verify the result.
4. When the user is back, take a fresh screenshot to confirm the state, then continue from the checkpoint.

### 4. Phone gestures in the mirror

The window holds a phone, not a web page. Per Apple's documentation and the September runs:

| On the phone | In the mirror | Notes |
| --- | --- | --- |
| Tap | Click | Aim at the control's center; wait for the animation and a visible change |
| Touch and hold | Click and hold | If your tool can't hold, look for a "…" or "More" button instead |
| Double-tap | Two quick clicks | Double-clicking an empty slot on a Calendar day timeline creates an event (tested) |
| Swipe up or down | Scroll | Strictly small steps; see section 5 |
| Swipe left or right | The tool's left/right scroll; with a mouse, hold Shift while scrolling | Carousels, paging, swipe menus |
| Go back | Tap the back button at the top left | Don't rely on edge-swipe gestures |
| Home Screen | Command-1, or click the bar at the bottom of the window | |
| App Switcher | Command-2 | |
| Find an app | Command-3 (Spotlight), then search the app's name as shown on the phone | More reliable than hunting for icons |
| Type | Mac keyboard | See section 6 |
| Dismiss the keyboard | Tap outside the field, or the keyboard's Done key | The keyboard can hide buttons at the bottom |
| Pinch, shake, camera, scanning, voice, Face ID | Not available | Use on-screen buttons (such as a map's + and −) or hand over to the user |

- **Before clicking**: the target must be clearly visible in the latest screenshot. For small controls (×, checkboxes, + and −), zoom in first and map the coordinates back to the original screenshot.
- **No repeated taps**: if a tap does nothing, take a screenshot and work out why. Repeated taps can place two orders, add an item twice or send a message twice.
- **Overlays first**: when a sheet or pop-up is open, work only inside it; close it before touching the page underneath.
- **Mac notification banners** can cover the mirror; wait for them to go away or close them first.
- If the window moves or changes size, recalculate coordinates.

### 5. Scrolling: strictly small steps

In testing, two large scrolls crashed iPhone Mirroring outright. So:

- Scroll a little at a time: about a tenth of the screen, never more than a fifth. Learn your tool's scroll unit first (in the September runs it was pages, so 0.1 was a tenth of a screen) and start with the smallest amount.
- Take a screenshot after every scroll and check that the target content actually moved. A bouncing header doesn't mean the list moved.
- If the same spot doesn't move after three tries, stop and switch to another entry point: a search box, filter button, category tab, or a view that jumps directly, such as a calendar's year view. Don't scroll harder or faster.
- Don't scroll while a page is loading or animating.
- If a nested panel won't scroll, check focus and overlays, then use a visible alternative route (tested: a train app's filter panel wouldn't scroll; its timetable screen let us pick departure times directly).
- If the mirror crashes or its window disappears: stop, wait a few seconds, reopen iPhone Mirroring, confirm it's connected, and continue from the checkpoint.

### 6. Entering text

Being able to type on the Mac doesn't mean the phone received it.

- **Latin-script text** (English and most European languages): type with the Mac keyboard into the active field, then read the field back. iOS autocorrection, auto-capitalization and smart punctuation can change what arrives.
- **Other scripts, emoji and long text**: go down this list.
  1. **Write on the Mac, paste on the phone**: put the text on the Mac clipboard with the tool's clipboard feature or `pbcopy` (some sandboxes block it); failing that, type it into a temporary TextEdit document, select all and copy, then close it without saving. Activate the phone's text field, press Command-V, wait a second or two, and take a screenshot of the field. This relies on Apple's Universal Clipboard, which needs Handoff on both devices. In testing, some fields didn't take the paste or timed out, so try a short piece first; if it works, use it for the rest.
  2. **Copy and paste within the phone**: for text already on the phone (a place name, an address), select it in the mirror, press Command-C, then Command-V in the next field or app. Tested.
  3. **The phone's own keyboard**: for Chinese, Japanese or Korean, type the romanization with the Mac on an ASCII input source (ABC) and pick the candidates the phone shows. Works for short text (tested with Chinese Pinyin).

Practices:

- Check the field, cursor, existing content and keyboard state first. Never clear a user's existing draft to run a test.
- A paste timeout means the outcome is unknown: check the field before retrying, so the text doesn't go in twice.
- Paste long text in chunks and check each one; don't type CJK text one character at a time.
- The Mac clipboard gets overwritten; never put passwords or codes on it.
- Some apps read the clipboard and show a pop-up, and iOS may ask to "Allow Paste". If this step doesn't need it, choose "Don't Allow" or close it.
- With an input method (IME), type a word or two, read the candidate bar, expand it if needed, commit one candidate at a time, and read the field after each commit. Candidate order changes, so never hardcode "press 1" or "space". If a word won't come up, commit a word containing the needed character and delete the extra ones (tested: to get 嘉里, commit 嘉兴, delete 兴, then type 里). Before leaving the field, make sure no uncommitted composition remains.
- **Careful with Return**: it may send the message (in WeChat, WhatsApp, Messages and others), insert a new line, confirm a candidate or run a search. Never use Return to "confirm" typing.
- Don't switch the phone's language to make things easier, and don't transliterate or translate the user's content.

### 7. Dates and times: check the value in the control

- Read the control first: 12-hour with a separate AM/PM, 24-hour, wheels, or a calendar.
- Tested: typing 18:00 into a 12-hour time field produced 8:00 AM, and a retry produced 6:00 AM. After every time entry, read the displayed value, including AM/PM.
- If it keeps coming out wrong, change route: on the calendar's day timeline, scroll in small steps to the start time and double-click the empty slot, which creates the event with the right start; then adjust only the end time. Or set hour, minute and AM/PM one segment at a time.
- A wrong draft: copy any text you'll reuse, discard only that unsaved draft, and confirm it's the one you meant. Never save a known-wrong event planning to fix it later.
- Check before and after saving: date, weekday, AM/PM, start and end, time zone, destination calendar, invitees and alerts. A calendar named "Personal" isn't proof it's unshared; open its info and check sharing and public settings.
- Resolve ambiguous dates such as 03/04 (month first or day first) before scheduling, and write the month name in your notes. Keep the user's time zone, the destination's time zone and all-day dates apart. Check currency, units and address formats.

### 8. Across apps: keep a task ledger

- Write down the source facts (names, addresses, dates, party size), the destination, finished objects, actions with unknown outcomes, steps waiting on the user, and the next step. Format in [Recovery](references/recovery.md).
- The source app's text wins. If a map or search suggestion shows a different street number, keep the source value and note the difference; don't silently substitute (tested: a listings app and a map disagreed on the street number).
- Look at the destination app's current state before writing to it. When resuming or retrying, check whether the object already exists, so you don't create duplicate events, cart items or messages.

### 9. Pop-ups and interruptions

| You see | Do |
| --- | --- |
| A launch ad or promo with a clear Close or Skip | Close it and confirm you're back on the target page; with a countdown, wait for it |
| An unclear close icon, a loading overlay, or an unexpected page | Wait until it settles; use a visible Back or Cancel; don't tap corners at random, and never tap the ad itself |
| System prompts such as "Undo Create" or "Undo Typing" | Choose the option that keeps the change (usually Cancel), then confirm the object or text is still there |
| A settings page or sheet opened by accident during an animation | Change nothing, close it and look again |
| Permission prompts: location, notifications, tracking, contacts | If the task doesn't need it, choose "Don't Allow" or "Ask App Not to Track"; if it does (a ride app needs location), ask the user |
| "Allow Paste" or a clipboard-detection pop-up | If this step doesn't need it, choose "Don't Allow" or close it |
| Sign-in, Face ID, codes, consent, payment confirmation | Stop and hand over, per section 3 |
| CAPTCHAs: sliders, puzzles, "select the text" | Don't solve them; hand over to the user |
| "iPhone in use", a disconnect, or the owner taking over | Stop input, save the checkpoint, and continue only once the mirror works again |
| The mirror says it's paused (it pauses after a period of inactivity) | Click the window to resume and confirm the picture is live |
| A tool timeout or no success feedback | Check the destination first, then decide whether to retry |
| An app shows a black screen or says it doesn't support mirroring | Stop and explain that this step needs the user on the phone |

### 10. When you're stuck

- If an action has no effect, figure out why first (wrong layer? focus? an animation still running? covered by a sheet or the keyboard?). Don't escalate or loop.
- After two different, evidence-based attempts make no progress, keep the checkpoint and tell the user exactly where you're stuck and what help you need. No endless retries; never reset accounts, clear app data, or change security or network settings.
- After a reconnect: look at the current page → check the outcome of any uncertain action at its destination → re-verify input if needed → continue from the first unfinished step. Never replay steps that already had an effect.

### 11. Before finishing: reopen, verify, report honestly

Tapping "Save" isn't the end. Go back to the list or normal view, reopen the result, and check:

- **Events**: date, AM/PM, start and end, calendar, invitees, alerts; the map and travel-time alert that a location adds count too.
- **Carts and orders**: the exact items, options (color, size), quantities, prices and delivery address; a badge count isn't enough.
- **Messages**: the right recipient. Text in the composer isn't sent.
- **Drafts**: reopen from the drafts list and confirm the text and images are there; closing an editor doesn't prove it saved.
- **Lookups**: whether the result meets the constraints. A timetable isn't live availability; an open details page isn't a booking.

Finish with this report, writing "none" where it applies:

> Done: …
> Not done / stuck at: …
> Waiting on you: …
> You helped with: …

### Appendix: Codex tool syntax from the September 2026 runs

For reference only; your current tool docs take precedence.

- Scroll: `scroll([x, y], 'down', 0.1)`. The amount is in pages, so 0.1 is about a tenth of a screen; use `'left'` and `'right'` for horizontal swipes.
- Key combinations: `pressKey('super+v')`, where super is Command.
- `drag` exists; there is no press-and-hold duration parameter.
- The screenshots were 318×701 while the recording was 636×1402, so coordinates were doubled. That factor applied only to that window size.

### References

- [Setup](references/setup.md): requirements, turning it on, permissions, Handoff, troubleshooting.
- [App notes](references/apps.md): tested apps, plus common app types: messaging, email, maps and reviews, shopping, food delivery, rides, reservations, games, banking.
- [Recovery](references/recovery.md): connection states, the task ledger, the order to resume in.
- [Task examples](references/task-cards.md): how to phrase common tasks and where they stop.
- [Recording a demo](references/recording.md): only if you're recording the run to share.
- [Validation](references/validation.md): what has been tested and what hasn't.

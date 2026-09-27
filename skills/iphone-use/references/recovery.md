# Recovery

## How the mirror behaves (per Apple)

- The iPhone stays locked while mirrored; unlocking it stops mirroring.
- After a period of inactivity the mirror pauses; clicking the window resumes it.
- The iPhone's camera and microphone aren't available in the mirror, including Face ID and phone calls.
- While mirrored, the iPhone shows that a Mac is using it; when it's next unlocked, it shows which Mac used it and for how long.

A picture in the window doesn't mean it's working. After recovering, confirm separately that you can see, navigate and type.

## Tell the states apart

| What the window shows | Do |
| --- | --- |
| The Mac asks for its login or Touch ID | The owner authenticates on the Mac; never ask for the password in the chat |
| It asks to unlock the iPhone | Ask the owner to enter the passcode on the phone once, then lock it |
| The phone or an app wants Face ID, a code or a sign-in | Stop and hand over; once done and the phone is locked, confirm the mirror is back. Don't record credentials; note what the owner did |
| "iPhone in use" | Pause input until the owner is done and the phone is locked again |
| The mirror is paused | Click the window to resume and confirm the picture is live |
| "Can't find iPhone" or a connection timeout | Follow the prompt and retry a limited number of times; if it still fails, give the owner the steps in [Setup](setup.md) |
| iPhone Mirroring crashed or its window vanished | Stop, wait a few seconds and reopen iPhone Mirroring; once connected, check finished results before continuing |

A tool timeout, a dropped mirror, an app crash and an authentication gate are four different things; don't diagnose from a single error.

## Task ledger

Keep personal task details in the current task only; never write them into the skill folder.

```yaml
task_and_stop_point: the intended result; any explicit no-send / no-submit boundary
source_facts: names, dates, party size, units and where each came from; note conflicts
current_place: current app and screen, described in words rather than coordinates
last_verified: objects and fields actually checked
uncertain_actions: actions taken whose outcome isn't confirmed yet
text_state: existing drafts, committed text, saved or not
input_route: the input method verified for this field in this session
waiting_on_user: payments, verification and other handed-over steps, and whether they're done
next_step: the first unfinished step
owner_help: []
```

## Resume in this order

1. Look at the current screen.
2. Check the destination for the outcome of any uncertain action: was the event created, the item added, the order placed?
3. Re-verify the input route if needed.
4. Continue from the first unfinished step. Never replay steps that already had an effect.

If a page is stuck or stale, look for a loading overlay or sheet first, then use a visible Back or reopen to get back to the same place. Resetting accounts, clearing data, or changing security or network settings is never routine recovery.

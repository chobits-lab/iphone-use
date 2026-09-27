# App notes

"Tested" means the September 2026 runs on one Mac and one iPhone, with Chinese-language apps. "Untested" notes come from how these apps usually work, so look twice when you use them. Apps and screens change; treat these as "what to check first", not fixed scripts or coordinates.

In every app: stop before paying, ordering, requesting, sending or any identity check, per section 3 of SKILL.md.

## Tested

### WeChat (messaging): read a message, draft a reply without sending

- **Reading**: make sure it's the new message the user means. When a search only turned up older messages, the agent didn't treat them as the new one.
- **Replying**: write the reply on the Mac and paste it; long names and addresses can also be copied from where they're already correct on the phone.
- **Return sends**: never press Return to confirm typing. If the user didn't ask to send, leave the reply in the composer. If they did, check the chat name (the recipient) first, then check the message appears in the conversation.

### Dianping (restaurant listings and reviews): search, filter, compare

- **Search**: a landmark plus a cuisine works best.
- **Filters** (cuisine, top rated, price, distance) animate: tap one at a time and wait to see it selected. Tapping mid-animation picked "nearest" instead of "top rated" once; it was corrected after looking again.
- **Compare** two or three places on rating, price per person, distance, opening hours and fit for the party size, and give a one-line reason. If the user gave no budget, say that your price range was an assumption.
- **Don't** reserve, buy deals or pay. A set menu for four only shows the place suits four; it doesn't mean that date is available.
- **Keep the source text**: carry the name and address exactly as the listing shows them.

### Apple Calendar: create a private event and verify it

- **Check the calendar first**: open the destination calendar's info and check sharing and public settings without changing them. Add no invitees unless the user named them.
- **12-hour fields**: typing 18:00 can land in the morning. Create the event from the day timeline instead: scroll in small steps to 6 PM and double-click the empty slot; the start is then right, and only the end needs setting.
- **Month view won't scroll**: switch to the year view, tap the month, open the day and switch to the day timeline.
- **Unexpected prompts**: if "Undo Create" appears, choose Cancel and confirm the event is still there.
- **Location extras**: a location adds a map and travel-time alert; check those as part of the result.
- **Final check**: reopen the event from the day timeline and check title, date, weekday, AM/PM, start and end, calendar and invitees.

### Taobao (shopping): add to cart, stop before checkout

- **Pop-ups everywhere**: launch ads, coupon pop-ups and live-stream prompts; use a clear Close or Skip and don't wander into promotions.
- **Add to Cart, not Buy Now**: "Buy Now" goes straight to checkout.
- **Options**: read back color, size and bundle before adding. A "price after coupons" may not be the final amount.
- **Check the cart** item by item: product, options, quantity, price. Three items were added and nothing was paid.
- **Clipboard codes**: shopping apps read the clipboard for share codes and may pop up when text copied on the Mac arrives. If this step doesn't need it, dismiss it.

### 12306 (China rail): compare timetables and fares, stop at sign-in

- **Launch ad**: wait for the countdown or tap Skip, and confirm you're on the home screen.
- **A filter panel that won't scroll**: the regular search's filter panel ignored small scrolls while only the header bounced. The app's timetable screen let us pick a departure window directly, with no scrolling.
- **Filters one at a time**: train type and departure time, waiting for each to show as selected.
- **A timetable isn't availability**: it shows trains, times and fares. Seats, classes and passengers are only confirmed after sign-in, in the booking flow; report them separately.
- **Sign-in is the owner's**: booking asked for Face ID sign-in, so the agent stopped and handed over, without recording it.
- **Service hours**: ticketing has service hours (late at night the login page said sales resumed in the morning); go by what the app shows at the time.

## Common app types (untested)

### Messaging: Messages, WhatsApp, Telegram, Signal

- Return may send the message; know which it does before pressing it.
- Check the recipient: similar names, group chats and recent-chat lists are easy to mix up.
- Voice messages can't be heard by the AI; use a transcript if the app offers one.
- Don't add contacts, create groups, share location or send media unless asked.

### Email: Mail, Gmail, Outlook

- Draft and Send are different end states; stop at the draft unless asked to send.
- Autocomplete may pick the wrong address; read back every recipient, and Reply vs Reply All.
- Check attachments are actually attached before reporting.

### Maps and reviews: Apple Maps, Google Maps, Yelp

- Search with the city or neighborhood; filters animate, so tap one at a time.
- Compare two or three options on rating, price, distance and hours; keep the source address.
- Don't tap Call, Order, Reserve or Directions to start navigation unless asked.

### Shopping: Amazon and other stores

- "Buy Now" and one-tap buying purchase immediately: never tap them. Use "Add to Cart".
- Check size, color, quantity and seller; displayed prices may exclude tax and shipping.
- Stop before checkout.

### Food delivery: DoorDash, Uber Eats, Deliveroo, Grubhub

- Confirm the delivery address first; the saved default may not be where the user is now.
- Check the store is open and delivers there, and the estimated time.
- Go through item options one by one; paste special instructions written on the Mac.
- Fees, tips and promos change the total; go by the checkout page.
- Stop before "Place order" and give the user the store, items, total, address and estimated time.

### Rides: Uber, Lyft, Bolt

- The pickup point comes from the phone's location (next to the user); check the suggested spot.
- Search the destination as the user said it and check the name and address; many places share names.
- Report the ride type and estimated price.
- "Request" or "Confirm" sends a driver, and canceling can cost money: tap it only after the user explicitly confirms, then check the ride status.

### Reservations and travel: OpenTable, Resy, airlines, hotels

- Check date, time, party size and time zone.
- Holds, deposits and cancellation policies are part of the result; report them.
- Stop before Reserve, Book or Pay.

### Games (not recommended)

- Each step needs a screenshot and a decision, and the mirror adds lag, so real-time games are out of reach; multi-touch isn't available.
- Many games forbid automated play; accounts can be banned.
- Never make in-app purchases.

### Banking, payments and trading (not recommended)

- These apps may show a black screen in the mirror, refuse to work, or ask for Face ID at every step.
- Transfers, payments and trades are the user's to do. At most, the AI can find the right screen and read out what's on it.

# Validation

Version 0.6.0, September 28, 2026.

Test setup: Codex's Computer Use with the Astra model (gpt-6-astra), one Mac and one iPhone, Chinese-language apps.

## Tested

**September 25, single-app tasks**: Computer Use on the Mac operated Chinese-language apps through iPhone Mirroring. Three items went into a Taobao cart with no payment; a WeChat reply was written and not sent. Typing ASCII keys and picking the phone's Pinyin candidates entered Chinese; typing Chinese directly and pasting from the Mac didn't work in those fields. The owner helped with the connection and input setup.

**September 26, one cross-app task, about 22 minutes**: starting from a WeChat message, the agent compared three restaurants in Dianping against the message's constraints; after confirming the destination calendar was neither shared nor public, it created a private event for October 10, 6–8 PM, with the restaurant's name and address; it wrote the reply in WeChat without sending it; then it reopened the event from the day timeline to check it. Along the way:

- The restaurant name went in through Pinyin candidates; one word wouldn't come up, so a word containing the needed character was committed and the extra character deleted.
- The 12-hour time field turned 18:00 into 8:00 AM, and a retry into 6:00 AM. The agent copied the title, discarded only that unsaved draft, and recreated the event from the 6 PM slot on the day timeline, which set the time correctly.
- Scrolling by month didn't respond; the year view reached the right month. Small scroll steps were used throughout.
- An unexpected "Undo Create" prompt appeared; choosing Cancel kept the saved event.
- A map search showed a different street number from the listing; the listing's text was kept.
- Once the name was right, copying and pasting within the phone carried it into the next field and into the WeChat reply.

The owner restored the mirror and sent the test message before the run and didn't intervene during it.

**September 26, 12306 (China rail)**: the search screen's filter panel wouldn't scroll, so the agent switched to the timetable screen and compared afternoon trains by time and fare. Booking required Face ID sign-in, so it stopped before sign-in and handed over. That run didn't complete a booking.

Two large scrolls crashed iPhone Mirroring; the cause wasn't established. With small scroll steps it didn't happen again.

These are observations from one device and one set of accounts, used to shape the method. They don't establish compatibility across devices or app versions.

## Not yet tested

- A complete run of this version by someone else, on another Mac, iPhone and account.
- Claude and other Computer Use clients following these rules with iPhone Mirroring.
- The appendix's tool syntax comes from the September Codex version; later versions may differ.
- "Write on the Mac, paste on the phone": Apple supports copying between Mac and iPhone through Universal Clipboard, and this version tries it first, but some fields didn't take the paste in September. Which fields work reliably with Handoff on still needs testing.
- English-language apps and every app type under "untested" in [App notes](apps.md).
- Input methods other than Pinyin, and right-to-left or mixed-direction text.
- Whether banking and payment apps display and work in the mirror.
- More kinds of ads and permission prompts, and controlled disconnect-and-resume tests.

After testing, write concrete results back here, including failures and owner help. Only what actually ran end to end counts as tested.

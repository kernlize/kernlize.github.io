# Everything between an applet and the world.

> What the kernl guard does between an applet and your network: a sealed sandbox, verified bytes, budgets, flood control and a question before anything destructive is signed, loosened only by you.

The guard is the set of protections that sit between an applet and you. It is **on from the first second**, in its strict setting. It tells you when it acts and why, and only you can loosen it.

## Eleven protections, in plain words.

1. **A sealed sandbox**
   Each applet runs in a frame with no address of its own and a policy that forbids every network call, and it cannot open a frame of its own inside it. The only way out is through the shell, where you can see it, take back what you granted, or close the applet. It does not even learn which account you use unless you grant it.
2. **Identity bound to the bytes, with revocation**
   An applet's identity is tied to the exact code you verified and to the live connection it runs over. If either changes, the connection is cut and the frame is removed. What you allowed stays with that exact code, so it applies again when you reopen it; changed code starts with no grants.
3. **Verified before it runs, re-checked from cache**
   Applet code is checked against its content hash before the first run. Cached copies are checked again on every read, so a tampered cache cannot slip past.
4. **Old or repeated posts are not sent**
   When the shell posts for an applet, it refuses a post it has already sent in the last half minute, one dated too far in the past, or one dated in the future. A message from a window other than the applet's own is ignored.
5. **Behavioural rate limits**
   Reading, publishing, messaging, storage and downloads each have an allowance per applet, set before it starts. A request over its allowance is refused until the allowance refills. Deletions count against publishing, and are also counted on their own so you can see an applet that deletes a lot.
6. **Focus-aware tightening**
   An applet you are not looking at is measured against a smaller budget. A request over it is refused before it is handled, and the guard tells you; the applet can try again once you switch to it. The budget above still applies. The shell decides what is focused; the applet is never asked.
7. **Hidden applets cannot act until you can see them**
   While an applet is minimised or hidden, the shell refuses its requests before they are handled, except the messages that let you close, theme or reach it; the applet can try again once it is visible. One that keeps asking for downloads past its allowance is quarantined: the download that crossed the allowance is dropped, and the shell closes it and tells you.
8. **Flood control and quarantine**
   The shell counts every message an applet sends. Requests in a burst above the per-second rate are refused before they are handled, and the shell tells you; messages that keep the window controllable still get through. One that keeps flooding is quarantined: the message that crossed the limit is dropped, and the shell closes the applet and tells you. You can open it again when you choose.
9. **Oversized requests are refused**
   Requests for files and long-running searches are measured against a maximum size. One that is too large is refused before it is handled, so nothing it asked for is fetched, and the shell tells you.
10. **Device permissions denied**
    Camera, microphone, location and the rest are off for every applet. There is no prompt to be tricked into.
11. **Consent for destructive changes**
    Before the shell signs anything for an applet that overwrites or erases part of your public record (your profile, who you follow, your servers, one of your lists or any other record a new version replaces, a deletion, or a request to erase your account), it shows you what changes compared with the current version and waits for your answer. If the current version cannot be loaded, it says so. If you say no, nothing is signed. Everyday posts go through without a question, and the shell asks again every time.

*What you see*

## What it reports, it explains.

The guard records what it reports, refuses or quarantines, each with a stable reason you can read. Some refusals made inside the runtime that runs applets are not shown yet; they will be listed as soon as the runtime reports them.

*Loosening it*

## By you, and only you.

Three profiles exist: strict, balanced and relaxed. The shell boots strict, every time. For now the choice applies to the whole shell and is forgotten when you reload; easing one applet at a time is planned. No configuration file or developer flag can ease the guard. The [documentation](https://kernlize.github.io/docs/) lists each limit by profile.

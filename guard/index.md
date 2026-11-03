# Everything between an applet and the world.

> What the kernl guard does between an applet and your network: a sealed sandbox, verified bytes, rate limits, flood control and consent, loosened only by you.

The guard is the set of protections that sit between an applet and you. It is **on from the first second**, in its strict setting. It tells you when it acts and why, and only you can loosen it, one applet at a time.

## Eleven protections, in plain words.

1. **A sealed sandbox**
   Each applet runs in a frame with no address of its own and a policy that forbids every network call. The only way out is through the shell.
2. **Identity bound to the bytes, with revocation**
   An applet's identity is tied to the exact code you verified and to the live connection it runs over. If either changes, every grant it held ends at once and the frame is removed.
3. **Verified before it runs, re-checked from cache**
   Applet code is checked against its content hash before the first run. Cached copies are checked again on every read, so a tampered cache cannot slip past.
4. **Replay detection**
   A message the shell has already handled is not handled twice, and a message meant for one window cannot be replayed into another.
5. **Behavioural rate limits**
   Each kind of request has its own budget per applet. An applet that asks too often is made to wait, and you can see the counter.
6. **Focus-aware tightening**
   An applet you are not looking at gets a smaller budget. The shell decides what is focused; the applet is never asked.
7. **Hidden-window deferral**
   Traffic from a hidden or minimised applet waits until you bring it back. When you do, the queue drains in order.
8. **Flood control and quarantine**
   An applet that floods the shell is queued, then quarantined. Quarantine lasts until you lift it.
9. **Size caps**
   Requests for files and subscriptions have a maximum size. Oversized ones are refused rather than buffered.
10. **Device permissions denied**
    Camera, microphone, location and the rest are off for every applet. There is no prompt to be tricked into.
11. **Consent for destructive changes**
    Anything that deletes, publishes or sends on your behalf is shown to you as what it changes, and waits for your yes.

*What you see*

## Every refusal has a reason.

The guard emits an event for every request it slows, defers, refuses or quarantines, with a stable reason you can read. Nothing is silently dropped.

*Loosening it*

## Per applet. By you.

Three profiles exist: strict, balanced and relaxed. The shell boots strict. You can ease one applet from the grants panel; no configuration file or developer flag can ease them all. The [documentation](https://kernlize.github.io/docs/) lists each limit by profile.

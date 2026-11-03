# Five opinions, held on your behalf.

> The five opinions behind kernl, in plain words: one place for your things, a shell that contains applets, protections on by default, many networks, no ranking.

kernl is built on [kehto](https://github.com/kehto/web), a toolkit that deliberately decides nothing. kernl decides everything kehto left open, and every decision breaks the same way: **towards the person at the keyboard**.

01

## Everything in one place, reached one way.

Your messages, contacts, files and account live in one store inside the shell, read through one connection and signed by one account manager. kernl does not hedge that with a second library doing the same job, because every extra copy is another thing to protect.

- Applets never get a handle on the store. Services read from it for them.
- Your keys are never raw bytes outside the signer that holds them.
- One path in and out means one place to watch.

02

## The shell exists to empower you and to contain the applet.

A shell has two jobs. It gives you a place where your identity and your things are yours and portable. And it gives an untrusted program a place to run where the worst it can do is bounded. kernl cannot protect you from everything. It does all of it that it can.

- Applets run in a sealed frame with no network of their own.
- They never hold keys and never see text you did not ask to show them.
- Every write the shell makes for an applet is shown to you as what it changes, not as code.
- An applet's identity is bound to the exact bytes you verified. Changed bytes are a new applet, with no grants.

03

## Protections are on by default. You loosen them, not the developer.

When the toolkit offers a privacy or safety mitigation, kernl turns it on, in its strict setting, and documents how to ease it. You matter more than the applet developer does. Within reason: an applet interface so tight that nothing can be written protects nobody.

- The [guard](https://kernlize.github.io/guard/) ships strict, with focus-aware tightening.
- Hidden and minimised applets have their traffic deferred.
- A protection is loosened per applet, by you. Never globally, never by a flag.

04

## One account, many networks, no brand names.

Your account is how you are known, how applets are found and verified, and how you reach other people. It is not the only network kernl speaks. Downloads, sharing and mail plug in as [bridges](https://kernlize.github.io/bridges/), behind the same consent and quota rules as everything else.

- Bridges are named by what they do for you, not by the wire format they speak.
- This site does not name protocols. The protocol is the plumbing. The person is the point.

05

## No private-messaging system is "the best".

kernl supports any reasonable private-messaging provider through one interface. You pick the one your correspondent can read, and the shell makes that choice visible and reversible.

- The shell does not rank providers. It [describes them](https://kernlize.github.io/messaging/): forward secrecy or not, what the network can see, whether the other person needs the same app.
- Applets see one messaging surface that spans every provider you enabled.

## The tie-breakers, in order.

1. **Your safety and agency**
   Always first.
2. **Doing what the open format actually says**
   Conformance with the upstream specification, not a convenient reading of it.
3. **The applet developer's ability to build**
   A competent developer, reading the docs, must still have a clear path.
4. **Documentation accuracy**
   A feature without docs is not shipped.
5. **Performance, then code size**
   In that order, and last.

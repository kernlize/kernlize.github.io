# Run things you don't have to trust.

> kernl is a shell that runs small applets in a sealed sandbox. Your identity, contacts, messages and files stay yours; applets borrow them only while you watch.

kernl runs small, self-contained applets in a sealed sandbox. **Your identity, contacts, messages and files are yours** and travel with you. An applet borrows them only with your say-so, and only while you watch.

Pass, slow down, or cut off. Each line is a decision you can see.

## A window, a loan, and a line it cannot cross alone.

*Sealed*

### A window of its own

Each applet runs in a sealed frame with no address of its own and no way to call out, and it cannot open a frame of its own inside it. It can draw and compute; it cannot reach anything you did not hand it.

*Borrowed*

### Your things, on loan

Contacts, messages, files and your account are read by the shell on the applet's behalf. A grant is something you gave and can take back, and the shell shows what each one changes.

*Watched*

### A network it reaches through you

Everything an applet sends or fetches goes through the shell. The guard shows you what it reports, refuses or quarantines; some refusals made deeper inside the shell are not listed yet. You can block an applet, take back any grant, or make the guard stricter for the whole shell, at any time.

## kernl is opinionated so you don't have to be.

It is built on [kehto](https://github.com/kehto/web), an open toolkit that leaves every choice open. kernl makes the choices, in your favour, and writes down why.

1. **Everything in one place, reached one way**
   One store, one connection, one account manager. There is no second copy of your world for an applet to get at.
2. **The shell empowers you and contains the applet**
   Those are its only two jobs, in that order.
3. **Protections are on by default**
   The shell starts strict on every visit. Only you can ease it, for the whole shell until you reload; easing one applet at a time is planned. A developer flag never can.
4. **One account, many networks, no brand names**
   Downloads, sharing and mail plug in as bridges named by what they do for you.
5. **No private-messaging system is "the best"**
   The shell describes each provider truthfully and lets you choose the one your correspondent can read.

[Read the five opinions](https://kernlize.github.io/why/)

## Alpha, and said so.

kernl is alpha software. The sandbox and the guard work today. Private messaging providers are described and you can choose one, and sending works in the preview; the real messaging backends are not connected yet. Bridges for downloads, sharing and mail have their contracts in place and wait for backends too. The shell shows anything without a backend as unavailable rather than pretending.

Applets are verified by content hash before they run and re-checked on every read from cache. If the bytes change, the applet's grants die with them.

[Build on it](https://kernlize.github.io/developers/) [Read the decisions](https://kernlize.github.io/docs/decisions)

## Free. $0, no tier, no catch.

*Price*

### $0

No subscription and no paid features. The whole shell is the free version.

*Licence*

### MIT

The source is private during alpha and opens under the MIT licence with the first public release. The decisions behind it are public now.

*To try it*

### No sign-up

[Open the preview](https://kernlize.github.io/app/?preview=1) and use the shell with sample applets, entirely in your browser.

## Asked often, answered plainly.

### What is an applet?

A small, self-contained program published as a single verified file. kernl checks its content hash before it runs and gives it a sealed window with no network of its own.

### What can an applet see?

Only what you grant, for as long as you grant it. By default it sees your theme, its own storage and which account is signed in. Network access, messages, notifications and files are each a separate grant you can take back.

### Does kernl hold my keys?

No applet ever does. You can sign in with a browser extension or a remote signer so your key never enters the shell, or create a local account whose key is encrypted with a password you choose.

### What does kernl cost?

Nothing. kernl is free, with no account to buy and no paid tier. It is MIT licensed; the source is private during alpha and opens with the first public release.

### Can I try it without signing in?

Yes. The preview runs the whole shell in your browser with sample applets and a throwaway account. Nothing leaves the tab.

### Is it ready for daily use?

Not yet. kernl is alpha software. The sandbox and the guard work. Private messaging is half done: the shell describes each provider and lets you pick one, and sending works in the preview, but the real backends are not connected yet. Downloads, sharing and mail are waiting for their backends too, and the shell says so.

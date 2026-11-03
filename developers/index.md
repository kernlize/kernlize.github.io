# Build something people can run without trusting you.

> How to build for kernl: write an applet in the open applet format, learn what the sealed sandbox and strict guard mean for your code, and read the docs first.

An applet for kernl is a small, self-contained web page in the open applet format. It gets a sealed window, asks for what it needs, and reaches the world through the shell. **That constraint is the feature.**

## Three places to read.

*Docs*

### [kernl documentation](https://kernlize.github.io/docs/)

Concepts, how-tos and the reference for every package: the guard and its profiles, messaging providers, bridges and the shell's composition root.

*Toolkit*

### [kehto](https://github.com/kehto/web)

The open, unopinionated toolkit kernl is built on. If you want to build a different shell with different opinions, start there.

*Format*

### [Applets under kernl](https://kernlize.github.io/docs/concepts/applets-under-kernl)

How applets are packaged, addressed and verified, and the message domains an applet can ask a shell for. kernl hosts this format without changing it; the full specification lives on [the applet format's site](https://napplet.run/).

## What your applet gets, and does not.

1. **A sealed window**
   Your code runs in a frame with no origin and a policy that blocks every direct network call. Draw, compute, and talk to the shell over its message port.
2. **Grants, not permissions**
   Ask for the domains you need. The shell narrows what it advertises to what the user has granted, shows every overwrite or deletion as what it changes before signing it, and lets the user take a grant back. Knowing who is signed in is a grant too: ask for the user's account if you need it.
3. **The strict profile**
   Rate limits, size caps, a hidden-window download allowance and focus-aware tightening are on. Design for them: batch requests, do less when hidden, and expect a refusal to carry a stable reason you can show.
4. **Verified bytes**
   Your applet is identified by the hash of its content. Ship a new version and it is a new identity with fresh grants. That is deliberate.
5. **Messaging across providers**
   One messaging surface spans every provider the user enables. You do not pick the provider; the user does. In this alpha private and legacy messages work in the live shell when the signed-in account can encrypt; ratchet sessions do not, and nothing is available while nobody is signed in. A send through a provider that cannot serve it fails with the reason `unavailable`. Feature-detect messaging and handle `unavailable` as a normal answer, not a crash.

*Source*

## MIT, opening after alpha.

Four small packages and one app. Behaviour is specified in scenarios before it is implemented, and coverage is complete. Decisions, and the reasons for them, are written down and published now. The source itself is private during alpha and opens under the MIT licence with the first public release.

[Read the decisions](https://kernlize.github.io/docs/decisions)

*For agents*

## Read this site as text.

Every page has a Markdown twin at `index.md` next to it, listed in [llms.txt](https://kernlize.github.io/llms.txt). The full text is in [llms-full.txt](https://kernlize.github.io/llms-full.txt), and the docs publish their own.

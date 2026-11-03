# kernl

kernl is an opinionated shell for sandboxed web applets. It is built on [kehto](https://github.com/kehto/web), the unopinionated NIP-5D toolkit, and it treats the person at the keyboard as the only principal who matters.

A shell has two jobs. It gives the user a place where their identity, relays, contacts, media and messages are theirs and portable. And it gives an untrusted program a place to run where the worst it can do is bounded. kernl does both, and when kehto offers a way to bound an applet further, kernl turns it on by default.

> **Alpha**
>
> kernl is a first draft. The four packages build, the contracts are stable enough to document, and the shell runs. Several backends are contracts without implementations. Read [Alpha status](https://kernlize.github.io/docs/alpha-status.md) before depending on anything here.

## What kernl decides that kehto leaves open

kehto ships `@kehto/{acl,firewall,runtime,shell,services,nip,wm}` and deliberately does not pick a relay library, a signer, a consent model, a layout engine or a deployment story. kernl picks all of them:

| Opinion | kernl's choice |
| --- | --- |
| Event layer | [applesauce](https://applesauce.build) v7 only. One `EventStore`, one `RelayPool`, one `AccountManager` per shell. `nostr-tools` is never imported by kernl source. |
| Containment | Opaque-origin `srcdoc` iframe, `sandbox="allow-scripts"`, zero-network CSP, every network path through a shell service the user can see, rate-limit and revoke. |
| Mitigations | Every kehto mitigation ships on, in the `strict` [guard](https://kernlize.github.io/docs/concepts/guard.md) profile. The user loosens per applet; a developer never loosens globally. |
| Protocols | One identity layer, many [bridges](https://kernlize.github.io/docs/concepts/bridges.md) named by what they do for the user, never by the wire format. |
| Messaging | Any reasonable private-messaging protocol, exposed through one contract. [Providers](https://kernlize.github.io/docs/concepts/messaging.md) describe their security properties truthfully and the shell does not rank them. |

kernl does not fork kehto. When kehto lacks a hook kernl needs, kernl composes around it and files the gap upstream. The four gaps filed so far are recorded in [D-001](https://kernlize.github.io/docs/alpha-status.md#upstream-gaps).

## Three doors

**Use the shell.** Run kernl locally, sign in with a browser extension or a remote signer, and open an applet by its address. Start with [Run the shell](https://kernlize.github.io/docs/tutorials/run-the-shell.md), then read [Grant and revoke](https://kernlize.github.io/docs/how-tos/grant-and-revoke.md) to understand what the shell asks you and why.

**Build an applet for it.** Applets are ordinary NIP-5D napplets; kernl adds nothing to the wire format. What kernl changes is the posture: fewer domains advertised until granted, deferral while hidden, and rate limits that tighten when you lose focus. [Build an applet for kernl](https://kernlize.github.io/docs/tutorials/build-an-applet-for-kernl.md) tells you what to expect and how to test against it.

**Extend the shell.** Add a [messaging provider](https://kernlize.github.io/docs/how-tos/add-a-messaging-provider.md), a [bridge backend](https://kernlize.github.io/docs/how-tos/add-a-bridge-backend.md), or change how the guard is composed. Start with [Architecture](https://kernlize.github.io/docs/concepts/architecture.md) and the [package pages](https://kernlize.github.io/docs/packages/index.md).

## How these docs are organised

| Section | What you find there |
| --- | --- |
| [Concepts](https://kernlize.github.io/docs/concepts/architecture.md) | Why the shell is shaped the way it is: layering, guard, identity, messaging, bridges. |
| [Tutorials](https://kernlize.github.io/docs/tutorials/run-the-shell.md) | End-to-end walkthroughs that leave you with something running. |
| [How-tos](https://kernlize.github.io/docs/how-tos/change-guard-profile.md) | One task each, with the exact calls. |
| [Packages](https://kernlize.github.io/docs/packages/index.md) | One page per published package: version, install, exports, scope. |
| [API reference](https://kernlize.github.io/docs/reference/api.md) | Generated from source JSDoc by TypeDoc. |
| [Policies](https://kernlize.github.io/docs/policies/index.md) | Rules the repository enforces mechanically: vocabulary, security posture, spec conformance. |

Protocol vocabulary is used freely in these pages because they are written for developers. The public website and the shell UI follow a different rule, described in [Public vocabulary](https://kernlize.github.io/docs/policies/public-vocabulary.md).

Agents reading this site should start at [Agent access](https://kernlize.github.io/docs/agent-access.md).

## Licence and cost

kernl is free software under the MIT licence. Every package and the shell cost $0; there is no paid tier and no account to buy. The source, these docs and the decisions behind both live at [kernlize/web](https://github.com/kernlize/web).

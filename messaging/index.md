# Described, not ranked.

> kernl describes several private-message providers and ranks none. Each is described by what it protects. Private, legacy and ratchet messages work in the live shell when your account can encrypt; ratchet sessions are experimental.

kernl is built to offer private messaging through several providers. **None of them is "the best".** The shell tells you plainly what each one protects, and you pick the one the person you are writing to can read.

## Two providers send today; one is still to come.

kernl is alpha software. Private messages and legacy messages work in the live shell once you sign in with an account that can encrypt: a browser extension, a remote signer or a local account on this device. A read-only account cannot, and the shell says so. Ratchet sessions work the same way and are experimental: the person you write to needs an app that speaks them, they are one to one, and the keys that change with every message are kept on this device, locked so only your account can open them. Clearing this site's data ends those sessions. Group sessions work the same way and are experimental too: everyone you add needs an app that speaks them and must have used it once, so that you can invite them; your groups are kept on this device, locked to your account, while their messages last only until you reload. The [preview](https://kernlize.github.io/app/?preview=1) lets you try private and legacy messages without an account, and keeps everything in your browser tab; ratchet sessions need the live shell.

Your messages are opened by your own account, in the Messages panel, for you. An applet sees your messages only if you grant it messages, and you can take that grant back.

## The same six questions, asked of each.

### Private messages

The default. Each message is meant to be wrapped so the network cannot see who wrote it or what it says.

- **Forward secrecy**: No
- **Heals after a key leak**: No
- **Metadata protection**: Partial
- **Other person needs this app**: No
- **Groups**: Yes
- **Experimental**: No

### Legacy messages

The original format, kept so old conversations still open. The content is hidden; who talks to whom and when is not.

- **Forward secrecy**: No
- **Heals after a key leak**: No
- **Metadata protection**: None
- **Other person needs this app**: No
- **Groups**: No
- **Experimental**: No

### Ratchet sessions

Keys change with every message, so a leak today does not expose yesterday. Both sides need an app that speaks it.

- **Forward secrecy**: Yes
- **Heals after a key leak**: Yes
- **Metadata protection**: Partial
- **Other person needs this app**: Yes
- **Groups**: No
- **Experimental**: Yes

### Group sessions

A group shares keys that change as it talks and as people join or leave, so a leak exposes neither what came before nor, once the group moves on, what comes after. Everyone in it needs an app that speaks it.

- **Forward secrecy**: Yes
- **Heals after a key leak**: Yes
- **Metadata protection**: Partial
- **Other person needs this app**: Yes
- **Groups**: Yes
- **Experimental**: Yes

## What the rows mean.

- **Forward secrecy**: If your keys leak today, messages from before today stay unreadable.
- **Heals after a key leak**: Once both of you keep writing, a leaked key stops being useful to whoever has it.
- **Metadata protection**: How much someone watching the network learns about who talks to whom and when. "Partial" means the sender and timing are hidden but delivery is not.
- **Other person needs this app**: Whether your correspondent must use an app that speaks the same provider.
- **Experimental**: The provider is still changing and may lose history between versions. kernl says so before you enable it.

Applets are given one messaging surface that spans every provider you enable. The choice of provider stays with you, is shown on every conversation, and can be changed. More in the [documentation](https://kernlize.github.io/docs/).

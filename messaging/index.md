# Described, not ranked.

> kernl describes several private-message providers and ranks none. Each is described by what it protects. In this alpha sending works only in the preview; the real backends are not connected yet.

kernl is built to offer private messaging through several providers. **None of them is "the best".** The shell tells you plainly what each one protects, and you pick the one the person you are writing to can read.

## Described and selectable; sending waits for backends.

kernl is alpha software. Every provider below is described and you can choose one in the shell. Sending works in the [preview](https://kernlize.github.io/app/?preview=1), which keeps everything in your browser tab. In the live shell no provider has a backend yet, so each one shows as unavailable and a send fails with a plain reason instead of pretending.

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

## What the rows mean.

- **Forward secrecy**: If your keys leak today, messages from before today stay unreadable.
- **Heals after a key leak**: Once both of you keep writing, a leaked key stops being useful to whoever has it.
- **Metadata protection**: How much someone watching the network learns about who talks to whom and when. "Partial" means the sender and timing are hidden but delivery is not.
- **Other person needs this app**: Whether your correspondent must use an app that speaks the same provider.
- **Experimental**: The provider is still changing and may lose history between versions. kernl says so before you enable it.

Applets are given one messaging surface that spans every provider you enable. The choice of provider stays with you, is shown on every conversation, and can be changed. More in the [documentation](https://kernlize.github.io/docs/).

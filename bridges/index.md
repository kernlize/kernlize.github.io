# Named by what they do for you.

> Bridges let kernl reach other networks for you. Web fetch works today; downloads, sharing and mail work by handing off to an app on your device. In-shell backends are planned.

A bridge is a service the shell owns that turns a link into bytes or a conversation on another network. An applet never talks to the other network itself; it asks the shell, and the shell answers. **In this alpha web fetch has no consent prompt yet** and refuses private and local addresses by policy. Downloads, sharing and mail hand the link to an app on your device, and the shell asks you before it leaves kernl.

## What works today, and what is waiting.

*Works today*

### Web fetch

Fetches a web address for an applet, through the shell, with a policy that refuses private and local addresses so an applet cannot use you to look inside your own network.

*Hands off to your device*

### Downloads

Understands the links people already share for large files and newsgroup posts, and hands each one to the download app on your device after asking you. kernl itself moves no bytes for it; an in-shell backend is planned.

*Hands off to your device*

### Sharing

Person-to-person file sharing between people who choose each other. The shell opens the sharing app on your device with the file the link names; an in-shell backend is on the roadmap.

*Hands off to your device*

### Mail

Turns a mail link into a new message in the mail app on your device, with the subject and text the link carries. Sending and receiving inside the shell wait for a backend you would run or trust.

Handing off is honest about what happens: the app on your device does the transfer, so what that app shares with the other side is what Settings lists for the bridge, and nothing goes through kernl's own connections. Where no app is set up, nothing opens. A bridge with nothing to hand off to reports itself as unavailable, and an applet cannot tell the difference between "unavailable" and "you said no".

## Every bridge, the same way.

1. **An applet asks; the shell resolves**
   The applet never touches the other network. It hands the shell a link and gets back bytes or a conversation, or a reason.
2. **Not yet: seeing each request**
   Bridge requests are not listed in the [guard](https://kernlize.github.io/guard/) yet, and there is no per-applet allowance for them. Until those exist, the shell does not claim either.
3. **Named for people**
   "Downloads", "sharing", "mail". Not the name of the wire format underneath. If you care which one it is, the documentation says.

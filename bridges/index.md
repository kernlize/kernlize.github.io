# Named by what they do for you.

> Bridges let kernl reach other networks for you. Web fetch and downloads from peers work inside kernl today; newsgroup downloads, sharing and mail hand off to an app on your device.

A bridge is a service the shell owns that turns a link into bytes or a conversation on another network. An applet never talks to the other network itself; it asks the shell, and the shell answers. **In this alpha web fetch has no consent prompt yet** and refuses private and local addresses by policy. Files shared by peers download inside kernl. Newsgroup downloads, sharing and mail hand the link to an app on your device, and the shell asks you before it leaves kernl.

## What works today, and what is waiting.

*Works today*

### Web fetch

Fetches a web address for an applet, through the shell, with a policy that refuses private and local addresses so an applet cannot use you to look inside your own network.

*Works today*

### Downloads from peers

Links to files that people share with each other download inside kernl, in the Downloads panel, where you can pause, resume, remove and save them. Peers see your network address and what you fetch. If you prefer, Settings sends these links to the download app on your device instead.

*Hands off to your device*

### Newsgroup downloads

Understands the links people share for newsgroup posts, and hands each one to the download app on your device after asking you. kernl itself moves no bytes for it.

*Hands off to your device*

### Sharing

Person-to-person file sharing between people who choose each other. The shell opens the sharing app on your device with the file the link names; an in-shell backend is on the roadmap.

*Hands off to your device*

### Mail

Turns a mail link into a new message in the mail app on your device, with the subject and text the link carries. Sending and receiving inside the shell wait for a backend you would run or trust.

Why some bridges hand off: a web page may only make web requests and direct connections to other browsers. Newsgroup servers, sharing networks and mail servers need a kind of connection no web page is allowed to open, so until kernl can reach a helper you run or trust, an app on your device does that part.

Handing off is honest about what happens: the app on your device does the transfer, so what that app shares with the other side is what Settings lists for the bridge, and nothing goes through kernl's own connections. Where no app is set up, nothing opens. A bridge with nothing to hand off to reports itself as unavailable, and an applet cannot tell the difference between "unavailable" and "you said no".

## Every bridge, the same way.

1. **An applet asks; the shell resolves**
   The applet never touches the other network. It hands the shell a link and gets back bytes or a conversation, or a reason.
2. **Not yet: seeing each request**
   Bridge requests are not listed in the [guard](https://kernlize.github.io/guard/) yet, and there is no per-applet allowance for them. Until those exist, the shell does not claim either.
3. **Named for people**
   "Downloads", "sharing", "mail". Not the name of the wire format underneath. If you care which one it is, the documentation says.

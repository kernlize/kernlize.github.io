# Named by what they do for you.

> Bridges let kernl reach other networks for you. Web fetch works today; downloads, sharing and mail have their contracts in place and wait for their backends.

A bridge is a service the shell owns that turns a link into bytes or a conversation on another network. An applet never talks to the other network itself; it asks the shell, and the shell answers. **In this alpha there is no consent prompt for bridges yet**: web fetch refuses private and local addresses by policy, and the other bridges are not connected to anything.

## What works today, and what is waiting.

*Works today*

### Web fetch

Fetches a web address for an applet, through the shell, with a policy that refuses private and local addresses so an applet cannot use you to look inside your own network.

*Needs a backend*

### Downloads

Understands the links people already share for large files and newsgroup posts. The parsing and the contract exist; the part that actually moves bytes does not yet.

*Needs a backend*

### Sharing

Person-to-person file sharing between people who choose each other. Same story: the contract is in place and tested, the backend is on the roadmap.

*Needs a backend*

### Mail

Turns a mail link into a conversation. The locator is parsed and the contract is defined; sending and receiving wait for a backend you would run or trust.

A bridge without a backend reports itself as unavailable, and the shell shows exactly that. It will not pretend, and an applet cannot tell the difference between "unavailable" and "you said no".

## Every bridge, the same way.

1. **An applet asks; the shell resolves**
   The applet never touches the other network. It hands the shell a link and gets back bytes or a conversation, or a reason.
2. **Not yet: seeing each request**
   Bridge requests are not listed in the [guard](https://kernlize.github.io/guard/) yet, and there is no per-applet allowance for them. Until those exist, the shell does not claim either.
3. **Named for people**
   "Downloads", "sharing", "mail". Not the name of the wire format underneath. If you care which one it is, the documentation says.

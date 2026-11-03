# Named by what they do for you.

> Bridges let kernl reach other networks for you. Web fetch works today; downloads, sharing and mail have their contracts in place and wait for their backends.

A bridge is a service the shell owns that turns a link into bytes or a conversation on another network. Every bridge sits behind **the same consent and quota rules** as everything else an applet can ask for.

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
2. **You see the request**
   Each request shows up in the [guard](https://kernlize.github.io/guard/) with what it is for, and counts against the applet's budget.
3. **Named for people**
   "Downloads", "sharing", "mail". Not the name of the wire format underneath. If you care which one it is, the documentation says.

# cfengine2
A repository to track some of my hacks on ancient cfengine2 code and the work necessary to make Debian packages out of them.

This repository was created to publish and help track some fixes to the very ancient cfengine2 code that unfortunately our organization still relies upon.

Yes, I realize that that's largely a wasted effort since lots of improved projects like cfengine 3.x, SaltStack, Chef, etc. are out there.  However, we have some 50k lines of cfengine2 inputs files (ie: not including any of the actual service config file artifacts), and simply put it's currently (surprsingly) easier to fix the few truely deficient parts of cfengine2 than it is to port all our configs over to a new system.  Also, cfengine2 isn't changing anymore, so it's actually somewhat more stable than those other things (at least for what it is).  Given that the package is still available in Debian, I imagine there are others in this boat as well.

Major fixup/enhancement hilights currently include:
- More unique `link`/`copy` lock names (avoiding lock collisions that cause actions not to be performed).
- Improved last action timing checks (a related fixup to the lock name collisions issue).
- Skip some `libdb` `fdatasync()` operations on repetive `open()`/`close()` `cfengine_lock_db` and `performance.db` operations (major speed improvements on `cfagent` runs, general avoids the previous two conditions).
- Add `TCP_NODELAY` flag to `cfservd` and `cfagent` connections (avoid some buffering delays on small file copy stat operations).
- Enable POSIX ACL support for non-Solaris machines (**TODO**).

===============
LightLdapd NEWS
===============

This is a summary of user visible changes for each release. Where
possible it includes references to bug and patch numbers. Please
ensure that things are moved to here from the TODO file as they get
done. Before doing a release please ensure that this document is up to
date.

Changes in 1.0 (Not released yet)
=================================

* Forked LightLdapd project from entente.

  With permission and thanks to Sergey Urbanovich, the author of
  entente.


Changes in entente 1.1 (merged 2014-01-25)
==========================================

* Improve options.

  Make -b basedn argument work. Make -l loopback argument work.
  Simplified and removed environment based settings.

* Make pam authentication failures non-blocking:

  It will nolonger stall all connections ~2 seconds whenever someone
  tries a bad user/passwd. Instead only the connection that failed to
  bind is paused for time configured by pam_fail_delay.

* Improved bind result failure returncodes.

  Changed the bind failure response resultcode from "other" to
  "invalidDNSyntax" or "invalidCredentials", depending on why it failed.

* Tidy code.

  Reformated using "indent -linux -l120". Added a "tidy" make target
  to do this automatically.

  Tidied up lots of code, simplifying methods, renaming things to be
  more consistant, and make better use of common library functions.

  Made all memory allocation checking to use "alloc or die" macro's,
  since libev will abort on alloc failures anyway.

* Improved/updated debian build:

  Updated for debhelper v9. Added debclean make target.


Changes in entente 1.0 (committed 2011-04-11)
=============================================

* Initial Release

  Published at https://github.com/urbanserj/entente. Does enough to
  work as a pam_ldap auth server.


----

$Id: TODO,v 1.40 2004/10/18 02:30:53 abo Exp $

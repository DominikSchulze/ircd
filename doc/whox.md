## Introduction
See https://ircv3.net/specs/extensions/whox

## Additional non-standard fields
The following additional fields have been added:
- `S`: return the SID
- `U`: return the UID

## Examples
Username/ident, IP address, hostname, nick

    WHO #ircd %uihn
    :dev.irc.it 354 test ~username 92.74.191.157 dslb-092-074-191-157.092.074.pools.vodafone-ip.de test
    :dev.irc.it 354 test ~patrick 54.38.153.88 de.ircnet.com patrick_
    :dev.irc.it 354 test ~patrick 255.255.255.255 patrick.users.contempt.chat patrick
    :dev.irc.it 315 test #ircd :End of WHO list.

Nick and UID

    WHO #ircd %nU
    :dev.irc.it 354 test test 380DAAAAB
    :dev.irc.it 354 test patrick_ 380IAAADS
    :dev.irc.it 354 test patrick 380IAAADL
    :dev.irc.it 315 test #ircd :End of WHO list.

SID only

    WHO #ircd %S
    :dev.irc.it 354 test 380D
    :dev.irc.it 354 test 380I
    :dev.irc.it 354 test 380I
    :dev.irc.it 315 test #ircd :End of WHO list.

All information

    WHO #ircd %tcuihsnfdlaorSU,123
    :dev.irc.it 354 test 123 #ircd ~username 92.74.191.157 dslb-092-074-191-157.092.074.pools.vodafone-ip.de dev.irc.it test H 0 262 0 n/a 380D 380DAAAAB :realname
    :dev.irc.it 354 test 123 #ircd ~patrick 54.38.153.88 de.ircnet.com nova.irc.it patrick_ H 1 0 0 n/a 380I 380IAAADS :email: patrick@ircnet.com
    :dev.irc.it 354 test 123 #ircd ~patrick 255.255.255.255 patrick.users.contempt.chat nova.irc.it patrick H*@ 1 0 patrick n/a 380I 380IAAADL :Patrick
    :dev.irc.it 315 test #ircd :End of WHO list.
    
Legacy: Former 'o' flag which filters for opers is still working with or without WHOX fields

    who #ircd o%n
    :dev.irc.it 354 test patrick
    :dev.irc.it 315 test #ircd :End of WHO list.


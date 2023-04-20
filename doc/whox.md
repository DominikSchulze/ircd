## Introduction
See https://ircv3.net/specs/extensions/whox

## Additional non-standard fields
The following additional fields have been added:
- `S`: return the SID
- `U`: return the UID

## Examples
    WHO #labs %tcuihsnfdlaorSU,123
    :dev.irc.it 354 test 123 #labs ~me 92.74.191.157 dslb-092-074-191-157.092.074.pools.vodafone-ip.de dev.irc.it test H 0 9 0 n/a 380D 380DAAAAB :Myself
    :dev.irc.it 354 test 123 #labs ~mxl 127.0.0.1 127.0.0.1 hub.ipv4.pl mxl G*@ 3 0 mxl n/a 616H 616HAAAAA :mxl
    :dev.irc.it 354 test 123 #labs ~patrick 255.255.255.255 patrick.users.contempt.chat nova.irc.it patrick H*@ 1 0 patrick n/a 380I 380IAAADL :Patrick
    :dev.irc.it 315 test #labs :End of WHO list.

## Notes
* idle time is 0 for remote users because servers do not receive all PRIVMSGs, e.g. if the user is just messaging himself
* OP level is always "n/a" since we do not support levels

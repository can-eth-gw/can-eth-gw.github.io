---
layout: index
title: Manual cegwsend
subtitle: CAN - Ethernet Gateway Send Utility
---


# NAME

cegwsend - CAN - Ethernet Gateway Send Utility



# SYNOPSIS

__cegwsend__ \[ __\-s__ _SRC MAC_ | __\--src__=_SRC MAC_ \] { __\-d__ _DST MAC_ | __\-dst__=_DST MAC_ \] \[ __\-t__ _ETHERTYPE_ | __\--type__=_ETHERTYPE_ \] { __\-r__ _RAW_ | __\--raw__=_RAW_ } { __\-i__ _IFACE_ | __\--interface__=_IFACE_ }

_ETHERTYPE_ := { __ipv4__ | __ipv6__ | __can__ | __canfd__ | __none__ | __\[0x\]1234__ }



# DESCRIPTION

Send Utility for testing non ip-based ethernet interfaces. You can send with this utility an ethernet package with raw data or with an CAN/CAN-FD Frame as payload.



# OPTIONS

- __\-s__, __\--src__

    The MAC address, which should be written down in the SOURCE field of the ethernet header. In the current version this option is NOT USED.

- __\-d__, __\--dst__

    The MAC address, which should be written down in the DESTINATION field of the ethernet header.

- __\-t__, __\--type__ _ETHERTYPE_, __\--type__=_TYPE_

    Set the EtherType of the Ethernet frame. '__ipv4__', '__ipv6__', '__can__' and '__canfd__' can be translated to their hexadcimal code. All other types must be written like '__0x1234__' or '__1234__. Please note that the last example is a hexadecimal number, too. '__none__' can be used for experimental purposes.

- __\-r__, __\--raw__

    The raw data that should be sent. Please notice that the raw data must be typed in the console as a hexadecimal number like this "01 23 45 67 89 ab cd ef", for example. You can use capital letters for A, B, C, D, E and F, of course.

- __\-i__, __\--interface__

    The name of the Ethernet Interface, that is going to receive the message

# EXIT STATUS

cegwsend returns a zero exit status if the command succeeds. Non Zero if an error has occured.



# COPYRIGHT

(C) Copyright 2013 Fabian Raab, Stefan Smarzly, Jakob Pfeiffer

This file is part of CAN-Eth-GW.

CAN-Eth-GW is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

CAN-Eth-GW is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.
You should have received a copy of the GNU General Public License
along with CAN-Eth-GW. If not, see [http://www.gnu.org/licenses/](http://www.gnu.org/licenses/).

# AUTHOR

Jakob Pfeiffer <jakob.pfeiffer@in.tum.de>

# SEE ALSO

[http://can-eth-gw.github.io/](http://can-eth-gw.github.io/)

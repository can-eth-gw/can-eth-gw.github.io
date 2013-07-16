---
layout: index
title: Manual cegwctl
subtitle: CAN - Ethernet Gateway Control Utility
---

# NAME

cegwctl - CAN - Ethernet Gateway Control Utility


# SYNOPSIS

__cegwctl__ \[ __\-f__ | __\--can-fd__ \] \[ __\-t__ _TYPE_ | __\--type__=_TYPE_ \] \[ __\-b__ | __\--bidirectional__ \] __add__ __route__ _SRC_ _DST_

__cegwctl__ \[ __\-f__ | __\--can-fd__ \] \[ __\-t__ _TYPE_ | __\--type__=_TYPE_ \] __add__ __dev__

_TYPE_ := { __none__ | __eth__ | __net__ | __udp__ | __tcp__ }

__cegwctl__ __del__ __route__ _ID_

__cegwctl__ __del__ __dev__ _NAME_

__cegwctl__ __route__

# DESCRIPTION

Control Utility for the ce\_gw Kernel Programm.



# OPTIONS

- __\-b__, __\--bidirectional__

    If you add a route from SRC to DST, there will be also add the same route back from DST to SRC.

- __\-f__, __\--can-fd__

    A Flag for the larger CAN-FD Frames.

- __\-t__ _TYPE_, __\--type__=_TYPE_

    Set The Type of the Gateway. '__net__' is the Default. __udp__, __tcp__ are not supported yet.

- _TYPE_ := { __none__ | __eth__ | __net__ | __udp__ | __tcp__ } Types

# COMMANDS

- __add__ __route__ _SRC_ _DST_

    Add a Gateway from _SRC_ to _DST_, where SRC and DST are the String names of the Interfaces.

- __add__ __dev__

    Add a virtual ethernet device. You need this device for adding a route. With the options \[ __\-f__ | __\--can-fd__ \] \[ __\-t__ _TYPE_ | __\--type__=_TYPE_ \] you can set a meaningfull MTU.

    	+------+-----+------+--------------------------+
    	| TYPE | FD? | BYTE | MTU Size Description     |
    	+------+-----+------+--------------------------+
    	| NONE | --- | 1500 | Standart Ethernet MTU    |
    	| ETH  | NO  | 8    | Max CAN Payload          |
    	| ETH  | YES | 64   | Max CAN-FD Payload       |
    	| NET  | NO  | 16   | Max CAN Frame            |
    	| NET  | YES | 72   | Max CAN-FD Frame         |
    	| UDP  | --- | 1500 | Standart Ethernet MTU    |
    	| TCP  | --- | 1500 | Standart Ethernet MTU    |
    	+------+-----+------+--------------------------+

- __del__ __route__ _ID_

    Deletes the Gateway with _ID_.

- __del__ __dev__ _NAME_

    Deletes a previously with __add__ __dev__ added device with _NAME_ as name.

- __route__ \[_ID_\]

    List active Gateways and Informations or if _ID_ is specified, Information of the Gateway with _ID_ will printed

# EXAMPLES

Add a Gateway:

          cegwctl -f -t net add route "eth0" "can0"



# EXIT-STATUS

cegwctl returns a zero exit status if the command succeeds. Non Zero if an error has occured.



# COPYRIGHT

(C) Copyright 2013 Fabian Raab, Stefan Smarzly

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

Fabian Raab <fabian.raab@tum.de>



# SEE ALSO

[http://can-eth-gw.github.io/](http://can-eth-gw.github.io/)

ip(8)

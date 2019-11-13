# multicast-relay

Relays multicast traffic from one network to another where multicast routing is disabled between them.

Use case is where multicast traffic on a UAT network is not routed to a developer's workstation but the developer needs to receive this traffic for local application testing.

The relay server runs on the network that is able to receive the multicast traffic.  It listens on a TCP socket for relay requests from a relay client to forward multicast packets for some multicast address.  The relay server forwards the requested multicast packets to the relay client where they are republished locally with a TTL of zero, until the client closes the TCP session.  A relay client may set up multiple relays.

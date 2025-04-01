![[file-20250320023128526.png]]The ***LLC sublayer** takes the network protocol data, which is typically an IPv4 or IPv6 packet, and adds Layer 2 control information to help deliver the packet to the destination node.

The ***MAC sublayer*** controls the NIC and other hardware that is responsible for sending and receiving data on the wired or wireless LAN/MAN medium.

The MAC sublayer provides data encapsulation:

- **Frame delimiting** - The framing process provides important delimiters to identify fields within a frame. These delimiting bits provide synchronization between the transmitting and receiving nodes.
- **Addressing** - Provides source and destination addressing for transporting the Layer 2 frame between devices on the same shared medium.
- **Error detection** - Includes a trailer used to detect transmission errors.

The MAC sublayer also provides media access control, allowing multiple devices to communicate over a shared (half-duplex) medium. Full-duplex communications do not require access control.

###### At each hop along the path, a router performs the following Layer 2 functions:

###### 1. Accepts a frame from a medium
###### 2. De-encapsulates the frame
###### 3. Re-encapsulates the packet into a new frame
###### 4. Forwards the new frame appropriate to the medium of that segment of the physical network


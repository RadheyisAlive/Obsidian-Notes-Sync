A switch is made up of integrated circuits and the accompanying software that controls the data paths through the switch. Switches use destination MAC addresses to direct network communications through the switch, out the appropriate port, toward the destination.

For a switch to know which port to use to transmit a frame, it must first learn which devices exist on each port. As the switch learns the relationship of ports to devices, it builds a table called a MAC address table. This table is stored in content addressable memory (CAM) which is a special type of memory used in high-speed searching applications. For this reason, the MAC address table is sometimes also called the CAM table.
### Step 1: Learn (Examine the Source MAC Address)

- **What happens?**: Every time a frame enters a switch, it checks the **source MAC address**.
    - **If the MAC address is new** (not in the table), it adds the **MAC address** and the **incoming port** to the **MAC address table**.
    - **If the MAC address is already in the table**, it updates the **timer** for that MAC address entry.
    - **If the MAC address is on a different port** than before, it updates the table with the new port.

### Step 2: Forward (Examine the Destination MAC Address)

- **What happens?**: The switch looks at the **destination MAC address** in the frame.
    - **If the destination MAC address is found** in the MAC address table, the switch **forwards the frame** out of the correct port associated with that MAC.
    - **If the destination MAC address is not in the table**, it **floods the frame** (sends it out on all ports except the one it came in on).
    - **For broadcast or multicast frames**, it floods them to all ports as well.

### In Short:

- **Learn**: Switch remembers the source MAC and port.
- **Forward**: Switch uses the destination MAC to send data to the correct port or floods if it doesn't know.
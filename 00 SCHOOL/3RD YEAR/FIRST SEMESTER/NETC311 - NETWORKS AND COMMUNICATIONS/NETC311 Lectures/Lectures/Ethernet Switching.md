Ether - Source
Encapsulation 

## Ethernet Frames
### Ethernet Encapsulation
- Ethernet operates in the __data link layer__ and the __physical layer.__
- a family of networking tehnologies defined in the ___IEEE 802.2___ and ___802.3___ standards
- Data Link Layer has 2 sub-layers: LLC & MAC

### Data Link Sublayers
- 802 LAN/MAN standards including Ethernet 
    - Uses two separate sublayers of the data link layer to operate:
         - __LLC__ Sublayer ___(IEEE 802.2)___ - Places info in the frsme to identify which network layer protocol is used for the frame.
         - __MAC__ Sublayer (___IEEE 802.3, 802.11, or 802.15___) - Responsible for 
             - data encapsulation and 
             - media access control, and 
             - provides data link layer addressing


### MAC Sublayer
- Responsible for data encapsulation and accessing the media.
#### IEEE 802.3 data encapsulation includes:
1. __Ethernet frame__ - Internal structure of the Ethernet frame
2. Ethernet Addressing - Eth. frame included both a source and destination MAC address to deliver the Eth frame from Eth. NIC to Eth NIC on the same LAN
3. Ethernet Error Detection - Eth. frame includes a frame check sequence (FCS) trailer used for error detection.

#### Media Access


### Ethernet Frame Fields
- __Minimum__ Ethernet frame size: __64 Bytes__
    - Any frame less 64 bytes in length is considered a "collision fragment" or "runt frame"
        - Automatically discarded
- ___Maximum___ Ethernet frame size: ___1518 Bytes___
    - Frames more than 1500 bytes are considered "jumbo" or "baby giant"

## Ethernet MAC Address
- Every networl device iz 

### Frame Processing
- the Ethernet header include a Source MAC Address and 


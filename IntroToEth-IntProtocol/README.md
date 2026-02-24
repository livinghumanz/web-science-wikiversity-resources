# Week 1 Quiz ( Introduction to Ethernet and Internet Protocol)

1. ### What is not a part of ethernet Frame ? (Ethernet Frame Vs Packet)
    - [X] **Preamble**
    - [ ] CRC
    - [ ] payload
    - [ ] MAC Header 

2. ### Ethernet packet structure in correct Order
    - Preamble 
    - Mac Destination
    - Mac Source
    - Length 
    - Payload
    - Frame Check Sequence
    - IPG (Inter-Packet Gap)

3. ### Cable Issue
- #### Let us consider two cables of 20 meters each. One of them is in a 100MBps network while the other is in a 10MBps network. If you had to transfer data through each of them, how much time it would take for the first bit to arrive in each setting?
    _For your calculation you can assume that the speed of light takes the same value as in the videos. Round the answer to the nearest hundredth._

Speed of Light = $300 * 10^6$
Cable length = 20 mtrs

Network1 = 100MBps => 100 million Bits per second

$$
\displaylines{
100 * 10^6 bits/sec \\ 
\text{Time per bits} = 100 * 10^{-6} => 10^{-8} sec (10ns)\\
}
$$

> for sending 1 bit ~ 10ns of time is taken 

Network2 = 10MBps => 10 million Bits per second

$$
\displaylines{
10 X 10^6 bits/sec \\
\text{Time per bits} = 10 X 10^{-6} => 10^{-7} sec (100ns)\\
}
$$

> for sending 1 bit ~ 100ns of time is taken 

_distanceCovered = Speed X Time_

$$
\displaylines{
\text{TimeTaken} = \frac{20 mtrs}{300 * 10^6} \\
\text{TimeTaken} = 6.6667 * 10^{-8} => 66.67 *10^{-7} \\
\text{TimeTaken} = 66.67 sec\\
}
$$

4. ### Why does a collision occur in an Ethernet network?
    - [X] **Two or more devices attempt to transmit data simultaneously.**
    - [X] **Data are sent across shared medium.**
    - [ ] The Ethernet network is using fiber-optic cables instead of copper.
    - [ ] Cables are too long, causing signal loss.
    - [ ] The network is using full-duplex communication, causing data packets to overlap.
    - [ ] Ethernet switch does not have enough memory to store all data packets.

5. ### Collision Detection ( Bring the steps of collision detection algorithm in correct order. )
    * >Computer A assembles an Ethernet frame
    * >Computer A attempts to send data for the first time
    * >Computer A listens the medium to check anyone sending data already and waits if "the line is busy"
    * >Computer A transmits the first bit of the frame
    * >System checks for collision: If no collision is detected, check if transmission is finished. If there are still more bits, transmit the next bit of the frame in the next clock cycle.
    * >Computer sends another bit check if collision is detected and repeat steps this until transmission is finished or collision is detected.
    * >If collision is detected, Computer A checks if the number of attempts is bigger than max number of attempts. If yes, system will stop sending data to avoid wasting of time or endless loop.
    * >If the max number of attempts is not reached - computer A choses wait number (from 0 to 16)
    * >"Wait" is a loop. Each time we reduce it by one and wait for one time slot or 512 clock cycles; during this time Computer A avoids sending data.
    * >When wait number is 0 - increase the number of attempts by one. Computer tries to send data again starting the first bit.
    * >Sending the data is finished


# cm-project-wlan2
Project for Comunicações Móveis - DETI UA

## Table of Contents
1. [Access Point Configurations](cisco_ap-conf.ios)
1. [RTS/CTS](#rtscts)
1. [802.11 perfomance (Signal Strenght and Bandwidth)](#80211-perfomance)
1. [Roaming between APs](#roaming-between-aps)

## RTS/CTS

To avoid collisions and preform a congestion control in the network traffic, RTS and CTS are used. These are control frames that request and confirm the possibility to send packets. A threshold can be set to specify the packet size from which the handshake should be done. Depending on that size and the network conditions, the handshake might not be necessary (small packets have less probability to collide).

### Approach

We will use a [WiFi Jammer](https://github.com/DanMcInerney/wifijammer) to flood the network and increase the probability of packet collisions. Then, we will vary the value of the RTS threshold to observe the handshaking mechanism in action, which should reduce the number of dropped packets.

### Setup

To perform this experimentation, we will create a network using an Access Point. We will have two PCs connected, one working as a Server and another as a Client. A third PC will serve as a Monitor, listening to all the communications between the former.

The WiFi Jammer will be running on the Monitor PC.  

![rts_cts.png](diagrams/rts_cts-dark.png#gh-light-mode-only)
![rts_cts-white.png](diagrams/rts_cts-white.png#gh-dark-mode-only)

### Result

## 802.11 perfomance

A network connection may behave differently depending on a number of factors. A way of measuring this connection is by looking at the strength of its signal, and the rate of data transferred through such connection, the bandwidth. These two properties will be affected by several physical factors, such as the distance between the communicating entities, the obstacles between them and the way the Wi-Fi waves are propelled.

### Approach

To evaluate the performance of the IEEE 802.11 (aka Wi-Fi), we will take into consideration the 2 properties under the 4 scenarios mentioned above, for the two most used frequencies bands, 2.4GHz and 5GHz.

To measure the Signal Strength, we will use the mobile application %Mobile APP Name%, which etc...

To measure the Bandwidth, we will use iPerf, which is a tool that allows the setup of a server, and have clients send data to it. This app provides us with how much data was sent each second, for a set number of seconds.

### Setup
To preform this experiment, we will create two VLANs, one for the traffic in the 2.4GHz frequency band, and the other one for the 5GHz. These VLANs will be created in the Access Point, which is directly connected through an Ethernet Cable to the ISP's Router to open the VLANs to the Internet.

We will have 3 devices (2 PCs and 1 Mobile Phone) connecting to the networks through two different SSIDs (one for each VLAN), in order to make the performance tests taking into consideration the two 802.11 frequencies. One of the PCs will act as the Server, and the other devices will be the Clients.

![performance.png](diagrams/performance-dark.png#gh-light-mode-only)
![performance-white.png](diagrams/performance-white.png#gh-dark-mode-only)

### Results

## Roaming between APs

### Approach

### Setup
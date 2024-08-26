# Section 12 WLAN Troubleshooting and Analysis

> Part of the troubleshooting process is trying to understand what is
> happening in the network and nearby that could be causing issues for
> our target network. Nearby access points operating legacy
> technologies, adjacent and co-channel interference, and high number of
> CTS/RTS frames are just a few examples of factors that can all affect
> throughput and capacity. Using a protocol analyzer can help us
> determine causes or at least point us to areas to focus our attention.
> A protocol analyzer can capture raw 802.11 traffic and higher layers
> depending on the mode that the wireless adapter is operating, e.g.
> monitor vs. managed.
>
> Use the packet capture file**, hotel_02.pcapng**, to do some analysis
> of the RF environment from which it was pulled. It includes both raw
> 802.11 traffic and layers 3-7 in some cases. This was accomplished
> with two wireless network cards, on in each of the modes mentioned
> earlier.

1.  Open the Wireless tab at the top in Wireshark and the select WLAN
    Traffic to give you some statistics about the capture file which
    also gives you insight into the network environment.

2.  What are the channels being used for non-broadcast traffic?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

3.  Are there any SSIDs that are “hidden?” If so, what are the MAC
    addresses of the APs and what is the manufacturing vendor?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

4.  What APs and SSIDs are the top 3 talkers?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

5.  Under the Statistics tab at the top, again, determine how many
    conversations occur between IPv4 addresses.
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

6.  What layer 7 protocol is seen the most between the conversations?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

7.  Under Statistics, determine the number and percentage of wireless
    management frames.
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

8.  Use a Wireshark filter and determine the following:

    1.  How many RTS frames are in this capture?
        \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

    2.  How may CTS frames are captured?
        \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

    3.  Why the significant difference and what can this indicate?
        \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
        \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

9.  How many deauthentications occur in this capture and who initiated
    it?


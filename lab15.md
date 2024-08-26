# Section 15 WLAN Surveys

We will be using the Panda wireless cards. It is important to know the
details of the model of the wireless card you will be using for
testing and network evaluations. You may need **sudo**.

1.  Note the model number and MAC address of the wireless card:

Model \#
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

MAC Address:
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

2.  Plug in the wireless card into a USB port. After you plug it in and
    it settles down, open up a terminal window and run **lsusb** to get
    the chipset information. The **lsusb** command list devices that are
    connected to the USB bus. To get a verbose output, try **-vv**.

> **\$ lsusb**:
> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
>
> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

3.  Next, find the driver associated with the wireless card(s) using
    **airmon-ng**.

Displayed as PHY, Interface, Driver, Chipset

**\$ airmon-ng**:
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

> Now that we have an idea about our driver and chipset, visit the
> aircrack-ng website,
> https://www.aircrack-ng.org/doku.php?id=compatibility_drivers and see
> if your wireless adapter is compatible with Linux for wireless
> pentesting and surveys.
>
> Newer versions of the Linux kernel support newer wireless drivers.
> With new kernels and drivers come newer command line configuration
> tools. The command **iwconfig** is being replaced by the newer **iw**
> command. The **iw** command is used to show or manipulate wireless
> devices and their configurations.

4.  Read the detailed information about options and WLANs in the RF
    vicinity.

> **\$ iwlist \<your interface\> scanning**
>
> How many SSIDs are visible?
> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
>
> How many bands/frequencies are available?
> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

5.  Use the **iwlist** command, which is one word and slightly different
    from **iw**, to view the frequencies supported by your wireless
    adapter. Also, find the transmit power.

> **\$ iwlist \<your interface\> frequency**
>
> **\$ iwlist \<your interface\> channel**

**\$ iwlist \<your interface\> txpower**
\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Sometimes **iwlist txpower** needs to be run a few times to get the
output.


### Wireless Card Troubleshooting

Sometimes the wireless cards we use will not get enumerated properly or
there is an issue with popping in and out of monitor and managed mode
that keeps us from seeing the wireless traffic the way we want. Here are
some steps that could be tried to help you out.

```bash
reboot # This seems to help most of the time
su – root
```

Run the following as root:

```bash
iwconfig; ifconfig \# Confirm the cards are visible
airmon-ng check kill
airmon-ng start \<wireless_adapter\> \# Replace with the output from iwconfig
iwconfig; ifconfig \# Confirm the cards are now visible
ip link set \<new_adapter_name\> up
ifconfig \# Confirm it is in an UP state
airodump-ng \<new_adapter_name\> \# Traffic should be visible
ip link set \<new_adapter_name\> down/up \# Turn it off then back on;
```
re-run airodump

##  Wireshark Filters


| Decription                                 | Filter                          |
|--------------------------------------------|---------------------------------|
| Select only frames from a BSSID            | `wlan.bssid == <BSSID>`         |
| Sort by wireless network name              | `wlan.ssid == "Guest"`          |
| Sort on Frame Control Types                | `wlan.fc.type == #`             |
| Sort on Frame Control Subtypes             | `wlan.fc.type_subtype == #`     |
| Management frames                          | `wlan.fc.type == 0`             |
| Control frames                             | `wlan.fc.type == 1`             |
| Data frames                                | `wlan.fc.type == 2`             |
| Association request                        | `wlan.fc.type_subtype == 0`     |
| Association response                       | `wlan.fc.type_subtype == 1`     |
| Reassociation request                      | `wlan.fc.type_subtype == 2`     |
| Reassociation response                     | `wlan.fc.type_subtype == 3`     |
| Probe request                              | `wlan.fc.type_subtype == 4`     |
| Probe response                             | `wlan.fc.type_subtype == 5`     |
| Beacon                                     | `wlan.fc.type_subtype == 8`     |
| Announcement traffic indication map (ATIM) | `wlan.fc.type_subtype == 9`     |
| Disassociate                               | `wlan.fc.type_subtype == 10`    |
| Authentication                             | `wlan.fc.type_subtype == 11`    |
| Deauthentication                           | `wlan.fc.type_subtype == 12`    |
| Action frames                              | `wlan.fc.type_subtype == 13`    |
| Block ACK Request                          | `wlan.fc.type_subtype == 24`    |
| Block ACK                                  | `wlan.fc.type_subtype == 25`    |
| Power-Save Poll                            | `wlan.fc.type_subtype == 26`    |
| Request to Send                            | `wlan.fc.type_subtype == 27`    |
| Clear to Send                              | `wlan.fc.type_subtype == 28`    |
| ACK                                        | `wlan.fc.type_subtype == 29`    |
| Posting of HTTP information                | `http.request.method == "POST"` |

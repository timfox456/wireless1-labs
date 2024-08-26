# Section 5 IEEE Standards

> Before we dive into some more command line, ensure the Panda Wireless
> card is connected.
>
> If using VirtualBox, this is done by selecting from the top menu of
> the running VirtualBox machine: Devices, USB, Ralink 802.11 n WLAN,
> Connect (Disconnect from host). If done correctly, then a check mark
> will appear next to it. To disable, uncheck the box. We need it
> enabled for these labs.

1.  There are multiple copies of oui.txt document on these Linux
    machines. This document has the OUI for each vendor associated with
    a network interface cards—wireless or wired. Find each oui.txt on
    your local Linux box and place a copy of the *largest* one on your
    desktop. The following command will find it, count the number of
    lines in the file and display it to you with a path. The higher the
    line count, the greater the entries that are found in it.

**\$ sudo find / -iname oui.txt -exec wc -l {} \\**

**\$ sudo find / -iname oui.txt \| xargs wc -l**

**\$ sudo find / -iname oui.txt \| xargs ls -l**

What is the absolute path of the original local copy of ieee oui.txt?

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**\$ cp \<path to largest ieee oui.txt\> ~/Desktop/.**

2.  Locate the MAC address(es) of your *virtual* Linux box.

**\$ ifconfig -a**

What is the 48-bit MAC address(es)?

> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

3.  Locate any wireless network adapters and their MAC address. The MAC
    address might be changing dynamically. Your mileage may vary.

**\$ iwconfig**

What is the name and MAC of the wireless adapters

> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

4.  Search through the oui.txt file to locate the manufacturer and
    address of your adapter(s).

> **\$ grep -i ‘yourOUI’ ~/Desktop/oui.txt** \# replace the OUI
>
> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
>
> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

5.  Many networks use a white list of allowed or permitted MAC addresses
    that can associate with a wireless network. It is used in many guest
    hot spots as an authorization method. MAC filters and white lists
    can still be found implement in enterprise networks despite the ease
    of bypassing them. Use **macchanger** and its help to view your
    current/permanent MAC address of your wireless interface. Change
    your wireless interface MAC address to a randomly generated one,
    then back to the permanent one. After each step, verify any changes
    with **ifconfig** command. Try and figure out the usage and do so.
    You will likely have to turn off the wireless interface before
    switching any of the properties if you get a “device busy” error
    message. After you change the MAC, be sure to turn it back on.

```bash
which macchanger
macchanger --help
sudo macchanger \[options\] device
sudo ifconfig \<yourDevice\> down/up
```

6.  What commands did you use to view the current MAC address, change
    it, and revert to the permanent MAC?

> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
>
> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

7.  What was the MAC address of the wireless adapter before, permanent,
    and after?

> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
>
> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

8.  Research where to find and what the timeout is set as for your local
    ARP cache. What is the path of the file you found and what is the
    current value? Hint: 7<sup>th</sup> section man page for arp.

> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

9.  Reboot the physical or virtual machine to revert the MAC address you
    changed. As an alternative, use **macchanger** to set it back to its
    permanent MAC.


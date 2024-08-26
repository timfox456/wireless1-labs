# Section 14 Wireless Attacks, Intrusion, and Policy

> Wi-Fi Protected Setup is a certification given by the Wi-Fi Alliance.
> WPS Certified devices allow for alternative methods of establishing
> WPA/WPA2 Personal security associations setup between wireless
> devices. The WPS alternatives (PIN, PBC, and NFC) contrasted with
> users having to remember or input the 8-63 character Pre-shared keys
> (PSK). WPS eased setup while maintaining the strong encryption
> mechanisms. As with most alternatives and ease-of-use implementations
> in the industry came security vulnerabilities. Methods to brute-force
> the WPS PIN have been demonstrated and often work in the field.
>
> There are a few tools that help us identify access points that allow
> for the use of WPS PINs. We can also view the version of WPS
> mechanisms used, e.g. 1.0. If we can locate APs that allow WPS PINs,
> so can attackers. If they can successfully brute force the WPS
> mechanisms, they will have access to your AP and network resources.
> Let’s look for that offer up WPS in lieu of typing in a Pre-shared
> Key.
>
> Airodump-ng is a tool part of the Aircrack-ng tool suite. Before it
> can be used, we should use a wireless interface in “monitor” mode.
> Monitor mode allows us to dump raw 802.11 frames.
>
> As a good habit, list all network interfaces and wireless adapters so
> that you know what state your system is in.
>
> \$ ifconfig -a
>
> \$ iwconfig
>
> If there is already a listing for a monitor mode wireless interface,
> then jump down to the airodump-ng step below.

Now the environment should be ready for the next section.

1.  Create a monitor mode wireless interface from the command line.

> \$ sudo airmon-ng start wlan0

2.  With a monitor mode interface created, you can use it to dump raw
    802.11 frames, display vendor information, and show WPS information.
    The output of the dump can be saved as well. Use the help to
    understand more options and arguments.

> \$sudo airodump-ng --manufacturer --wps wlan0mon

3.  How many access points in your hearing vicinity, offer WPS as an
    alternative? \_\_\_\_\_\_\_\_\_\_\_\_

4.  By default, airodump-ng runs in the 2.4 GHz channel space. What
    versions of WPS are allowed?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

5.  Additionally, are there options for WPS listed, e.g. (LAB, PBC) and
    what does that mean?

> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
>
> **Section 14 Wireless Attacks, Intrusion, and Policy**
>
> Another tool to show WPS information is “wash.” Use the help for wash
> and run it to display WPS and version information for nearby access
> points.

6.  Does wash show the same number of access points as airodump-ng for
    2.4 GHZ?

> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
>
> With this knowledge, research the vulnerabilities of WPS and be
> prepared to discuss. Along with this research find tools or
> applications that attackers or wireless penetration testers can use to
> defeat the WPS mechanisms.

**Section 14 More on Wireless Attacks, Intrusion, and Policy**

> Wi-Fi Protected Access (WPA) is a security implementation and
> certification prior to the release of the 802.11i standard. WPA has
> two modes, Personal and Enterprise, and uses TKIP/RC4 encryption
> algorithms. WPA2 is a certification that is fully compliant with the
> 802.11i standard. It, too, has two modes, Personal and Enterprise.
> WPA2 uses AES/CCMP encryption algorithms. With either WPA or WPA2
> personal, a Passphrase is used to seed the key derivation functions
> used by the STA and the AP. The Passphrase along with the SSID are
> passed through a key derivation function that outputs a 256-bit
> Pre-shared Key (PSK) which is also known as the Pairwise Master Key
> (PMK). To generate the actual key used to encrypt traffic between the
> STA and the AP, a Pairwise Transient Key (PTK) has to be generated.
> The PTK is used to encrypt the data payload of 802.11 frames. This
> data payload is the layer 3-7 data passed between the STA and the AP.
>
> The generation of the per-session PTK requires four more pieces of
> data: The Authenticator Nonce, Supplicant Nonce, Authenticator MAC,
> and Supplicant MAC. The supplicant is synonymous with the client or
> device. The authenticator is the access point. A Nonce is a random
> number.
>
> It should be clear at this point that we can determine or use tools to
> help find the PTK from the other four pieces of data because the
> function to generate the PTK is not a secret. So how do we get the
> other pieces of data? We capture it in raw 802.11 form. The process to
> exchange the data between the AP and the STA is also known as a
> four-way handshake. Once we have the handshake we can use a cracking
> tool and a dictionary to try the different letter combinations in the
> dictionary in an attempt to find the PTK. The dictionary is only going
> to work if the actual letter combination of the passphrase in in
> there. With this information, we can deduce that the dictionaries may
> be large files.
>
> In the capture file, **belkin_4way.cap**, exists a four-way handshake.
> Aircrack-ng is installed on your Linux workstation. Also bundled with
> Linux are wordlists that serve as dictionaries.

1.  Research and try to crack the passphrase.

2.  What dictionary did you use and how did you find it?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

3.  What is the full path to the dictionary?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

4.  What commands did you use to crack the handshake if you were
    successful?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

5.  How many keys were tested?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

6.  If you are successful, what is the passphrase?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_


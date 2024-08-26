# Section 13 Network Security Architecture

> Legacy security implementations with the original 802.11 standard
> included SSID hiding (also known as cloaking or non-broadcasting), MAC
> filtering, and WEP. Uncovering the hidden SSID is quite trivial. If we
> look at the raw 802.11 frames over any length of time, clients will
> connect to hidden SSIDs and probe for specific SSIDs that may be
> “hidden.” It is also possible to deauthenticate or disassociated a
> connected STAs to force it to reconnect automatically. When it does we
> can see to what SSID it connects back. In short, SSID hiding is really
> not a security mechanism. Still, new access points and wireless
> routers still leave this as an option for the administrator of the
> device.
>
> Use the **belkin_hidden.cap** file to answer the following questions.

1.  What is set as the SSID parameter in frame \#1?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

2.  What is the SSID of the same frame?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

3.  What is the Beacon Interval in seconds?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

4.  How many frames in this capture include the BSSID of the from frame
    \#1? \_\_\_\_\_\_\_\_\_\_\_\_\_

5.  Examine frame \#546. What is the SSID of the AP that is responding
    to the probe request?

> \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

6.  How many times does the AP respond with a probe response?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

7.  What is the MAC address of the STA trying to associate with the AP?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

8.  What is going on starting at frame \#628?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

9.  What is the Association ID assigned to the STA in frame \#622?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

10. What is the purpose of the AID assigned to the station?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_


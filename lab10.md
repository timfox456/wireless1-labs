# Section 10: 802.11 Medium Access

> We’re going to look at the duration field in some 802.11 frames. The
> duration field is used to indicate to stations how long the medium
> will be tied up by the sending client. The duration is the number of
> microseconds to transmit the packet plus the time to receive an
> acknowledgement back.
>
> Open capture **bg_public.cap** file and examine the duration fields in
> packet \#12. This particular frame is a Request-to-Send or RTS. The
> duration field can be found under the section IEEE 802.11, Frame
> Control Field, and the Flags subsection.

1.  What is the duration in microseconds?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

2.  Identify the sender MAC
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

3.  Identify the receiver MAC
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Let’s take a look at the acknowledgements.

> Block acknowledgements are sent after a block unicast frames. A
> station requests a block acknowledgment for the unicast frames. This
> is then followed by the actual block acknowledgment.
>
> Examine the Block Ack in frame \#83 and \#292 of **bg_public.cap**.
> Open up each sub section of the frame and try to identify the Starting
> Sequence Number.

4.  What is the starting sequence number for \#83?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

5.  What is the starting sequence number for \#292?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

> Now, look at Block Acknowledgement Request and an actual Block
> Acknowledgement in response to the request. Examine frames \#467 and
> \#468 in the capture file.

6.  What is the starting sequence number for \#467?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

> Open up frame \#468. And determine if the receiver received all the
> frames.

7.  Were all frames successful?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

> There are different priorities of Quality of Service (QoS). Examine
> frame \#361 and determine the category of QoS.

8.  What is the QoS category?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

> Open up QoS frame in \#478.

9.  What is the QoS category there?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

10. Between 361 and 478, which will have a higher priority?
    \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_


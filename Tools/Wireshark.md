Conversations Option

Lets us see conversations to see the different ips and what they are sending back and forth.

Good to know some of the ip addresses on our network. We would want to learn the MAC addresses of our devices to check that they are connected to the internet.

Wireshark is super powerful but it's like an open world sandbox where we would want to have a specific goal in mind.
Having goals will be a good way to know how we can learn wireshark. 

We can specify what we want to filter
There are a lot of filter options. I dont think this document will be helpful at all but I might as well write something as I watch the video.

Filter option
ip.addr==<ip-address>

Might want to look for http since it's not secure, common to see for hacks.


Helpful filters:

Hide Protocols: !\(arp or stp or lldp or cdp) and can add any other protocols we want to ignore
First part of 3-way handshake: tcp.flags.syn==1
Flagged Packets: tcp.analysis.flags Shows only packets that wireshark wants us to care about
!(arp or stp or lldp or cdp) and http.request.method == "POST"
[malware-traffic-analysis.net] or net not sure, to practice looking at packets.




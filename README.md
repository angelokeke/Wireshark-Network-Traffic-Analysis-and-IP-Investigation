# Wireshark: Network Traffic Analysis and IP Investigation

This project involved capturing and analyzing real network traffic using Wireshark inside a Pop!_OS virtual machine to ensure a safe and isolated testing environment. The goal of the lab was to practice packet capture, protocol filtering, endpoint review, and IP investigation to determine whether observed traffic represented normal behavior or potential security risk. Traffic was collected from my home Wi-Fi network and analyzed across DNS, TLS, and UDP communications, followed by WHOIS lookups to verify IP ownership and legitimacy.

## Lab Environment

- Pop!_OS virtual machine running in Oracle VirtualBox  
- Traffic captured from VM network interface (enp0s3)  
- Wireshark installed and configured for non-root packet capture  
- Capture saved to .pcapng file for analysis  

Running the lab inside a VM ensured the session was isolated from the host system and allowed network analysis without affecting normal device activity.

## Traffic Capture and Protocol Analysis

During the live capture, I observed and analyzed:

- DNS queries  
- NTP background traffic  
- TLS encrypted sessions  

Display filters were applied to narrow the dataset and review protocol-specific behavior.

DNS filtering revealed normal domain lookups to legitimate services such as Mozilla and Google, consistent with expected browsing and application activity.

TLS traffic was reviewed at the metadata level, where activity patterns and destinations appeared normal and showed no suspicious frequency or endpoints.

## Stream and Communication Review

To further examine host interactions, I used:

- Follow UDP Stream  
- Conversation views  
- Source vs destination traffic comparison  

The stream output helped distinguish client requests from server responses and visualize communication flow.

One communication path involved an Akamai CDN endpoint, which was determined to be legitimate activity.

## Endpoint Statistics & IP Investigation

Using Wireshark’s **Statistics → Endpoints** feature, I:

- identified the most active private VM address  
- reviewed the highest-volume public IP  

Private `10.x.x.x` traffic was excluded as internal VM communication.

A public `50.x.x.x` IP was selected for investigation.

WHOIS lookup confirmed the IP belonged to **Comcast Cable Communications (ISP)**.

No malicious indicators were found.

## Findings and Conclusion

After reviewing:

- protocol filters  
- encrypted session metadata  
- UDP streams  
- endpoint statistics  
- WHOIS verification  

The captured traffic was determined to be **normal, safe network activity**.

No suspicious behavior or abnormal traffic patterns were detected.

## Key Skills Strengthened

- Packet capture & filtering  
- Protocol traffic interpretation  
- Endpoint analysis & statistics review  
- IP ownership & reputation validation  
- Network investigation methodology  

This project strengthened my ability to interpret network traffic and approach analysis using a layered, security-focused workflow.

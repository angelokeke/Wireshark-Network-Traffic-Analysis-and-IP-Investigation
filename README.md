# Wireshark: Network Traffic Analysis and IP Investigation
This project involved capturing and analyzing real network traffic using Wireshark inside a Pop!_OS virtual machine to ensure a safe and isolated testing environment. The goal of the lab was to practice packet capture, protocol filtering, endpoint review, and IP investigation to determine whether observed traffic represented normal behavior or potential security risk. Traffic was collected from my home Wi-Fi network and analyzed across DNS, TLS, and UDP communications, followed by WHOIS lookups to verify IP ownership and legitimacy. 

## Lab Environment

-Pop!_OS virtual machine running in Oracle VirtualBox
-Traffic captured from VM network interface (enp0s3)
-Wireshark installed and configured for non-root packet capture
-Capture saved to .pcapng file for analysis

Running the lab inside a VM ensured the session was isolated from the host system and allowed network analysis without affecting normal device activity.

## Traffic Capture and Protocol Analysis

During the live capture, I observed and analyzed:

-DNS queries
-NTP background traffic
-TLS encrypted sessions

Display filters were applied to narrow the dataset and review protocol-specific behavior.

DNS filtering revealed normal domain lookups to legitimate services such as Mozilla and Google, consistent with expected browsing and application activity. TLS traffic was also reviewed at a metadata level, where session patterns and destinations appeared normal and showed no unusual frequency or suspicious endpoints.

## Stream and Communication Review

To further examine host interactions, I used:

-Follow UDP Stream
-Packet conversation views
-Source vs destination traffic review

The red and blue stream output helped distinguish client requests from server responses and visualize communication flow.
One observed connection involved an Akamai content delivery network host. Based on traffic behavior and domain reputation, it was assessed as legitimate activity.

## Endpoint Statistics and IP Investigation
Using Wireshark’s Statistics → Endpoints feature, I reviewed IPv4 activity and identified:

-the most active private IP (VM internal address)
-the highest-volume public IP

The private 10.x.x.x address was excluded since it belonged to the VM.

A public IP beginning with 50.x was selected for investigation.

A WHOIS lookup confirmed the IP belonged to:

-Comcast Cable Communications (Internet Service Provider)

Because the address matched a known and trusted ISP and aligned with expected network behavior, no malicious indicators were identified.

## Findings and Conclusion

After reviewing:
-protocol filters
-encrypted session metadata
-UDP streams
-endpoint statistics
-external IP reputation checks

I concluded that the captured traffic represented normal, safe network activity.
No suspicious domains, anomalous traffic patterns, or malicious endpoint behavior were detected. 

This lab strengthened my ability to:

interpret packet-level data

distinguish normal vs abnormal network behavior

investigate IP addresses using WHOIS

apply a layered analysis approach to network traffic review


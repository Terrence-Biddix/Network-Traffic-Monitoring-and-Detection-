# Network-Traffic-Monitoring-and-Detection-

Capture and Filter Network Traffic in a Linux Environment
Objective

The purpose of this project was to gain hands-on experience capturing and analyzing live network traffic in a Linux environment. Using the tcpdump utility, I learned how to identify network interfaces, capture packets, apply filters, and interpret packet details. This exercise simulated real-world analyst tasks where packet inspection is critical for network monitoring, incident response, and troubleshooting.

Skills Learned

Proficiency in using tcpdump for live traffic capture and analysis.

Ability to identify and analyze properties of network interfaces.

Understanding how to filter traffic by protocol, port, and packet type.

Familiarity with interpreting packet metadata such as source/destination, flags, checksums, and payloads.

Experience saving, reloading, and analyzing .pcap files for forensic review.

Tools Used

Linux Terminal – environment for executing commands.

tcpdump – command-line utility for network packet capture and filtering.

curl – used to generate HTTP traffic for capture.

Steps
Ref 1: Identify Network Interfaces

Command:

sudo ifconfig
sudo tcpdump -D


📷 Screenshot of ifconfig output

Shows available interfaces (eth0, lo).

eth0 identified as the main interface for packet capture.

Ref 2: Inspect Live Traffic with tcpdump

Command:

sudo tcpdump -i eth0 -v -c5


📷 Screenshot of tcpdump capturing 5 packets

Output includes timestamps, IP addresses, protocol, TCP flags, sequence numbers, and checksums.

Demonstrates filtering live traffic directly from the network interface.

Ref 3: Capture Network Traffic to a File

Command:

sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &


📷 Screenshot of tcpdump running in the background and file created

Captured 9 packets of HTTP traffic.

Used curl opensource.google.com to generate web traffic.

Verified that the capture.pcap file was successfully saved.

Ref 4: Filter Captured Packet Data

Command:

sudo tcpdump -nn -r capture.pcap -v


📷 Screenshot of tcpdump reading from capture.pcap (verbose)

Displays details such as source/destination IPs, ports, TCP flags, and packet lengths.

Command:

sudo tcpdump -nn -r capture.pcap -X


📷 Screenshot of tcpdump showing packet data in hex/ASCII format

Provides deeper visibility into packet payloads.

Useful for detecting anomalies, signatures, or malicious content.

Conclusion

This project provided practical experience in capturing and filtering live network traffic using tcpdump. I learned how to:

Identify and monitor active network interfaces.

Capture and analyze packets in real time.

Apply filters to focus on specific protocols and ports.

Save and analyze packet captures offline for forensic investigation.

These skills are directly applicable to roles in network security, incident response, and threat hunting.

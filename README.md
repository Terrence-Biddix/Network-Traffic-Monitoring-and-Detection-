# Network-Traffic-Monitoring-and-Detection-

Capture and Filter Network Traffic in a Linux Environment
## Objective

The purpose of this project was to gain hands-on experience capturing and analyzing live network traffic in a Linux environment. Using the tcpdump utility, I learned how to identify network interfaces, capture packets, apply filters, and interpret packet details. This exercise simulated real-world analyst tasks where packet inspection is critical for network monitoring, incident response, and troubleshooting.

### Skills Learned

- Proficiency in using tcpdump for live traffic capture and analysis.

- Ability to identify and analyze properties of network interfaces.

- Understanding how to filter traffic by protocol, port, and packet type.

- Familiarity with interpreting packet metadata such as source/destination, flags, checksums, and payloads.

- Experience saving, reloading, and analyzing .pcap files for forensic review.

### Tools Used

- Linux Terminal – environment for executing commands.

- tcpdump – command-line utility for network packet capture and filtering.

- curl – used to generate HTTP traffic for capture.

## Steps
#### *Ref 1️⃣: Identify Network Interfaces*

Command:

sudo ifconfig
sudo tcpdump -D


📷 Screenshot of ifconfig output
<img width="783" height="495" alt="Network 1" src="https://github.com/user-attachments/assets/8aae873d-0def-4dd7-9429-b42b63cf635e" />
<img width="768" height="273" alt="Network 2" src="https://github.com/user-attachments/assets/951057a5-aa8f-4a2c-91e4-e576fb6584dd" />



Shows available interfaces (eth0, lo).

eth0 identified as the main interface for packet capture.


#### *Ref 2️⃣: Inspect Live Traffic with tcpdump*

Command:

sudo tcpdump -i eth0 -v -c5


📷 Screenshot of tcpdump capturing 5 packets
<img width="935" height="689" alt="Network 3" src="https://github.com/user-attachments/assets/49c52797-a3fb-438e-b037-c0d4f303b0de" />


Output includes timestamps, IP addresses, protocol, TCP flags, sequence numbers, and checksums.

Demonstrates filtering live traffic directly from the network interface.


#### *Ref 3️⃣: Capture Network Traffic to a File*

Command:

sudo tcpdump -i eth0 -nn -c9 port 80 -w capture.pcap &


📷 Screenshot of tcpdump running in the background and file created
<img width="934" height="145" alt="Network 4" src="https://github.com/user-attachments/assets/e43e5426-97a9-414b-9656-5d25f95163af" />
<img width="865" height="227" alt="Network 5" src="https://github.com/user-attachments/assets/50067edb-1321-466a-bfb7-55c2e8236557" />
<img width="902" height="140" alt="Network 6" src="https://github.com/user-attachments/assets/3fe558ce-0257-4920-bfb9-ac9cd27c6ffd" />



Captured 9 packets of HTTP traffic.

Used curl opensource.google.com to generate web traffic.

Verified that the capture.pcap file was successfully saved.


#### *Ref 4️⃣: Filter Captured Packet Data*

Command:

sudo tcpdump -nn -r capture.pcap -v


📷 Screenshot of tcpdump reading from capture.pcap (verbose)
<img width="930" height="802" alt="Network 7 part 1" src="https://github.com/user-attachments/assets/22e14e07-e98f-43b2-83f6-45b79d96d64b" />
<img width="932" height="794" alt="Network 7 part 2" src="https://github.com/user-attachments/assets/81393209-7c58-466b-927e-3432f13b1f28" />



Displays details such as source/destination IPs, ports, TCP flags, and packet lengths.

#### *Ref 5️⃣: *
Command:

sudo tcpdump -nn -r capture.pcap -X


📷 Screenshot of tcpdump showing packet data in hex/ASCII format
<img width="929" height="802" alt="Network 8 part 1" src="https://github.com/user-attachments/assets/b26f3569-0d45-4299-add6-a76550120739" />
<img width="909" height="826" alt="Network 8 part 2" src="https://github.com/user-attachments/assets/847dc41e-aadc-407f-8305-a49394a6ec32" />
<img width="931" height="836" alt="Network 8 part 3" src="https://github.com/user-attachments/assets/b580761a-f29c-4f31-b8da-ccb2151a3358" />




Provides deeper visibility into packet payloads.

Useful for detecting anomalies, signatures, or malicious content.

## Conclusion

This project provided practical experience in capturing and filtering live network traffic using tcpdump. I learned how to identify and monitor active network interfaces. Capture and analyze packets in real time. Apply filters to focus on specific protocols and ports. Save and analyze packet captures offline for forensic investigation. These skills are directly applicable to roles in network security, incident response, and threat hunting.

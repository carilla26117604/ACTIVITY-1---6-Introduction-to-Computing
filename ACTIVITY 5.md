# Activity No. 5

```text
Republic of the Philippines
                                      Sorsogon State University
                                COLLEGE OF INFORMATION
                            AND COMMUNICATIONS TECHNOLOGY
                                             Bulan Campus
                                          Zone 8, Bulan, Sorsogon
                         Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph



                            CC 101 – Introduction to Computing
        Laboratory Worksheet No. 3 | Week 6: Computer Networks & the Internet (CO4)

     “Know Your Network Settings”: Exploring Windows 11 Network
                        Configuration Tools
Name: Francine L. Carilla                             Block: BSCS 1 - 1


 Computer Unit Used (Desktop/Laptop, brand): Laptop Date: 10/20/2026



    I. Objectives


At the end of this activity, you should be able to:
 • Locate network adapter information using Windows 11 Settings, the Control Panel,
    Command Prompt (CMD), and PowerShell.
 • Use ipconfig, getmac, hostname, ping, netstat, route print, and systeminfo in CMD, and
    GetNetAdapter, Get-NetIPAddress, and Test-Connection in PowerShell.
 • Interpret a sample ipconfig /all output from a networked computer: identify its IP address,
    subnet mask, default gateway, and DNS servers, and classify the address as public or
    private.
 • Relate each tool and finding to the layer of the OSI model where it works.
 • Design a simple network and IP address plan for the computer laboratory.

    II. Materials Needed


 • A computer running Windows 11 (a network or Internet connection is not required for this
    activity)
 • This worksheet (printed copy, or the digital file to fill out and submit)
 • Week 6 lecture notes, for reference on IP addresses, protocols, the OSI model, and network
    devices


    III. Background


A computer does not need to be connected to a network to have network settings. Every PC has
one or more network adapters (NICs), each with a permanent MAC address, and Windows always
runs the TCP/IP software, including the loopback address 127.0.0.1 (IPv4) and ::1 (IPv6) that the
computer uses to talk to itself. Windows 11 lets you inspect these settings in four places: the Settings
app, the classic Control Panel, Command Prompt (CMD), and PowerShell. In this activity, you will
explore all four on your own unit, observe how Windows behaves when no network is available,
and then analyze a sample configuration taken from a computer that is connected to a network.


    IV. Procedure


Reminder: This is a viewing activity. Do not change, disable, or reset any network setting. Close
every dialog with Cancel. Record values exactly as Windows shows them.
                                         Republic of the Philippines
                                        Sorsogon State University
                                  COLLEGE OF INFORMATION
                              AND COMMUNICATIONS TECHNOLOGY
                                               Bulan Campus
                                            Zone 8, Bulan, Sorsogon
                           Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph


Part A – Windows 11 Settings
 1. Press Windows + I to open Settings, then click Network & internet. Write down the
    connection status shown at the top of the page (for example, “Not connected”).

 2. Click Advanced network settings. Under Network adapters, note every adapter listed (for
    example, Ethernet, Wi-Fi, Bluetooth Network Connection) and whether each one is enabled
       or disconnected.
 3. Scroll down and click Hardware and connection properties. For each adapter, record its
    Name, Description, Physical address (MAC), and Status in Table 1.

Part B – Control Panel (Network Connections)
 4. Press Windows + R, type ncpa.cpl, and press Enter. This opens the classic Network
    Connections window. A red X on an icon means the adapter has no network connection.
 5. Right-click your Ethernet adapter and choose Properties. List the items checked under “This
    connection uses the following items” in Table 2.

 6. Select Internet Protocol Version 4 (TCP/IPv4) and click Properties. Record whether the
    computer is set to Obtain an IP address automatically (DHCP) or Use the following IP
    address (static), and the same for DNS. Click Cancel, then Cancel again. Do not change
    anything.

Part C – Command Prompt (CMD)
 7. Press the Windows key, type cmd, and press Enter. Run each command below, one at a
       time, and record the results in Table 3.
         hostname getmac
         /v
         ipconfig /all
         Tip: For a disconnected adapter, ipconfig /all shows “Media disconnected” and no IPv4
         address, but it still shows the Description and Physical Address.

 8. Test the computer’s own TCP/IP software using the loopback address. Record whether you
       got replies and the time. For ping localhost, note the address that replied. ping 127.0.0.1
       ping localhost
 9. Now observe what happens when there is no network. Record the exact message each
       command displays. ping 8.8.8.8
 nslookup google.com

 10.View the ports your computer is listening on and its routing table. In Table 3, record three
       LISTENING local addresses with their port numbers, and the Netmask shown for the Network
       Destination 127.0.0.0. netstat -an | findstr LISTENING route print -4

 11.Run the command below. It may take a few seconds. Scroll to Network Card(s) and
       record how many network cards are installed and the status of each. systeminfo

Part D – PowerShell
 12.     Right-click the Start button and choose Terminal (or press the Windows key, type
       PowerShell, and press Enter). Run each command below and record the results in Table 4.
         Get-NetAdapter
         Get-NetIPAddress -AddressFamily IPv4 | Format-Table InterfaceAlias, IPAddress,
         PrefixLength
         Test-Connection 127.0.0.1 -Count 4
                                             Republic of the Philippines
                                            Sorsogon State University
                                     COLLEGE OF INFORMATION
                                 AND COMMUNICATIONS TECHNOLOGY
                                                   Bulan Campus
                                                Zone 8, Bulan, Sorsogon
                               Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph


         Get-NetTCPConnection -State Listen | Select-Object -First 5 LocalAddress, LocalPort

         Tip: PowerShell commands follow a Verb-Noun pattern (Get-NetAdapter = “get the network
         adapters”). Compare each result with the matching CMD command from Part C.

Part E – Analyze a Networked Computer
 13.     The output below was taken from a laboratory computer that is connected to a
       network. Study it, then complete Table 5.
Sample Output 1. ipconfig /all (excerpt) from a networked PC
    Host Name . . . :                         CICT-LAB-PC07
    Ethernet adapter Ethernet:
    Description . . . :                       Realtek PCIe GbE Family Controller
    Physical Address . . . :                  3C-52-82-A1-7F-09
    DHCP Enabled . . . :                      Yes
    Link-local IPv6 Address . . . :           fe80::8c2d:4a1f:93b2:61e5%12(Preferred)
    IPv4 Address . . . :                      192.168.10.37(Preferred)
    Subnet Mask . . . :                       255.255.255.0
    Lease Obtained . . . :                    Wednesday, October 14, 2026 8:02:15 AM
    Lease Expires . . . :                     Thursday, October 15, 2026 8:02:15 AM
    Default Gateway . . . :                   192.168.10.1
    DHCP Server . . . :                       192.168.10.1
    DNS Servers . . . :                       192.168.10.1, 8.8.8.8

Part F – Design a Network for Our Laboratory
 14.Our laboratory does not yet have a network. In the box after Table 5, draw a simple star
       topology network for it. Include at least four PCs, one switch, one router (default gateway),
       one printer, and the ISP / Internet. Use lines to show connections.

 15.Assign each device a private IPv4 address from the network 192.168.10.0/24, using
       192.168.10.1 for the router. Label each device in your drawing and complete the IP Address
       Plan (Table 6).

Part G – Optional / Bonus
 16.       In CMD, run type C:\Windows\System32\drivers\etc\hosts to view (not edit) the hosts
       file. In one or two sentences, explain what this file is for and how it relates to DNS.


    V. Data and Findings


Table 1. Network Adapters in Settings (Part A)
Connection status shown on the Network & internet page: Connected, secured

 Bluetooth Network
 ConnectionAdapt           Description                          Physical Address (MAC)     Status
 er Name


 Local Area                Microsoft Wi-Fi Direct Virtual
                                                                 b2:6b:11:e4:00:f8         Not operational
 Connection* 1             Adapter


 Local Area                Microsoft Wi-Fi Direct Virtual
                                                                 b2:6b:11:e4:10:e8         Not Operational
 Connection* 2             Adapter #2
                                        Republic of the Philippines
                                       Sorsogon State University
                               COLLEGE OF INFORMATION
                           AND COMMUNICATIONS TECHNOLOGY
                                             Bulan Campus
                                          Zone 8, Bulan, Sorsogon
                         Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph




                       MediaTek Wi-Fi 6 MT7920
  Wi-Fi                                                    b0:6b:11:e4:20:d8            Operational
                       Wireless LAN Card

                       ASIX AX88179 USB 3.0 to
 Ethernet                                                 f8:e4:3b:34:2b:2c             Not Present
                       Gigabit Ethernet Adapter

 Bluetooth Network
 ConnectionAdapt       Description                        Physical Address (MAC)        Status
 er Name


 Bluetooth Network     Bluetooth Device (Personal
                                                          b0:6b:11:e4:20:d9             Not operational
 Connection            Area Network)



Table 2. Adapter Properties (Part B)

 Items Checked Under “This connection uses
 the following items”                                  Item Checked (continued)


 Client for Microsoft Networks                         Microsoft LLDP Protocol Driver

 File and Printer Sharing for Microsoft Networks       Internet Protocol Version 6 (TCP/IPv6)


 QoS Packet Scheduler                                  Link-Layer Topology Discovery Responder

                                                       Link-Layer Topology Discovery Mapper I/O
  Internet Protocol Version 4 (TCP/IPv4)
                                                       Driver




 TCP/IPv4 Setting                                      Automatic or Static?


 IP address                                            Automatic


 DNS server address                                    Automatic



Table 3. Command Prompt Results (Part C)

 Command / Item                Your Findings                                            OSI Layer


                                                                                         Application
 hostname                        LAPTOP-AJH1QRFA
                                                                                        (7)

                                 B0-6B-11-E4-20-D8
 getmac /v: MAC address
                                                                                         Data Link (2)
 and Transport Name            \Device\Tcpip_{BD87F45E-2CB4-406E-
                               A0F39ECBB6BC6AD1}

 ipconfig /all: Media State
                                 Media Disconnected                                     —
 of Ethernet
                                          Republic of the Philippines
                                         Sorsogon State University
                                 COLLEGE OF INFORMATION
                             AND COMMUNICATIONS TECHNOLOGY
                                               Bulan Campus
                                            Zone 8, Bulan, Sorsogon
                           Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph




 ipconfig /all: DHCP
                                 Yes                                                   —
 Enabled

                                 Reply from 127.0.0.1: bytes=32 time<1ms
 ping 127.0.0.1: replies and
                                 TTL=128 (4 replies, 0% loss)                           Network (3)
 time


 ping localhost: address
                                 ::1                                                   —
 that replied

 ping 8.8.8.8: exact
                                 Reply from 8.8.8.8: bytes=32 time=37ms TTL=115         Network (3)
 message

 Command / Item                  Your Findings                                         OSI Layer


                                 Server: dev.opt
                                 Address: 192.168.1.1
 nslookup google.com:            Non-authoritative answer:                              Application
 exact message                   Name: google.com                                      (7)
                                 Addresses: 2404:6800:4017:806: : 200e
                                           172.217.26.78

 netstat -an: three
 LISTENING                       0.0.0.0:135, 0.0.0.0:445, 0.0.0.0:49664                Transport (4)
 addresses:ports

 route print -4: Netmask
                                 255.0.0.0                                             —
 for 127.0.0.0

                                 1
                                 [01] MediaTek Wi-Fi 6 MT7920 Wireless LAN Card
 systeminfo: number          of (Wi-Fi)
                                                                                       —
 NICs and status                 DHCP Enabled: Yes
                                 IP address 192.168.1.108




Table 4. PowerShell Results (Part D)

                                                                                       Matches CMD?
 Command                               What It Showed                                  (Y/N)


                                       Wi-Fi
 Get-NetAdapter: Name,
                                       Up
 Status, MacAddress,                                                                   Y
                                       B0-6B-11-E4-20-D8
 LinkSpeed
                                       300 Mbps
                                      Republic of the Philippines
                                     Sorsogon State University
                               COLLEGE OF INFORMATION
                           AND COMMUNICATIONS TECHNOLOGY
                                            Bulan Campus
                                         Zone 8, Bulan, Sorsogon
                        Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph




                                  Wi-Fi: 192.168.1.108
                                  (PrefixLength 24); Loopback Pseudo-
                                 Interface 1: 127.0.0.1 (PrefixLength 8)
 Get-NetIPAddress: IPv4
                                  Local Area Connection* 1: 169.254.68.249          Y
 addresses and PrefixLength
                                 (16)
                                  Local Area Connection* 2: 169.254.145.228
                                 (16)

 Test-Connection 127.0.0.1:
                                  4 successful replies from 127.0.0.1               Y
 result

 Get-NetTCPConnection -
 State Listen: two               :: : 49669
                                                                                    Y
 LocalAddress:LocalPort          0.0.0.0:135
 pairs



Table 5. Sample Output Analysis (Part E)

 Question                               Your Answer


 IPv4 address of PC07                    192.168.10.37


 Subnet mask (and its /prefix)           255.255.255.0(/24)

 Question                               Your Answer


 Default gateway, and what
                                         192.168.10.1; usually a router
 device it usually is

 DNS servers                             192.168.10.1and 8.8.8.8

 Was the address assigned by
                                         Assigned by DHCP because “DHCP Enabled” is set to
 DHCP or set manually? How do
                                        “Yes”
 you know?

 Public or private? Which RFC 1918      Private IP address; it belongs to the 192.168.0.0–
 range?                                 192.168.255.255 range.

 IPv4 address of PC07 in binary (four
                                         11000000.10101000.00001010.00100101
 octets)

 MAC address, and the OSI layer
                                        3C-52-82-A1-7F-09; Data Link Layer (Layer 2)
 where it is used

                                        24 hours — obtained Oct 14, 2026 8:02:15 AM; expires
 How long is the DHCP lease?
                                        Oct 15, 2026 8:02:15 AM

 If the DHCP server failed, what
                                        An APIPA address in the 169.254.0.0/16 range if it cannot
 kind of address would PC07 assign
                                        obtain an IPv4 address from DHCP.
 itself?
              Republic of the Philippines
             Sorsogon State University
      COLLEGE OF INFORMATION
  AND COMMUNICATIONS TECHNOLOGY
                    Bulan Campus
                 Zone 8, Bulan, Sorsogon
Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph
                                       Republic of the Philippines
                                      Sorsogon State University
                                COLLEGE OF INFORMATION
                            AND COMMUNICATIONS TECHNOLOGY
                                             Bulan Campus
                                          Zone 8, Bulan, Sorsogon
                         Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph


Figure 1. Proposed Laboratory Network Diagram (Part F)




Table 6. IP Address Plan (Part F)

 Device                        IPv4 Address                  Subnet Mask             Default Gateway


 Router (gateway)              192.168.10.1                  255.255.255.0           —


 PC 1                          192.168.10.2                   255.255.255.0          192.168.10.1


 PC 2                          192.168.10.3                   255.255.255.0          192.168.10.1


 PC 3                          192.168.10.4                   255.255.255.0          192.168.10.1


 PC 4                          192.168.10.5                   255.255.255.0          192.168.10.1


 Printer                       192.168.10.6                   255.255.255.0          192.168.10.1
                                      Republic of the Philippines
                                     Sorsogon State University
                              COLLEGE OF INFORMATION
                          AND COMMUNICATIONS TECHNOLOGY
                                            Bulan Campus
                                         Zone 8, Bulan, Sorsogon
                        Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph




Part G Notes (Optional / Bonus)

 The hosts file is a text file that maps specific hostnames to IP addresses on a
 computer.




    VI. Realization (Reflection)


In two to four sentences each, answer the following in your own words.

1.    Even without a network connection, what network information did your computer still
have? Why do you think it still has it?

  My computer still had network adapter information like its MAC address and
 loopback IP address. And these are available because the Windows maintains
 network settings even when the computer is not connected to any network.

2.      Compare Settings, Control Panel, CMD, and PowerShell. Which tool did you find most
useful for viewing network information, and why?

  Settings and Control Panel gives a graphical way to view network settings, while CMD
 and Powershell makes commands to display detailed information. I found CMD the
 most useful because commands such as ipconfig /all can show important network
 information in one place.

3.     What did the messages from ping 8.8.8.8 and nslookup google.com tell you? How would
you use messages like these when troubleshooting a real network?

  The message from these commands helped me understand whether my computer
 could reach an external IP address and resolve a domain name. I would use these
 commands to identify possible network or DNS problems when troubleshooting an
 internet connection.

4.     Why should you be careful about sharing your MAC address, IP address, or ipconfig /all
screenshots online? Relate your answer to data privacy.

 I should be careful when sharing network information online because it may reveal
 details about my computer and network configuration. Protecting this information
 helps maintain my privacy and reduces the risk of misuse by others.


    VII. Scoring Guide


 Criteria                    Description                                            Points


 Completeness                All tables (1–6) and required fields are filled out.   25
                                      Republic of the Philippines
                                     Sorsogon State University
                               COLLEGE OF INFORMATION
                           AND COMMUNICATIONS TECHNOLOGY
                                            Bulan Campus
                                         Zone 8, Bulan, Sorsogon
                        Tel. No.; 056 311 -0103; Email Address: cict@sorsu.edu.ph




                             Recorded values match what the tools show
                             and are consistent across Settings, CMD, and
Accuracy                                                                              30
                             PowerShell; sample analysis, binary conversion,
                             and OSI layers are correct.

Criteria                     Description                                              Points


                             Diagram shows a star topology with PCs, switch,
Network Design               router, printer, and ISP; IP plan uses valid, non-       15
                             duplicate addresses in 192.168.10.0/24.


                             Answers are thoughtful, based on the student’s
Realization / Reflection                                                              20
                             own results, and well written.

                             Worksheet    is  legible/well-formatted            and
Neatness & Timeliness                                                                 10
                             submitted on time.


Total                                                                                 100
```

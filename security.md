# Security

## Detect threat in computer level
Tools for detecting threats and log monitoring
* Microsoft Sysinternals Sysmon
* Custom Event Tracing for Windows Sensor
* Hostflows
* Windows Event Logs
* Microsoft Sysinternals Autoruns

Tools for forwarding logs
* **Filebeat**: Tails and ships log files
* **Heartbeat**: Ping remote services for availability
* **Metricbeat**: Fetches sets of metrics from the operating system and services
* **Packetbeat**: Monitors the network and applications by sniffing packets
* **Winlogbeat**: Fetches and ships Windows Event logs

## Vulnerability search databases
* http://hackerstorm.co.uk/
* https://cve.mitre.org/
* http://secunia.com/community/advisories/
* https://exploithub.com/
* https://www.us-cert.gov/ncas/alerts

## Windows *tcpdump*
`pktmon` (very useful `--help`)
### Basics
* `pktmon start --etw -l real-time` start capturing and show results in terminal.
* `pktmon filter add 'name' -i 'ip' -t 'protocol'` add filter for capturing packets.
* `pktmon filter remove` remove al filters.

## 10 Indicators of attack (IoA’s)
1. Internal hosts communicating with known bad destinations or to a foreign country where you don’t conduct business.
2. Internal hosts communicating to external hosts using non-standard ports or protocol/port mismatches, such as sending command shells (SSH) rather than HTTP, HTTPS traffic over port 80,443, the default web port.
3. Publically servers or demilitarized zone (DMZ) hosts communicating to internal hosts. This allows leapfrogging from the outside to the inside and back, permitting data exfiltration and remote access to assets such as RDP(Remote Desktop Protocol), Radmin, SSH.
4. Alerts that occur outside standard business operating hours (at night or on weekends) could signal a compromised host.
5. Network scans by internal hosts communicating with multiple hosts in a short time frame, which could reveal an attacker moving laterally within the network. 
6. Multiple alarm events from a single host or duplicate events across multiple machines in the same subnet over a 24-hour period, such as repeated authentication failures.
7. After Infected host is cleaned, a system is reinfected with malware within 5-10 minutes, repeated reinfections signal the presence of a rootkit or persistent compromise. This incident may detect from Endpoint Security Protection or Anti Virus events.
8. Multiple Login from different regions
9. Internal hosts use much SMTP
10. Internal hosts many queries to External/Internal DNS

## Information gather
* Memory [`winpmem`](https://github.com/Velocidex/WinPmem) example use:
    * `winpmem_v3.3.rc3.exe --formate raw --output memory.dmp`
* Network processes  `netstat` example use:
    * `netstat -anb`
* [`LastActivityView`]()
* Information about specific process [`PrcView`](https://www.majorgeeks.com/files/details/process_viewer_for_windows_(prcview).html)
* [`sysinternals`](https://docs.microsoft.com/en-us/sysinternals/downloads/) varius tools for varius listings
* [`sigcheck`](https://download.sysinternals.com/files/Sigcheck.zip) to check digital signatures of executables
    * `sigcheck -v -s -c c:\`
* [`listmodules`](https://blog.didierstevens.com/my-software/#ListModules) portable executable analysis tool

## Windows PowerShell commands
* `dir` List direcotries (`ls`)
* `whoami` who is current user
* `systeminfo` System Info
* `tasklist /V` list of running processes
* `tasklist /M` list of loaded dlls
* `netstat -ano` list of active network connections
* `ipconfig /displaydns` display DNS cache
* `arp -a` ARP table
* `net user` display users
* `wmic` ???
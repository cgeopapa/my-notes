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
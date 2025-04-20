# Task 7: Monitor System Resources Using Netdata

## Objective
Visualize system and app performance metrics using Netdata in Docker.

## Netdata Dashboard
![Netdata Dashboard]
<img width="1470" alt="netdata-dashboard" src="https://github.com/user-attachments/assets/4706ff31-7a21-47a2-9a3f-f67afeb28fff" />

## Access URL
http://localhost:19999

## Key Features Observed
- CPU usage
- Memory consumption
- Disk I/O
- Docker container stats

## Command Used to Run Netdata
```bash
docker run -d --name=netdata -p 19999:19999 --cap-add=SYS_PTRACE \
  -v netdataconfig:/etc/netdata \
  -v netdatalib:/var/lib/netdata \
  -v netdatacache:/var/cache/netdata \
  -v /etc/passwd:/host/etc/passwd:ro \
  -v /etc/group:/host/etc/group:ro \
  -v /proc:/host/proc:ro \
  -v /sys:/host/sys:ro \
  -v /etc/os-release:/host/etc/os-release:ro \
  netdata/netdata




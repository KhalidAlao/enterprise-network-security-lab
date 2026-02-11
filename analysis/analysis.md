## Test Objective
Validate that the firewall blocks unauthorized WAN traffic
while allowing approved services.

## Method
Attack traffic was generated from a Kali Linux VM.
Firewall logs and packet captures were collected.

## Results
- Unauthorized traffic was dropped
- Drops were logged with timestamps
- No sessions established

## Conclusion
The firewall enforces least-privilege access and provides
clear visibility into hostile traffic.

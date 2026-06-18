# Findings

## Detection Summary

A review of authentication logs identified multiple failed login attempts originating from the same IP address and targeting the same user account.

## Observations

* Username: user1
* Source IP: 192.168.1.100
* Failed Login Attempts: 5
* Successful Login Attempts: 1

## Analysis

The logs indicate repeated authentication failures followed by a successful login. This pattern is commonly associated with brute force attacks where an attacker attempts multiple password combinations until access is obtained.

## Security Impact

* Unauthorized account access
* Credential compromise
* Potential lateral movement
* Increased security risk

## MITRE ATT&CK Mapping

Technique: T1110 - Brute Force

## Risk Level

Medium to High

## Conclusion

The activity observed in the logs is consistent with a brute force attack. The source IP generated multiple failed login attempts before successfully authenticating to the target account.

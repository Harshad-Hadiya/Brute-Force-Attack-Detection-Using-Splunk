# Brute Force Attack Detection Using Splunk

## Overview

This project demonstrates the detection and investigation of a brute force attack using Splunk. Authentication logs were analyzed to identify repeated failed login attempts from a single IP address targeting the same user account.

## Project Objectives

* Import authentication logs into Splunk
* Detect brute force activity using SPL queries
* Analyze failed login attempts
* Identify suspicious authentication patterns
* Document findings and recommendations

## Tools Used

* Splunk Enterprise
* SPL (Search Processing Language)
* Windows Authentication Logs
* GitHub

## Detection Logic

The following SPL query was used to identify excessive failed login attempts:

```spl
index=main EventCode=4625
| stats count by Username Source_IP
| where count > 3
```

## Investigation Results

* Multiple failed login attempts detected
* Single source IP involved
* Successful login observed after repeated failures
* Potential brute force attack identified

## MITRE ATT&CK Mapping

| Technique ID | Technique   |
| ------------ | ----------- |
| T1110        | Brute Force |


## Skills Demonstrated

* Log Analysis
* Splunk Search & Reporting
* Security Monitoring
* Threat Detection
* Incident Investigation
* Cybersecurity Documentation

## Recommendations

* Enable MFA
* Implement account lockout policies
* Monitor failed login thresholds
* Investigate suspicious source IPs
* Strengthen password security

## Conclusion

This project demonstrates how Splunk can be used to identify brute force attacks through authentication log analysis. The investigation highlights the importance of proactive monitoring and rapid detection of suspicious login activity.

---

### Author

Harshad Hadiya

Aspiring SOC Analyst | Cybersecurity Enthusiast

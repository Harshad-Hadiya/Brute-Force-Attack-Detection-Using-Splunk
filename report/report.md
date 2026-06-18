\# Brute Force Attack Detection Using Splunk



\## Objective



The objective of this project is to detect brute force login attempts using Splunk and analyze authentication logs for suspicious activity.



\## Data Source



Sample Windows Authentication Logs



\## Investigation Process



\### Step 1: Log Collection



Authentication logs were imported into Splunk using a CSV data source.



\### Step 2: Log Analysis



Failed login attempts were analyzed using Splunk Search Processing Language (SPL).



\### Detection Query



```spl

index=main EventCode=4625

| stats count by Username Source\_IP

| where count > 3

```



\### Results



The query identified multiple failed login attempts from a single source IP address.



\### Additional Analysis



```spl

index=main (EventCode=4624 OR EventCode=4625)

| stats count by Username EventCode

```



This query was used to compare successful and failed authentication attempts.



\## Findings



\* Multiple failed logins detected

\* Same source IP repeatedly targeted one account

\* Successful login observed after failures

\* Activity matches brute force attack behavior



\## Threat Assessment



Attack Type: Brute Force Attack



Severity: Medium to High



MITRE ATT\&CK: T1110 - Brute Force



\## Recommendations



\* Enable Multi-Factor Authentication (MFA)

\* Configure account lockout policies

\* Monitor excessive failed login attempts

\* Block suspicious IP addresses

\* Implement strong password policies



\## Conclusion



The investigation successfully detected indicators of a brute force attack using Splunk. Repeated failed authentication attempts followed by a successful login suggest a potential account compromise attempt requiring further monitoring and response.




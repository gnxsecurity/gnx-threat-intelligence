<img src="https://gnxsecurity.com/gnx-logo.jpg" alt="drawing" width="150"/>

***

### About
gnX threat intelligence feed contains a blacklist of IP addresses that have crossed a threshold indicating malicious intent.  The list is updated every half an hour. 

### Source
gnX runs a micro server farm in multiple locations consisting of a variety of honey pot solutions, often built in house, which monitor for the following types of events:

- Multiple connections to uncommon publicly exposed server ports, indicating scan activity.
- Brute force login attempts against common services such as SSH, API, Basic Auth, etc.
- Injection attempts against web applications, databases and API endpoints.
- Vulnerability scans and attacks using common/known software through signature identification.

### Recorded data
gnX records and generates a signifcant amount of data about each potential attacker including:

- IP Address / DNS with reverse lookup/arin/whois data generated in real time.
- Attack signatures, strings, injection parameters for later utilization in our honey pots.
- Anonymously check for open ports and responses on the attackers end to identify C&C/malicious software.
- Aggregate data from other public threat sources to enrich the recorded data.

### Criteria
Before an IP addresses is comitted to the list, it must have met the following criteria:

- Observed making at least five malicious attempts against a single honey pot system over the course of one hour.
- Observed making at least one malicious attempts against three separate honey pot servers over the course of one hour.
- Observed making at least fifteen attempts against a single or multiple servers over the course of 12 hours.

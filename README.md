<img src="https://gnxsecurity.com/gnx-logo.jpg" alt="drawing" width="150"/>

***

# About
gnX threat intelligence feed contains a blacklist of IP addresses that have crossed a threshold indicating malicious intent and/or potential IOC [indicator of compromise] activity.  Because of the criteria standards and threat list sanitiation process, we significantly reduce the potential of false positives.  Can be used as a standalone blocklist or to agument your existing threat intelligence.

The list is updated every 30 minutes for rapid threat blocking. 

### Formats
The following formats are available:

1. latest-blacklist.raw:  one IP address per-line [standard format]
2. latest-blacklist.sc:  semi-colon separated list of IP addresses for some firewalls (e.g Fortinet).
3. latest-blacklist.csv:  comma separated list of IP addresses.
4. latest-blacklist.cdb:  CDB format list for OSSEC/Wazuh integration
5. latest-blacklist.crit:  Most critical of threats that significantly exceed the criteria standards below.
6. latest-blacklist.low:  All threats including low severity, may contain false positives, use with caution.

### Source
gnX runs a micro server farm in multiple locations consisting of a variety of honey pot solutions, often built in house, which monitor for the following types of events:

- Multiple connections to uncommon publicly exposed server ports, indicating scan activity.
- Brute force login attempts against common services such as SSH, API, Basic Auth, etc.
- Injection attempts against web applications, databases and API endpoints.
- Vulnerability scans and attacks using common/known software through signature identification.

### Criteria
Before an IP addresses is comitted to the list, it must have met the following criteria:

- Observed making at least five malicious attempts against a single honey pot system over the course of one hour.
- Observed making at least one malicious attempts against three separate honey pot servers over the course of one hour.
- Observed making at least fifteen attempts against a single or multiple servers over the course of 12 hours.

### Sanitiation
A notable amount of effort is put into reducing the possibility of false positives, including:

- Whitelists are leveraged to ensure popular web properties aren't accidentily listed.
- Any internal IP addressing (BOGONS) are removed.
- Reverse lookups are performed to gather data points which help determine whether an item should be removed.
- Addresses are routinely removed when they no longer pose a threat (e.g being shut down by ISP/Hosting provider)

### Recorded data
gnX records and generates a signifcant amount of data about each potential attacker including:

- IP Address / DNS with reverse lookup/arin/whois data generated in real time.
- Attack signatures, strings, injection parameters for later utilization in our honey pots.
- Anonymously check for open ports and responses on the attackers end to identify C&C/malicious software.

# Coding Challenge - PCAP

Please reach out to us with any questions:
contact@chameleoncg.com

![CCG Image](chameleon_color_600_dropshadow.png)

## Background

We have been running an EC2 instance for several minutes with no firewalls or security groups blocking traffic. Luckily, we have a PCAP (included [here](./capture.pcap)) of the traffic!

We would like a tool that will parse through the PCAP and determine if we should be concerned about anything specific. We know that scanning happens on all publicly reachable servers, and have decided we can safely ignore those.

## Task

We have found out we can use https://greynoise.io/ to get more information about IPs in the PCAP. In particular the information detailed here: https://developer.greynoise.io/reference#ip-lookup-1

Write a tool that generates a report to help us analyze the data. Submit the code back to us at contact@chameleoncg.com as a tar/zip or URL to a GitHub repository.

#### Task Details

You may use the following API key for greynoise.io (note it expires on Dec 25, 2020).
fEpyQknDfGAZo59MXNJF4Hjv7s8QLlhJcEhlae5a8XLnLhNAH4acpU90pbD7fjGy

We are interested in the following data in the report

* Unique source IPs
* Number of Unique IPs grouped by country & organization (according to greynoise)
* List of Malicious/Unknown IPs (according to the greynoise classification)

For example:

```sh
Unique IPs: 6

IP Details:
US/Digital Ocean: 5
US/AWS: 9

Concerning IPs:
1.2.3.4
5.6.7.8
```

### Hints

If using python, scapy is a great tool for reading PCAP files:
https://scapy.readthedocs.io/en/latest/usage.html#reading-pcap-files

If using python, requests library is an easy tool for doing REST calls
https://requests.readthedocs.io/en/master/
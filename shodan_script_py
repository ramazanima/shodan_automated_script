import shodan

# replace YOUR_API_KEY with your Shodan API key
API_KEY = "IaqOrMM0NR2nG2CcVSTFot2Dc0kDl78M"


# list of hosts to look up
hosts = ["20.251.28.200"]

# create a Shodan API object
api = shodan.Shodan(API_KEY)

# loop over the list of hosts and retrieve information for each one
for host in hosts:
    try:
        # retrieve information for the current host
        result = api.host(host)

        # print out the information retrieved for the current host
        print("IP: {}".format(result['ip_str']))
        print("Hostnames: {}".format(result.get('hostnames', 'N/A')))
        print("OS: {}".format(result.get('os', 'N/A')))
        print("Organization: {}".format(result.get('org', 'N/A')))
        print("Ports: {}".format(result['ports']))
        print("Vulnerabilities: {}".format(result.get('vulns', 'N/A')))
        print("=" * 50)

        num_cves = len(result.get('vulns', []))

        # print out the information retrieved for the current host

        print("CVE Count: {}".format(num_cves))
        print("=" * 50)
    except shodan.APIError as e:
        print("Error: {}".format(e))



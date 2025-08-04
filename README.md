# Port-Analysis---nmap

I just scanned my local network using the TCP SYN scan (-sS) along with service version detection (-sV) on the subnet 10.61.114.0/24.

The scan revealed that most hosts had no open TCP ports, which is expected for client devices or hardened systems.

However, a few hosts had open ports, which could indicate services running that may be vulnerable if not properly secured.




------Potential Risks-----------

1. Port 53 (tcp) — Service: dnsmasq 2.51
(This is a DNS service)

The version 2.51 is very outdated and known to have several vulnerabilities, including:

Remote Code Execution (RCE)

DNS cache poisoning

Denial of Service (DoS)

If accessible to untrusted devices, it can be exploited to disrupt DNS resolution or inject malicious responses.

2. Port 7070 (tcp) — Service: ssl/realserver?
(This port is commonly used for streaming or custom SSL applications)

Since the service couldn’t be identified clearly, it could be a custom or legacy service with poor security.

If SSL is misconfigured (e.g., using weak ciphers), it may allow data interception or downgrade attacks.

Unknown services should be audited to ensure they don’t expose sensitive interfaces or unpatched software.



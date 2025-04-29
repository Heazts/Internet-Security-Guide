# Network Security: VPNs, Secure DNS, and Tor

Your internet connection is the bridge between your device and the online world. Protecting this connection is vital to prevent your Internet Service Provider (ISP), network administrators (on public Wi-Fi, work, or school networks), or even malicious actors from spying on your activity, blocking your access, or intercepting your data. This section covers three key technologies for network security: VPNs, Secure DNS, and the Tor network.

## VPNs (Virtual Private Networks)

A VPN creates an encrypted "tunnel" between your device and a server operated by the VPN provider. All your internet traffic passes through this tunnel, hiding your activity from your local ISP and changing your public IP address to that of the VPN server.

**What a VPN DOES:**

*   **Encrypts your traffic:** Prevents your ISP or local network administrators from seeing the websites you visit or the content of your traffic (except for the fact that you are connected to a VPN).
*   **Masks your IP address:** Websites and services you access will see the IP address of the VPN server, not your real IP. This helps bypass geographic restrictions and makes IP-based tracking more difficult.
*   **Protects on public Wi-Fi:** Encrypts your connection on untrusted networks (cafes, airports), protecting against local snooping.

**What a VPN DOES NOT DO (Common Myths):**

*   **Does not guarantee total anonymity:** Your VPN provider *can* see your activity if they keep logs. You are transferring trust from your ISP to the VPN provider. Additionally, VPNs do not protect against tracking via cookies, browser fingerprinting, or logging into accounts.
*   **Does not protect against malware or phishing:** A VPN won't prevent you from downloading malicious files or entering your credentials on fake websites.
*   **Does not necessarily increase speed:** Although it can bypass ISP throttling, the encryption and additional routing can sometimes slow down the connection.

**Criteria for Choosing a Trustworthy VPN:**

Choosing a VPN provider is crucial, as you are entrusting them with your data.

*   **Logging Policy (Audited No-Logs):** The VPN must have a clear policy of *not* logging your online activity (sites visited, timestamps, IPs). Ideally, this policy should be verified by independent third-party audits.
*   **Jurisdiction:** The legal location of the VPN company matters. Countries with data retention laws or those part of surveillance alliances (like the 5/9/14 Eyes) may pose a higher risk.
*   **Strong Encryption Protocols:** Must offer modern and secure protocols like OpenVPN and WireGuard. Avoid outdated protocols like PPTP.
*   **Kill Switch:** An essential feature that blocks all internet traffic if the VPN connection drops unexpectedly, preventing your real IP from being exposed.
*   **Leak Protection (DNS, WebRTC, IPv6):** The VPN must ensure that your DNS, real IP address (via WebRTC), or IPv6 traffic does not leak outside the VPN tunnel.
*   **Payment and Privacy Model:** Providers that accept anonymous payments (cryptocurrencies, cash) and require minimal registration information are preferable.
*   **Open Source (Plus):** Open-source VPN clients allow for greater community scrutiny.
*   **Reputation and Transparency:** Research the company, its history, and the transparency of its operations.

**Examples of Well-Regarded Providers (Based on Trusted Sources like Privacy Guides):**

*   **ProtonVPN:**
    *   **Pros:** Based in Switzerland (strong privacy laws), audited no-logs policy, open source, strong focus on security, offers a limited free plan.
    *   **Cons:** Paid plans can be slightly more expensive.
    *   [![ProtonVPN](https://img.shields.io/badge/VPN-ProtonVPN-6D4AFF?style=for-the-badge&logo=protonvpn&logoColor=white)](https://protonvpn.com/)
*   **Mullvad:**
    *   **Pros:** Based in Sweden, strict audited no-logs policy, accepts anonymous payments (cash, crypto), requires no email for registration (uses random account numbers), solely focused on VPN, open source.
    *   **Cons:** Fewer servers than some competitors.
    *   [![Mullvad](https://img.shields.io/badge/VPN-Mullvad-008174?style=for-the-badge&logo=mullvad&logoColor=white)](https://mullvad.net/en)
*   **IVPN:**
    *   **Pros:** Based in Gibraltar, audited no-logs policy, open source, accepts anonymous payments, strong commitment to transparency.
    *   **Cons:** Interface might be less intuitive for beginners.
    *   [![IVPN](https://img.shields.io/badge/VPN-IVPN-00938A?style=for-the-badge)](https://www.ivpn.net/)

**Risks and Limitations of VPNs:**

*   **Trust in the Provider:** The biggest risk is choosing an untrustworthy provider that keeps logs or has weak security.
*   **Free VPNs:** Be wary of free VPNs. They often make money by selling your data, showing ads, or having inadequate security.
*   **False Sense of Security:** Remember that VPNs do not solve all privacy problems (cookies, fingerprinting, etc.).

## Secure and Private DNS (DoH/DoT)

The DNS (Domain Name System) is like the phonebook of the internet. When you type an address like `www.example.com`, your device queries a DNS server to get the corresponding IP address. Traditionally, these queries are made in plain text (unencrypted), allowing your ISP or anyone on the network to see which sites you are trying to access.

**Privacy Issues with Standard DNS:**

*   **Snooping:** Your ISP can log every website you visit.
*   **Censorship/Blocking:** ISPs or governments can block access to certain sites at the DNS level.
*   **Manipulation:** Malicious DNS servers can redirect you to fake websites (phishing).

**Secure DNS Technologies:**

*   **DNS over HTTPS (DoH):** Encapsulates DNS queries within normal HTTPS traffic (port 443). This makes them indistinguishable from regular web traffic, hindering blocking and snooping.
*   **DNS over TLS (DoT):** Uses a dedicated TLS connection (port 853) to encrypt DNS queries. It's easier for firewalls to block but is a dedicated standard for secure DNS.

**Recommended DNS Providers (Privacy Focus):**

*   **Quad9:**
    *   **Pros:** Security-focused, blocks known malicious domains, operated by a Swiss non-profit, strong privacy policy (does not log IPs).
    *   **Cons:** May mistakenly block some legitimate sites (rare).
    *   **Addresses (DoH):** `https://dns.quad9.net/dns-query`
    *   **Addresses (DoT):** `dns.quad9.net`
    *   [![Quad9](https://img.shields.io/badge/DNS-Quad9-2F2E60?style=for-the-badge)](https://www.quad9.net/)
*   **NextDNS:**
    *   **Pros:** Highly configurable, allows creating custom profiles with blocklists (ads, trackers, malware), offers analytics (with privacy options), generous free plan.
    *   **Cons:** Requires account creation for advanced configuration, logs are kept (but can be disabled or limited).
    *   **Addresses (DoH/DoT):** Customized per account.
    *   [![NextDNS](https://img.shields.io/badge/DNS-NextDNS-1E88E5?style=for-the-badge)](https://nextdns.io/)
*   **Cloudflare DNS:**
    *   **Pros:** Fast, widely available, promises not to sell data and delete logs after 24h (audited).
    *   **Cons:** Cloudflare is a large internet infrastructure company, raising concerns about data centralization for some users.
    *   **Addresses (DoH):** `https://cloudflare-dns.com/dns-query`
    *   **Addresses (DoT):** `1dot1dot1dot1.cloudflare-dns.com`
    *   [![Cloudflare DNS](https://img.shields.io/badge/DNS-Cloudflare-F38020?style=for-the-badge&logo=cloudflare)](https://1.1.1.1/)

**How to Configure Secure DNS:**

Configuration can be done at different levels:

*   **In the Browser:** Many browsers (Firefox, Brave, Chrome, Edge) support DoH natively. Look for "Secure DNS" or "DNS over HTTPS" in privacy/security settings.
*   **In the Operating System:**
    *   **Windows 11:** Native support for DoH.
    *   **macOS Ventura+:** Native support for DoH/DoT.
    *   **Linux:** Requires manual configuration or additional software (like `systemd-resolved`).
    *   **Android 9+:** Native support for DoT ("Private DNS").
    *   **iOS 14+:** Native support for DoH/DoT via configuration profiles or apps.
*   **On the Router:** Some routers allow configuring DoH/DoT for the entire home network.

Configuring at the OS or router level protects all traffic from the device/network, while browser configuration only protects traffic from that browser.

## Tor (The Onion Router)

Tor is a decentralized, volunteer-operated network that allows for more anonymous internet browsing. It works by routing your traffic through a series of three random servers (nodes), encrypting it in layers (like an onion) at each hop.

**How It Works:**

1.  **Entry Node (Guard Node):** Knows your real IP, but not the final destination.
2.  **Middle Node:** Receives traffic from the entry node and sends it to the exit node. Knows neither your IP nor the final destination.
3.  **Exit Node:** Sends your traffic to the final destination on the internet. Knows the destination, but not your real IP. The destination website sees the IP of the exit node.

**Use Cases:**

*   **Anonymity:** Makes it very difficult for websites to track your real location or for your ISP to see what you are accessing.
*   **Circumventing Censorship:** Allows access to sites blocked in your region.
*   **Protection Against Surveillance:** Used by journalists, activists, and citizens in oppressive regimes.

**Tor Browser:**

The easiest and safest way to use the Tor network is through the **Tor Browser**, a modified version of Firefox pre-configured to route all traffic through the Tor network and include additional protections against fingerprinting.

*   **Instructions:** Download from the official website [torproject.org](https://www.torproject.org/). Do not install additional extensions, as they can compromise anonymity.
*   **Limitations:** Browsing can be slower due to the additional routing. Some websites may block access from known Tor exit node IPs or present CAPTCHAs more frequently.
*   [![Tor Browser](https://img.shields.io/badge/Browser-Tor%20Browser-7D4698?style=for-the-badge&logo=torproject)](https://www.torproject.org/)

**Risks of the Tor Network:**

*   **Malicious Exit Nodes:** Anyone can run an exit node. Malicious nodes might try to spy on unencrypted traffic (HTTP) or inject malware. **Always use HTTPS when browsing through Tor.**
*   **Timing Attacks:** Adversaries controlling both entry and exit nodes (or monitoring traffic to/from them) could theoretically correlate traffic timing to try and de-anonymize users (difficult, but possible for powerful adversaries).
*   **Browser Compromise:** Vulnerabilities in the Tor Browser itself (though rare) could expose the user.

**Tor vs VPN:**

| Feature             | VPN                                  | Tor                                      |
| :------------------ | :----------------------------------- | :--------------------------------------- |
| **Main Goal**       | Privacy from ISP/Local Network       | Anonymity from Websites/Surveillance     |
| **Trust**           | Trust in the VPN provider            | Trust in the decentralized network (design)|
| **Routing**         | Single point (VPN Server)            | Multiple hops (3 random nodes)           |
| **Speed**           | Generally faster                     | Generally slower                         |
| **Exit IP**         | Fixed (VPN server's IP)              | Variable (random exit node's IP)         |
| **Blocking**        | Less likely to be blocked            | More likely to be blocked by sites       |
| **Cost**            | Usually paid                         | Free                                     |

**Using VPN with Tor?** It's possible (VPN -> Tor or Tor -> VPN), but generally not recommended for most users as it adds complexity and potential new points of failure without a clear anonymity benefit in most scenarios. Tor Browser by itself provides a good level of anonymity for most needs.

By combining the careful use of VPNs, secure DNS configuration, and, when necessary, the Tor network, you can significantly strengthen the security and privacy of your internet connection.


If you care about your online privacy, it's time to stop using your ISP's DNS servers. You don't have to self-host a DNS server if you don't want to, but take a little time to research an external DNS provider that uses encrypted methods, and switch to that on all your devices. Every little piece of data you can claw back from your ISP and other data hogs is worth the effort.

## The problem with your ISP's DNS

### Okay, problems, plural, because they're not your friend

- ![TP-Link Archer AXE75 tri-band on a bench](https://static0.xdaimages.com/wordpress/wp-content/uploads/wm/2023/07/tp-link-archer-axe75-wi-fi-6e-router.jpg?q=49&fit=contain&w=750&h=422&dpr=2)

- ![TP-Link Archer AXE75 tri-band on a bench](https://static0.xdaimages.com/wordpress/wp-content/uploads/wm/2023/07/tp-link-archer-axe75-wi-fi-6e-router.jpg?q=49&fit=contain&w=5333&h=4000&dpr=2)
    
- ![ASUS ZenWiFi Wi-Fi router](https://static0.xdaimages.com/wordpress/wp-content/uploads/wm/2023/07/asus-zenwifi-et8-router-amazon.jpg?q=49&fit=contain&w=4371&h=3278&dpr=2)
    
- ![ISP router showing connection lights](https://static0.xdaimages.com/wordpress/wp-content/uploads/wm/2024/05/isp-router-gateway-service-lights.jpeg?q=49&fit=contain&w=4032&h=3024&dpr=2)
    
- ![Old fiber router with phone, ethernet, and an ONT](https://static0.xdaimages.com/wordpress/wp-content/uploads/wm/2024/05/old-fiber-router-ethernet.jpeg?q=49&fit=contain&w=1280&h=960&dpr=2)
    
- ![Xfinity XFi internet gateway and app controls](https://static0.xdaimages.com/wordpress/wp-content/uploads/2024/03/xfinity-internet-gateway-app-controls.jpg?q=49&fit=contain&w=2200&h=1238&dpr=2)
    
    Source: [Comcast](https://corporate.comcast.com/)
    

There are many reasons you'd [not want your ISP resolving your DNS queries](https://www.xda-developers.com/dns-blocking-is-double-edged-sword/), but most of them boil down to one thing — privacy. [ISPs are lousy at this](https://www.xda-developers.com/how-isp-internet-know-using-vpn/), whether it's not [enabling DNSSEC](https://www.xda-developers.com/pi-hole-tweaks-made-difference/) to ensure DNS responses are authentic and untampered with, or bundling your browsing habits into nice packages to sell to advertisers as supposedly anonymous data. In a world where all data is for sale, sending out unencrypted DNS records is another way for you and your habits to be tracked.

By moving to another DNS provider, you sidestep any ISP-level blocks. It doesn't guaranteed your new DNS provider doesn't have its own blocks, but these are generally more forthcoming about what and why they're blocking certain content, and it's mostly for the user's benefit and safety.

## You don't have to self-host DNS

### Many of the commercial alternatives are safe and secure

   ![Cloudflare 1.1.1.1 DNS app on Android](https://static0.xdaimages.com/wordpress/wp-content/uploads/wm/2024/06/cloudflare-dns-app-android.jpeg?q=49&fit=crop&w=825&dpr=2)

There are plenty of [private DNS providers](https://www.xda-developers.com/use-private-dns-everywhere-you-can/) worldwide to get encrypted DNS set up with the minimum of fuss. You don't have to self-host anything to use these options; instead you change the DNS server on every device you want to use it on, from your router to smartphones and more. That gives your devices better security, circumvents any ISP-level blocks to DNS resolution, and helps you stay more private when online.

While encrypted DNS will keep your ISP from seeing your DNS queries, it's not going to keep your browsing private. You'll need a VPN or other securely encrypted method of accessing the internet for that.

You'll want to make sure the DNS provider you choose supports **DNSSEC**, **QNAME Minimization**, and also either **disable or anonymize EDNS Client Subnet (ECS)** if it's available. Also, you don't want it to **log personal data to disk**, and it should support **anycast** or **geo-steering**.

In no particular order, each of these DNS providers will be more secure and private than your ISP's:

These should all also support various encrypted options, including DNS-over-HTTPS, DNS-over-TLS, or DNS-over-Quic. And with how often [DNS goes wrong](https://www.xda-developers.com/it-really-was-dns/), it's always a good idea to use a trusted DNS solution for the best and most secure option.

## But self-hosting gives you more control

### You get ad-blocking, locally resolved domains, and more

[Self-hosting a DNS server](https://www.xda-developers.com/reasons-host-your-own-dns-server-home/) is deceptively simple to do these days, whether you choose from [any of the options](https://www.xda-developers.com/dns-servers-you-can-self-host/), including [Unbound](https://www.xda-developers.com/reasons-run-dns-server-unbound/), [AdGuard Home](https://www.xda-developers.com/adguard-home-self-hosting-dns-server/), [PowerDNS](https://www.xda-developers.com/isps-use-this-dns-resolver/), or my personal favorite, [Technitium](https://www.xda-developers.com/technitium-best-local-dns-tool/). You'll still want to have some queries sent to an external DNS server in an encrypted manner for fallback, but having your own local DNS server making its own encrypted requests will increase the security and privacy of your home network and the devices using that DNS server.

### Whatever you choose, it's time to stop using your ISP's DNS servers

Using the DNS servers your ISP defaults to might be easy, but it's [not good for your online privacy](https://www.xda-developers.com/online-tools-digital-privacy-security/). Plus, your DNS data is likely being sold for advertising use, along with any other data that the ISP can sniff. Using an encrypted DNS provider means your ISP is cut out of the loop, so while it doesn't make your browsing private, it does reduce the exposure of your online usage. And it's not just your browsing habits, because your location can be triangulated with DNS queries, and that's possibly more worrisome.
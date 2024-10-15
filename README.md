# 1.1.1.1 (DNS Resolver)
Speed up your online experience with Cloudflare’s public DNS resolver.

## 1.1.1.1 (DNS Resolver) IP addresses

Consider the tables below to know which IPv4 or IPv6 addresses are used by the different Cloudflare DNS resolver offerings.

For detailed guidance refer to Set up.

1.1.1.1 is Cloudflare’s public DNS resolver. It offers a fast and private way to browse the Internet.

| IPv4	| IPv6 |
|-------|------|
|1.1.1.1|2606:4700:4700::1111|
|1.0.0.1|2606:4700:4700::1001|

Refer to Encryption to learn how to use 1.1.1.1 in an encrypted way.

## 1.1.1.1 for Families
1.1.1.1 for Families categorizes destinations on the Internet based on the potential threat they pose regarding malware, phishing, or other types of security risks.

For more information, refer to 1.1.1.1 for Families set up.

### Block malware
|IPv4 | IPv6 |
|-------|----|
|1.1.1.2|2606:4700:4700::1112|
|1.0.0.2|2606:4700:4700::1002|

### Block malware and adult content
|IPv4 | IPv6 |
|-------|----|
|1.1.1.3|2606:4700:4700::1113|
|1.0.0.3|2606:4700:4700::1003|

[DNS Resolver Setup](https://github.com/readloud/Cloudflare-WARP/blob/main/DNS%20Resolver%20Setup.md)

[DNS in Google Sheets](https://github.com/readloud/Cloudflare-WARP/blob/main/DNS%20in%20Google%20Sheets.md)

[DNS over Discord](https://github.com/readloud/Cloudflare-WARP/blob/main/DNS%20over%20Discord.md)

[DNS over Tor](https://github.com/readloud/Cloudflare-WARP/blob/main/DNS%20over%20Tor.md)

## Cloudflare WARP - Debian [has been disable]
The supported releases are:

    Bookworm (12)
    Bullseye (11)
    Buster (10)
    Stretch (9)

Add cloudflare gpg key

```
    curl -fsSL https://pkg.cloudflareclient.com/pubkey.gpg | sudo gpg --yes --dearmor --output /usr/share/keyrings/cloudflare-warp-archive-keyring.gpg
```

Add this repo to your apt repositories
```
    echo "deb [signed-by=/usr/share/keyrings/cloudflare-warp-archive-keyring.gpg] https://pkg.cloudflareclient.com/ $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/cloudflare-client.list
```
Install
```
    sudo apt-get update && sudo apt-get install cloudflare-warp
```

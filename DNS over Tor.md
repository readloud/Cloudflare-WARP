# DNS over Tor

*Warning*

The hidden resolver is still an experimental service and should not be used in production or for other critical uses.

If you do not want to disclose your IP address to the resolver, you can use our Tor onion service. Resolving DNS queries through the Tor network guarantees a significantly higher level of anonymity than making the requests directly. Not only does doing so prevent the resolver from ever seeing your IP address, but it also prevents your ISP from knowing that you attempted to resolve a domain name.

## Setting up a Tor client
The important difference between using all other modes of DNS and this one is that packet routing no longer uses IP addresses, and therefore all connections must be routed through a Tor client.

Before you start, head to the Tor Project website ↗ to download and install a Tor client. If you use the Tor Browser, it will automatically start a `SOCKS proxy ↗ at 127.0.0.1:9150`.

If you use Tor from the command line, create the following configuration file:

`SOCKSPort 9150`

Then you can run tor with:

Terminal window
```
tor -f tor.conf
```
Also, if you use the Tor Browser, you can head to the resolver’s address to see the usual 1.1.1.1 page:

`https://dns4torpnlfs2ifuz2s2yf3fc7rdmsbhm6rw75euj35pac6ap25zgqad.onion/`

*Note*

The HTTPS certificate indicator should say “Cloudflare, Inc. (US).”

If you ever forget 1.1.1.1’s address, use cURL to retrieve it:

Terminal window
```
curl -sI https://tor.cloudflare-dns.com | grep -i alt-svc
```

## Setting up a local DNS proxy using socat
Of course, not all DNS clients support connecting to the Tor client, so the easiest way to connect any DNS-speaking software to the hidden resolver is by forwarding ports locally, for instance using socat ↗.

## DNS over TCP, TLS, and HTTPS
The hidden resolver is set up to listen on TCP ports `53` and `853` for DNS over TCP and TLS. After setting up a Tor proxy, run the following socat command as a privileged user, replacing the port number appropriately:

Terminal window
```
PORT=853; socat TCP4-LISTEN:${PORT},reuseaddr,fork SOCKS4A:127.0.0.1:dns4torpnlfs2ifuz2s2yf3fc7rdmsbhm6rw75euj35pac6ap25zgqad.onion:${PORT},socksport=9150
```

From here, you can follow the regular guide for setting up `1.1.1.1`, except you should always use `127.0.0.1` instead of `1.1.1.1`. If you need to access the proxy from another device, simply replace `127.0.0.1` in `socat commands` with your local IP address.

## DNS over HTTPS
As explained in the blog post ↗, our favorite way of using the hidden resolver is using DNS over HTTPS (DoH). To set it up:

Download cloudflared by following the guide for connecting to 1.1.1.1 using DNS over HTTPS clients.

Start a Tor SOCKS proxy and use socat to forward port TCP:443 to localhost:

Terminal window
```
socat TCP4-LISTEN:443,reuseaddr,fork SOCKS4A:127.0.0.1:dns4torpnlfs2ifuz2s2yf3fc7rdmsbhm6rw75euj35pac6ap25zgqad.onion:443,socksport=9150
```
Instruct your machine to treat the .onion address as localhost:
Terminal window
```
cat << EOF >> /etc/hosts
127.0.0.1 dns4torpnlfs2ifuz2s2yf3fc7rdmsbhm6rw75euj35pac6ap25zgqad.onion
EOF
```
Finally, start a local DNS over UDP daemon:

Terminal window
```
cloudflared proxy-dns --upstream "https://dns4torpnlfs2ifuz2s2yf3fc7rdmsbhm6rw75euj35pac6ap25zgqad.onion/dns-query"

cloudflared proxy-dns --upstream "https://dns4torpnlfs2ifuz2s2yf3fc7rdmsbhm6rw75euj
INFO[0000] Adding DNS upstream url="https://dns4torpnlfs2
INFO[0000] Starting DNS over HTTPS proxy server addr="dns://localhost:53"
INFO[0000] Starting metrics server addr="127.0.0.1:35659"
```

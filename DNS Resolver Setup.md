##Set up Linux

Before you begin, take note of any DNS addresses you might have set up, and save them in a safe place in case you need to use them later.

Consider the sections below to set up 1.1.1.1 using either the command line interface (CLI) or a graphical user interface (GUI) of your preference.

###Use command line interface (CLI)
Choose whether you want to use 1.1.1.1 or 1.1.1.1 For Families, and replace 1.1.1.1 with the corresponding IPv4 or IPv6 address accordingly.

`resolv.conf`

Usually, `/etc/resolv.conf` is where you can configure the resolver IPs that your system is using.

In that case, you can use the following one-line command to specify 1.1.1.1 as your DNS resolver and 1.0.0.1 as backup:

Terminal window
```
echo -e "nameserver 1.1.1.1\nnameserver 1.0.0.1" | sudo tee /etc/resolv.conf
```
* Warning

Note that other systems, such as dynamic host configuration protocol (DHCP), may automatically write to `/etc/resolv.conf` and change that configuration. In those cases, consider changing your network settings or DHCP to use 1.1.1.1.

Alternatively, you can use an editor (nano or vim, for example) to manually edit the file.

`systemd-resolved`
If you use systemd-resolved utility and the resolver IPs configuration is in /etc/systemd/resolved.conf, consider the steps below:

Run the following command, replacing `<EDITOR>` with your preferred editor.

Terminal window
```
sudo <EDITOR> /etc/systemd/resolved.conf
```
In the editor, add or edit the following lines:
```
[Resolve]
DNS=1.1.1.1
```
###Use graphical user interface (GUI)

* GNOME
Go to Show `Applications > Settings > Network`.

Select the `adapter` you want to configure — like your Ethernet adapter or Wi-Fi card — and select the `Settings` button.

On the `IPv4 tab > DNS section, disable the Automatic toggle`.

Depending on what you want to configure, choose one of the following DNS addresses for IPv4:

###Use 1.1.1.1 resolver

Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Go to IPv6.

Depending on what you want to configure, choose one of the following DNS addresses for IPv6:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Select `Apply`.

* KDE Plasma
Go to `System Settings > Wi-Fi & Internet > Wi-Fi & Networking`. (or Connections, if on Plasma 5)
Select the `connection` you want to configure - like your current connected network.
On the `IPv4 tab`, select the `Method drop-down menu > Automatic` (Only addresses).
Select the `text box next to DNS servers`.

Depending on what you want to configure, choose one of the following DNS addresses for IPv4:

###Use 1.1.1.1 resolver

Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families

On the `IPv6 tab`, select the `Method drop-down menu > Automatic` (Only addresses).
Select the text box next to DNS servers.

Depending on what you want to configure, choose one of the following DNS addresses for IPv6:

###Use 1.1.1.1 resolver

Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Select `Apply`.

* Note

Setting up a static IP address to configure a DNS server may prevent you from connecting to some public Wi-Fi networks that use captive portals — these are the web pages some wireless networks employ to let users log in and use their services.

If you are experiencing connectivity issues related to captive portals:

Remove the static IP addresses from the device or disable the 1.1.1.1 app.
Connect to the Wi-Fi network.
Once the connection has been established, re-add the static IP addresses or enable the 1.1.1.1 app.

##Set up Router

Go to the IP address used to access your router’s admin console in your browser.

Linksys and Asus routers typically use http://192.168.1.1 or http://router.asus.com (for ASUS).
Netgear routers typically use http://192.168.1.1 or http://routerlogin.net.
D-Link routers typically use http://192.168.0.1.
Ubiquiti routers typically use http://unifi.ubnt.com.

Enter the router credentials. For consumer routers, the default credentials for the admin console are often found under or behind the device.

In the admin console, find the place where `DNS settings are set`. This may be contained within categories such as `WAN and IPv6 (Asus Routers) or Internet (Netgear Routers)`. Consult your router’s documentation for details.

Take note of any DNS addresses that are currently set and save them in a safe place in case you need to use them later.

Depending on what you want to configure, choose one of the following DNS addresses for IPv4:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Depending on what you want to configure, choose one of the following DNS addresses for IPv6:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Save the updated settings.

###Using DNS-Over-TLS on OpenWrt
It is possible to encrypt DNS traffic out from your router using DNS-over-TLS if it is running OpenWrt. For more details, see our blog post on the topic: Adding DNS-Over-TLS support to OpenWrt (LEDE) with Unbound ↗.

###FRITZ!Box
Starting with FRITZ!OS 7.20 ↗, DNS over TLS is supported, see Configuring different DNS servers in the FRITZ!Box ↗.

Set up Windows

* Windows 10
Take note of any DNS addresses you might have set up, and save them in a safe place in case you need to use them later.

Select the `Start menu > Settings`.
On `Network and Internet`, select Change `Adapter Options`.
Right-click on the `Ethernet` or `Wi-Fi` network you are connected to and select Properties.
Choose `Internet Protocol Version 4`.
`Select Properties > Use the following DNS server addresses`.

Depending on what you want to configure, choose one of the following DNS addresses for IPv4:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Select OK.
Go to Internet Protocol Version 6.
Select Properties > Use the following DNS server addresses.
Depending on what you want to configure, choose one of the following DNS addresses for IPv6:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Select OK.

* Windows 11
Take note of any DNS addresses you might have set up, and save them in a safe place in case you need to use them later.

Select the `Start menu > Settings`.
On `Network and Internet`, choose the adapter you want to `configure - like your Ethernet adapter or Wi-Fi card`.
Scroll to `DNS server assignment` and select Edit.
Select the `Automatic (DHCP)` drop-down menu > Manual.
Select the `IPv4` toggle to turn it on.
Depending on what you want to configure, choose one of the following DNS addresses for IPv4:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Select the IPv6 toggle.
Depending on what you want to configure, choose one of the following DNS addresses for IPv6:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Select Save.
Note

Setting up a static IP address to configure a DNS server may prevent you from connecting to some public Wi-Fi networks that use captive portals — these are the web pages some wireless networks employ to let users log in and use their services.

If you are experiencing connectivity issues related to captive portals:

Remove the static IP addresses from the device or disable the 1.1.1.1 app.
Connect to the Wi-Fi network.
Once the connection has been established, re-add the static IP addresses or enable the 1.1.1.1 app.

* Encrypt your DNS queries
1.1.1.1 supports DNS over TLS (DoT) and DNS over HTTPS (DoH), two standards developed for encrypting plaintext DNS traffic. This prevents untrustworthy entities from interpreting and manipulating your queries. For more information on how to encrypt your DNS queries, please refer to the Encrypted DNS documentation.

##Set up macOS

Take note of any DNS addresses you might have set up, and save them in a safe place in case you need to use them later.

Go to `System Settings`. You can find it by pressing `Command + Space` on your keyboard and typing `System Settings`.
Go to `Network`.
Select a `network service`.
Select Details.
Go to `DNS`.
Under `DNS Servers`, select `Add`.
Depending on what you want to configure, choose one of the following DNS addresses for IPv4:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Depending on what you want to configure, choose one of the following DNS addresses for IPv6:

###Use 1.1.1.1 resolver
Block malware with 1.1.1.1 for Families
Block malware and adult content with 1.1.1.1 for Families
Select OK.

* Note
Setting up a static IP address to configure a DNS server may prevent you from connecting to some public Wi-Fi networks that use captive portals — these are the web pages some wireless networks employ to let users log in and use their services.

If you are experiencing connectivity issues related to captive portals:

Remove the static IP addresses from the device or disable the 1.1.1.1 app.
Connect to the Wi-Fi network.
Once the connection has been established, re-add the static IP addresses or enable the 1.1.1.1 app.

* Encrypt your DNS queries
1.1.1.1 supports DNS over TLS (DoT) and DNS over HTTPS (DoH), two standards developed for encrypting plaintext DNS traffic. This prevents untrustworthy entities from interpreting and manipulating your queries. For more information on how to encrypt your DNS queries, please refer to the Encrypted DNS documentation.

##Set up Gaming consoles

###Gaming consoles PS4
Go to `Settings > Network > Set Up Internet Connection`.
Select `Wi-Fi or LAN` depending on your Internet connection.
Select `Custom`.
Set `IP Address Settings` to `Automatic`.
Change DHCP Host Name to Do Not Specify.
Set `DNS Settings` to `Manual`.

Change Primary DNS and Secondary DNS to:
`1.1.1.1`
`1.0.0.1`

If you are able to add more DNS servers, you can add the IPv6 addresses as well:
`2606:4700:4700::1111`
`2606:4700:4700::1001`

Set`MTU Settings` to `Automatic`.
Set `Proxy Server` to `Do Not Use`.

###Gaming consoles Xbox One
Open the `Network screen` by pressing the `Xbox button` on your controller.
Go to `Settings > Network > Network Settings`.
Next, go to `Advanced Settings > DNS Settings`.
Select `Manual`.
Set `Primary DNS` and Secondary DNS to:
`1.1.1.1`
`1.0.0.1`

If you have the option to add more DNS servers, you can add the IPv6 addresses as well:
`2606:4700:4700::1111`
`2606:4700:4700::1001`

When you are done, you will be shown a confirmation screen. Press B to save.

###Gaming consoles Nintendo
The following instructions work on `New Nintendo 3DS`, `New Nintendo 3DS XL`, `New Nintendo 2DS XL`, `Nintendo 3DS`, `Nintendo 3DS XL`, and `Nintendo 2DS`.

Go to the `home menu` and `choose System Settings` (the wrench icon).
Select `Internet Settings > Connection Settings`.
Select your `Internet connection` and then select `Change Settings`.
Select `Change DNS`.
Set `Auto-Obtain DNS` to `No`.
Select `Detailed Setup`.
Set `Primary DNS` and `Secondary DNS` to:
`1.1.1.1`
`1.0.0.1`

If you are able to add more `DNS servers`, you can add the IPv6 addresses as well:
`2606:4700:4700::1111`
`2606:4700:4700::1001`

Select Save > OK.

###Gaming consoles Nintendo Switch
Press the `home button` and select `System Settings`.
Scroll down and `select Internet > Internet Settings`.
Select your `Internet connection` and then select `Change Settings`.
Select `DNS Settings` > `Manual`.
Set `Primary DNS` and `Secondary DNS` to:
`1.1.1.1`
`1.0.0.1`

Select Save > OK.

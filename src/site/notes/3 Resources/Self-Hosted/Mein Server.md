---
{"dg-publish":true,"permalink":"/3-resources/self-hosted/mein-server/","created":"2024-07-28T22:41:21.654+02:00","updated":"2024-07-28T23:04:22.950+02:00"}
---


I host a few services for myself and my family. These include a chat server based on Prosody and a Nextcloud.
All services are running with Docker on a J4105 SoC mainboard, which i ordered 2018. I use Unraid as a management tool for these containers, which has served me well since the beginning of 2024. Previously, I was running Baremetal Ubuntu, which regularly led to update problems. To hide my IP, I use the free features of Cloudflare. Since July 2024, I've been using their Cloudflared tunnel so that I can easily activate new subdomains using the Nginx proxy manager, making it even easier to add new services to my ecosystem. With the help of Authentik, I have even established a central user management tool.
So I am gradually moving away from the [[Walled Garden\|Walled Garden]] of the big 5 and have a system that is becoming easier to maintain.
Borg and Borgmatic are used for backup. I'm currently planning an offsite backup using Wireguard and Raspberry Pis, which will then be set up at my (in-laws') parents' house. With the help of an append-only backup, this will also prevent a total loss of data in the future. It is important that my system is not designed to be fail-safe.


<div class="transclusion internal-embed is-loaded"><div class="markdown-embed">





==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'

# Excalidraw Data

## Text Elements

Nginx Proxy Manager 
Nextcloud 
Prosody 
... 
Router 
Cloudflare 
CloudflareD 
Local area network 
Unraid 
PC1 
PC ... 


</div></div>


The image shows that some devices in the LAN can also bypass the detour via the WAN, depending on the configuration. This is realized with the help of Pi-Hole and its custom DNS function. Pi-Hole is actually only intended to block advertising, but its functions have enabled a very easy-to-use DNS tool to be included in the system.


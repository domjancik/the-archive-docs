Currently no clean way to set up a self-signed trusted SSL certificate is available, see Proposals in https://httpslocal.github.io/proposals/

Main available approaches are:
- Using a trusted certificate for a real domain, see https://anteru.net/blog/2020/enabling-ssl-in-your-local-network/ 
	- Requires using DNS provider with API access (may be possible to do manually)
	- Requires modifying local DHCP server to assign the SSL certificate's domain name to local network, eg. Pi-hole
- Creating a self-signed certificate which needs to be accepted in the user device, see https://web.dev/how-to-use-local-https/ for some approaches

---

```
mkcert thearchive localhost 10.81.2.113 ::1
```

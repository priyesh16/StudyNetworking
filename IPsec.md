
## Features:

  * Confidentiality
  * Encryption
  * Integrity
	* Integrity check by checking message authentication code (MAC)
	* MAC is a checksum based on a mutually agreed secret key
  * Authentication
	* only transmitted to expected endpoint
  * Replay Protection
	* same data will not be accepted multiple times
	* data is not grossly out of order
  * Traffic Analysis Protection
	* protect against person monitoring the network 
	* obfuscate which parties are communicating
	* how often they are communicating
	* how much data is exchanged
	* Traffic flow confidentiality(TFC) capabilities of ESP
		* pad all packets to a single length(usually MTU)
		* send dummy packets to obfuscate the timing of packets
  * Access Control
	* IPsec endpoints perform filtering 
	* ensures only authorized users can access network resources
	* eg) allowing web server access but not file sharing
	* This is aka policy based IPsec
	* In route based IPsec all traffic is accepted at the policy layer
		* 	traffic is filtered by setting routes into IPsec interfaces. 
		* 	routing table acts as a policy filter
	* Policy based IPsec 
	* is more secure than routing based IPsec
	* is not vulnerable to malicious/accidental routing table changes
	* works independently to firewall and other access control mechanism
* Perfect Forward Secrecy (PFS)
	* session keys are changed typically once an hour
	* Old keys are deleted from memory 
		* so that in future nobody can decrypt past messages
	* To make sure old keys has no relationship to new keys we can do a DH exchange again. This mechanism is called PFS
* Mobility
	* outer IP address can change
		* without causing interruption to encrypted flow. 
	* Since application is only concerned about inner IP address,
		* the outer address can change 
		* allows user to change from Wifi to Ethernet without interruption

## Deployments:

* Site-to-site VPNs—Tunnels
	  * maintained by hardware devices
	  * connect multiple users at remote branches to (one or more) central sites.
  * Teleworker VPNs—Tunnels:
	  * maintained by hardware devices
	  * connect (typically) a single user at residence to a central site.
  * Remote-access clients—Tunnels:
	  * established by software
	  * connect mobile users at airports, hotels to a central site 
			using WLAN hotspots, LAN ports, or modems.

## VPN
	
* Most common deployment for IPsec
	* built on top of existing physical networks
	* provides secure communication
	* such as internet
	* less expensive than dedicated private links
	* deployments
		* mesh of IPsec connections across all nodes
		* subset of IPsec connections in a network
	* Confidentiality
		* symmetric cryptography
			* less processing power
			* algorithms that implement symmetric encryption -> AES, 3DES
			* modes for symmetric encryption algorithms -> AES-GCM
	* Integrity
		* HMAC
		* AES modes such as AES-CBC, AES-CMAC, AES-GMAC
	* Shared Keys
		* DH key exchange to create a confidential communication channel to compute shared key
		* After DH key exchange peers need to authenticated
	* Peer Authentication
		* 

  

## References
	- https://www.cisco.com/c/en/us/td/docs/solutions/Enterprise/WAN_and_MAN/QoS_SRND/QoS-SRND-Book/IPSecQoS.html
	- https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-77r1.pdf
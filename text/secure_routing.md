From Catnip/HTIRW: "This system [of ASs and BGP routes] is very clever, but asyou can guess, it's also quite prone to mistake. For example, if a neighbor shares the wrong map, or pretends to know how to get from one place to another when it actually doesn't, this can create an impasse or traffic congestion." We go on to describe peering, transit and IXPs.

## What is routing?

Routing is the process routers and networks use to exchange information and choose IP traffic paths. Devices on the Internet share information about the location of IP addresses, and IP traffic represents the flow of data across the Internet. For example, when we visit a website, data is exchanged between a client, like your phone or computer, and a server. These endpoints are identified by IP addresses.
IP traffic consists of packets, which are individual units of information from the same source to the same destination. Knowing a packet's destination IP address lets a router pick a path to reach it.
Routing protocols distribute information about IP address locations. Border Gateway Protocol (BGP) is the routing protocol used on the Internet. Networks connected to the internet, be it businesses, schools, governments, service providers, and more, are known as autonomous systems. There are many autonomous systems on the Internet, and each one uses BGP to advertise its own IP addresses to neighbors, who then share this information with their neighbors, and so on. This way, everyone knows where an IP address is located and can select a path to reach it.
In general, BGP prefers the shortest path, represented by the fewest number of autonomous systems needed to reach a destination (AS Path).
As information spreads, forwarding takes over. Forwarding moves IP traffic within a router or node. Based on the destination address, it decides which "next hop" (an adjacent router) to use.  Routing is a control plane function that shares knowledge while forwarding is in the data plane and acts on packets.
The routing information, mostly from BGP, helps create a forwarding table. This table shows the direction or interface to reach the "next hop". The same concept applies to forwarding IP traffic between autonomous systems; the next autonomous system is selected to reach a destination.  So, one autonomous system uses the forwarding information to send a packet to a specific destination through a specific neighboring autonomous system.
Each autonomous system is independent and can make its own decisions about routing and forwarding. It can build its forwarding tables using local policies or other factors, not just BGP information. 
For example, let's say a business has multiple service providers. BGP will prefer the one that announces the shorter AS Path to reach the destination.  However, if the other service provider charges less, the local autonomous system might choose to use the longer AS Path for financial reasons. This is a common practice on the Internet.
The forwarding table in the local autonomous system can be adjusted using local policy to prefer this alternate path. Local policy plays a role in decision-making, and information from outside BGP can influence choices made within an autonomous system.
Once a path is chosen, each router or autonomous system can select which "next hop" to use based on local policy.

## What is secure routing?

Authentication and confidentiality are usually considered when discussing security. BGP doesn't have built-in security mechanisms, so it relies on TCP for its capabilities. The recommended mechanism for authentication is TCP-AO. For encryption, TCP can run over TLS or IPsec.
The main concern today is the validity of the routes in BGP updates. When BGP was first created, the Internet was small, and everyone trusted each other. With the growth of the Internet, trust is harder to come by. Sometimes, routes are announced by autonomous systems that don't own them, a problem known as route hijacking. These hijacks can be intentional or due to misconfigurations.
BGP lacks a built-in way to verify if the information in updates is accurate. Regional internet registries like ARIN, LACNIC, RIPE, AFRINIC, and APNIC assign IP addresses and autonomous system numbers to local service providers, enterprises, and others. The RPKI (Resource Public Key Infrastructure) was created to verify routing objects and IP address ownership using public key infrastructure.
In RPKI, each participant can create a ROA (Route Origin Attestation) to confirm the relationship between an autonomous system and its IP addresses. The ROAs can be used for BGP route origin validation. In general, RIRs host repositories that service providers or enterprises use to populate local caches, which in turn provide validated information for routers to validate routes.
Not all routers need to perform route origin validation—only those with external BGP peers. While this system helps verify routes, it has limitations. Validation is optional and non-transitive; each autonomous system must validate routes independently. Malicious systems can still create updates that appear valid.
Obtaining ROAs happens outside BGP's route distribution, creating potential risks if unverified routes are used to access repositories. Synchronization issues can also occur as ROAs propagate through the RPKI infrastructure.
Despite these challenges, route origin validation is effective against route hijacking. Given that most internet paths are four to five hops long, this method offers a good approximation of path validity but only protects some of the path.
Ideally, only validated routes would be used for forwarding, but not all routes are covered by ROAs. Discarding unvalidated routes could cause reachability issues.
Proposals like BGPsec and ASPA aim to improve path validation by providing assurances about the list of autonomous systems a route traverses or can be in plausible paths. ASPA is nearing standardization, while BGPsec is already a standard but requires significant resources for deployment.
Local policies still influence routing decisions; an unvalidated route might be used over a valid one based on these policies. Routing and forwarding operate on different layers, allowing them to be decoupled from each other.

## Open to ideas

[It doesn’t stop here… Something about MANRS.]
Why does the State department (or other entity) care about secure routing? (link to IAB submission)
https://datatracker.ietf.org/doc/statement-iab-comments-on-a-notice-by-the-federal-communications-commission-on-secure-internet-routing-issued-03-11-2022/ 
What is “the internet way of routing”? (eg, what has ISOC said about it?) https://www.danyork.com/2023/10/slides-for-my-isc2-security-congress-session-on-demystifying-routing-security.html

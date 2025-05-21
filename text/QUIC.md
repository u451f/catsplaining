# Techsplanations: The QUIC Protocol \- Speed and Security

Beyond the canonical protocols that enable internet communication, one newcomer has been heralded as a revolution for data privacy and speed. The QUIC protocol — an acronym for Quick UDP Internet Connections — has garnered significant attention due to its unique approach to addressing the challenges of speed and security in modern online interactions. Stemming from Google's engineering endeavors, QUIC employs a framework that promises faster, more secure, and more efficient communication between clients and servers, as compared to its predecessors. QUIC was fully developed into an open standard in the Internet Engineering Task Force (IETF)’s [RFC 9000](https://datatracker.ietf.org/doc/html/rfc9000) in 2021\.

# A protocol with the best of both worlds

People expect immediate access to content online, but latency — the delay before data transfer begins — can be a major hindrance to that immediacy. Currently-used data transfer protocols like TCP (Transmission Control Protocol) introduce latency by requiring multiple round trips between client and server before any data is exchanged. QUIC employs a more streamlined approach, accelerating the establishment of connections by using UDP (User DataGram Protocol) to discard this latency-inducing “handshake” process. UDP alone was considered an insufficient protocol for wide implementation because while fast, it lacked security and resilience against packet loss (when some data fails to make it to its destination, resulting in outcomes like pixelated video on streaming services).

# Key Features of QUIC

QUIC combines the best features of TCP (packet loss mitigation and security) and UDP (speed), along with novel innovations for modern-day networking use. The main features of QUIC, which we explain below, are encryption, multiplexing, packet loss mitigation, and connection migration. 

## Encryption

Encryption protects data while it is being communicated over a network between the user and the service provider. Transport encryption is paramount to secure online communications at all layers of the internet stack. QUIC integrates security measures from the Transport Layer Security (TLS) protocol to ensure the confidentiality and integrity of data during transmission.

QUIC's distinctiveness lies in its encryption-first design. Traditional protocols tend to encrypt data after the “handshake” between client and server, leaving room for vulnerabilities during the initial connection. In contrast, QUIC encrypts data, providing an extra layer of security at the outset. This encryption-first approach not only enhances security but reduces the chances of data interception and tampering. 

Furthermore QUIC eliminates the need for a “SYN-SYN-ACK” three-way handshake between the user and the server, reducing latency and accelerating connection setup. QUIC does not need the handshake because it uses cryptographic keys exchanged during a previous connection, allowing subsequent connections to be established with minimal round trips.

Let’s use web search as an example: Before QUIC, an additional layer called transport layer security (TLS) was needed to secure HTTP connections over TCP. Establishing this secure connection with TLS involves a series of steps (the three-way handshake) that adds latency. QUIC streamlines this process by combining the transport and encryption handshakes, reducing the number of round trips required to establish a secure connection. So when you initiate a web search in your browser, QUIC helps in securing your search queries and the resulting data at this transport layer, and by default. The encryption ensures that information about what you’re searching and who you are is protected from eavesdropping or tampering, regardless of whether you are connected via an unsecured Wi-Fi network or a more secure wired connection.

## Multiplexing

QUIC employs multiplexing, meaning that it enables multiple streams of data to be transmitted concurrently over a single connection. That feature benefits users by ensuring a smooth experience even in resource-intensive scenarios.

This efficient stream management improves performance and resource utilization. Applications benefit from this feature by being able to prioritize specific streams, ensuring that critical data receives the necessary attention without compromising the overall communication process.

For example, when you open a webpage your browser often needs to download multiple resources from the server, such as HTML files, CSS stylesheets, JavaScript files, and images. Connections before QUIC would use HTTP over TCP and each resource would be requested and downloaded in turn. With QUIC a browser can open a single connection to the server and simultaneously request and receive multiple resources and each resource is treated as a separate stream within the QUIC connection. This means that even if one stream is slow or blocked, the other streams can continue unimpeded, allowing a smoother user experience.

## Minimizing Packet Loss Disruptions

Inherent to any data transmission process is the possibility of packet loss – packets of data failing to reach their destination. QUIC addresses this challenge through forward error correction techniques. These techniques allow the protocol to recover lost packets, reducing the need for retransmissions and minimizing disruptions in data flow. The result is enhanced reliability and a smoother user experience, particularly in scenarios where packet loss is more likely, such as wireless connections.

For example, streaming video at high resolutions requires a steady and consistent flow of data. In a TCP-based connection, if packets are lost, the protocol requires a retransmission of the lost data, and all data transmission is halted until the lost packets are resent and acknowledged. Before QUIC the alternative was to use UDP, which doesn’t resend lost packets and therefore keeps a steady transmission stream, however this can lead to a low-quality stream. QUIC combines the best of both of these protocols and handles packet loss more efficiently. QUIC operates over UDP to achieve steady transmission and, like TCP, when packet loss occurs resends only the lost packets. This means that a video stream over QUIC can continue relatively smoothly even when some packet loss occurs, reducing buffering and improving the viewer's experience.

## Mobility and Connection Migration

QUIC is designed to seamlessly handle changes in network conditions, making it well-suited for mobile devices and scenarios where users switch between different networks. This adaptability ensures uninterrupted connectivity during transitions.

As our devices become more interconnected, the ability to move seamlessly between different network connections and devices is crucial. QUIC's design caters to this demand by allowing connections to be effortlessly migrated between devices or network interfaces. This adaptability ensures that users can switch between devices or networks without interruptions, providing a consistent and continuous online experience.

A real-world example of QUIC's connection migration can be seen in the use of mobile devices, such as smartphones or tablets, especially when a user is on the move. Consider a scenario where a user is watching a live stream or video call on their smartphone while commuting. As they move, their device might switch from using a Wi-Fi network (e.g., at a train station) to a cellular network (e.g., LTE or 5G) as they leave the station.

# QUIC in Practice

QUIC is not just a proprietary solution; it is an open standard. This openness encourages collaboration among different entities, fostering innovation and preventing a single entity from dictating the evolution of the protocol. As a result, QUIC's future development will likely involve multiple contributors, leading to a more robust and resilient protocol that can adapt to the changing landscape of internet communication.

In the intricate world of networking protocols, the QUIC protocol emerges as an obvious evolution of internet communication that brings demonstrable improvements. Its unique blend of speed optimization, encryption-first security, and adaptability to various network conditions positions it as a significant player in shaping the future of data exchange. By addressing the challenges of latency, packet loss, and security, QUIC opens doors to a more efficient and secure online experience, fostering a safer and more interconnected digital realm.
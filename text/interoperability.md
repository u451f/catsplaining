# What is interoperability? 

Interoperability refers to the ability of two systems to communicate with each other interactively. Email is interoperable, for example, because by using the shared SMTP protocol two separate email services can successfully share data (emails) with each other. Interoperability is a general design concept which can be applied to any number of systems, both physical and digital. Different railroad companies, for example, need to make interoperable tracks for trains to be able to most effectively leverage national railroad infrastructure. Standardized specifications are the heart of interoperability. For this brief, we’ll focus on the benefits and challenges of interoperability as applied to social media or messaging systems.

Two systems do not have to be the same in order to be able to interoperate. For example, mobile browsers interoperate with the mobile operating system they are installed upon. The browser may interoperate with the phone to access the camera or to access text from the clipboard.

Interoperability is distinct from compatibility and portability. Compatibility refers to the ability of two systems to exist in the same environment without one disrupting the function of the other. Instagram and Twitter are compatible, but not interoperable. The two can both exist on a phone without impairing the function of each other, but one cannot comment on an Instagram post from Twitter.

Portability refers to the ability to transfer data from one application to another, but not necessarily via communication between applications. Being able to download a .csv from Excel and transfer it to Google Sheets is an example of portability. However, Google Sheets and Excel are not interoperable as you cannot use Google Sheets and Excel to edit the same asset.

## How can software systems interoperate?

There are two software design patterns which can be used to enable interoperability: APIs and Protocols.

### APIs

APIs are a set of functions which enable data exchange between applications. Two systems may be made interoperable if they exchange data through APIs. A hypothetical social networking platform CrochetNet might release an API. This API might take in a CrochetNet user identifier and return that user’s public posts in the past 24 hours. A competing social network, YarnNetwork, might use CrochetNet’s API to display posts that were originally posted to CrochetNet. In this way, CrochetNet and YarnNetwork are able to interoperate via data exchanged by an API.

The organization defining the API has control over how it is structured. They will structure the system’s inputs, outputs, and parameters around how it is used. An organization may place limits on how frequently their API is used, for example, to protect their servers from being overloaded. In the hypothetical CrochetNet example, CrochetNet decided that their API users would have to provide identifiers specific to CrochetNet and that they would only provide posts from the past 24 hours. These and other decisions in the hands of the API creator go a long way in shaping to what extent interoperability is enabled by the API.

Interoperable APIs are desirable when XXX – Mallory  (each section: describe, interoperability feature, example, points of control, third-party services, competition)
        ◦ [] – Sukhi can you find 3-4 examples? I can then write them out
        ◦ 3 Examples of Interoperability via API:
            ▪ Healthcare Interoperability Rule is proposed through a “standards-based” API: https://www.federalregister.gov/documents/2020/05/01/2020-05050/medicare-and-medicaid-programs-patient-protection-and-affordable-care-act-interoperability-and
            ▪ Hardware APIs: ​​https://developer.apple.com/documentation/avfoundation/capture_setup
                • As one example, linked above is the API that Apple provides to enable developers to access the iPhone camera. These types of hardware APIs have historically impacted browser interoperability for example. How much hardware access Apple gives to developers directly impacts how well developers can interoperate with the iPhone.
            ▪ Open Banking in Europe Occurs via standards-based APIs: https://standards.openbanking.org.uk/api-specifications/latest/

Note: really like the points you added here and above which discuss how the protocol / api design inherently distribute power in different ways

### Protocols and standards

Another way systems can achieve interoperability is to agree to use common standards and protocols. Protocols are specifications which describe syntax and procedures for structuring and exchanging data. The popular SMS protocol is an example. The protocol defines how to identify recipients (properly formatted numbers), how to format short message data, and how to send and receive that data. Two endpoints which have implemented the SMS protocol are able to communicate with each other. 

In this case, both parties adopting the protocol have an equal relationship in establishing interoperability between their systems as they have both chosen to structure their data in a particular way according to the protocol. If the protocol was defined through a multistakeholder process, it may also reflect a consensus between a broad set of industry stakeholders.

In either case, the existence of a protocol or existence of an API alone is not sufficient to accomplish interoperability. They are technical tools which organizations must intentionally leverage in order to build systems which interoperate.

Interoperable protocols are fundamental to internet architecture – Mallory (each section: describe, interoperability feature, example, points of control, third-party services, competition)
        ◦ TCP/IP – any networked device can send and receive packets
        ◦ HTTP/S – any device can talk to servers and other devices with applications
        ◦ HTML – any web browser can load any web page → Open Internet (no silos)
        ◦ POP/IMAP and SMTP – email clients and services can send and receive emails
        ◦ IPv4/6 and DNS – services can be found with an address or a domain

Note: Not trying to get into the benefits of interop here, just to explain that we can take for granted that that any webpage can be accessed and that's really because of intentionally interoperable architecture

### Use case: e2ee

The case of e2ee: Why some software services are interoperable, others we are still exploring whether they should be and how – TBD, main conclusion section

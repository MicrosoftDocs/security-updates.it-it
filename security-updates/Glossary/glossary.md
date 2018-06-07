---
TOCTitle: Glossary
Title: Glossary
ms:assetid: 'a7dd454f-fef8-4dab-a1c7-349f902b04ac'
ms:contentKeyID: 63185425
ms:mtpsurl: 'https://technet.microsoft.com/en-us/library/Dn848375(v=Security.10)'
author: SharonSears
ms.author: SharonSears
---

Glossary
========

Updated: October, 31 2016

## A

**Active Directory Federation Services (AD FS)**

Active Directory Federation Services (AD FS) is a standards-based service that allows the secure sharing of identity information between trusted business partners (known as a federation) across an extranet. When a user needs to access a web application from one of its federation partners, the user's own organization is responsible for authenticating the user and providing identity information in the form of "claims" to the partner that hosts the web application. The hosting partner uses its trust policy to map the incoming claims to claims that are understood by its web application, which uses the claims to make authorization decisions.

**Address Space Layout Randomization (ASLR)**

Address Space Layout Randomization (ASLR) moves executable images into random locations when a system boots, which helps prevent an attacker from leveraging data at predictable locations. For a component to support ASLR, all components that it loads must also support ASLR. For example, if A.exe consumes B.dll and C.dll, all three must support ASLR. By default, Windows Vista, Windows Server 2008, Windows 7, Windows Server 2008 R2, Windows 8, Windows 8.1, Windows RT, Windows RT 8.1, Windows Server 2012, and Windows Server 2012 R2 will randomize system DLLs and EXEs, but DLLs and EXEs created by Independent Software Vendors (ISVs) must opt in to support ASLR using the /DYNAMICBASE linker option.

ASLR also randomizes heap and stack memory:

When an application creates a heap in Windows Vista, Windows Server 2008, Windows 7, Windows Server 2008 R2, Windows 8, Windows 8.1, Windows RT, Windows RT 8.1, Windows Server 2012, and Windows Server 2012 R2, the heap manager will create that heap at a random location to help reduce the chance that an attempt to exploit a heap-based buffer overrun succeeds. Heap randomization is enabled by default for all applications running on Windows Vista and later.

-   When a thread starts in a process linked with /DYNAMICBASE, Windows Vista, Windows Server 2008, Windows 7, Windows Server 2008 R2, Windows 8, Windows 8.1, Windows RT, Windows RT 8.1, Windows Server 2012, and Windows Server 2012 R2 move the thread's stack to a random location to help reduce the chance that a stack-based buffer overrun exploit will succeed. 

**Always Encrypted**

Always Encrypted is a feature designed to protect sensitive data, such as credit card numbers or national identification numbers (e.g. U.S. social security numbers), stored in Azure SQL Database or SQL Server databases. Always Encrypted allows clients to encrypt sensitive data inside client applications and never reveal the encryption keys to the Database Engine (SQL Database or SQL Server). As a result, Always Encrypted provides a separation between those who own the data (and can view it) and those who manage the data (but should have no access

**Application Compatibility Infrastructure (AppCompat)**

The Microsoft Windows Application Compatibility Infrastructure (AppCompat) is designed to preserve application functionality as the Microsoft Windows operating system changes from version to version. The AppCompat infrastructure allows for targeted fixes to specific applications and specific versions of applications, with these fixes being stored outside of the core Windows functions.

**ASP.NET**

ASP.NET is a collection of technologies within the Microsoft .NET Framework that enable developers to build Web applications and XML Web Services.

Unlike traditional Web pages, which use a combination of static HTML and scripting, ASP.NET uses compiled, event-driven pages. Because ASP.NET is a Web-based application environment, requiring an underlying Web server to provide basic HTTP functionality, ASP.NET runs on top of Internet Information Services (IIS). For more information, see [The Official Microsoft ASP.NET Site](http://www.asp.net/).

## C

**Certification Authority (CA)**

Certification authorities are the organizations that issue certificates. They establish and verify the authenticity of public keys that belong to people or other certification authorities, and they verify the identity of a person or organization that asks for a certificate. 

**Certificate Trust List (CTL)**

A trust must exist between the recipient of a signed message and the signer of the message. One method of establishing this trust is through a certificate, an electronic document verifying that entities or persons are who they claim to be. A certificate is issued to an entity by a third party that is trusted by both of the other parties. So, each recipient of a signed message decides if the issuer of the signer's certificate is trustworthy. CryptoAPI has implemented a methodology to allow application developers to create applications that automatically verify certificates against a predefined list of trusted certificates or roots. This list of trusted entities (called subjects) is called a certificate trust list (CTL). For more information, please see the MSDN article, [Certificate Trust Verification](http://msdn.microsoft.com/en-us/library/aa376546(v=vs.85).aspx).

**Cipher suite**

A cipher suite is a set of cryptographic algorithms. Schannel protocols use algorithms from a cipher suite to create keys and encrypt information. For more information about cipher suites, see [Cipher Suites in Schannel](http://msdn.microsoft.com/en-us/library/windows/desktop/aa374757(v=vs.85).aspx). 

**Common Log File System (CLFS)**

The Common Log File System (CLFS) is a high-performance, general-purpose log file subsystem that dedicated client applications can use and multiple clients can share to optimize log access.

**Content Security Policy (CSP)**

Microsoft Edge now implements Content Security Policy (CSP) 1.0. For extended details, see the [W3C Content Security Policy specification](http://www.w3.org/tr/2012/cr-csp-20121115/). The CSP security standard enables web developers to control the resources (JS, CSS, plugins, images, etc.) which a particular page can fetch or execute with the aim of preventing cross-site scripting (XSS), clickjacking, and other code injection attacks seeking to execute malicious content in the context of a trusted web page. With CSP, web developers can create an allow list of sources of trusted content in the HTTP headers, pre-approving certain servers for content loaded into a webpage and instructing the browser to only execute or render resources from those sources.

**Cross-site Request Forgery (CSRF/XSRF)**

Cross-site Request Forgery (CSRF/XSRF) is a type of attack that occurs when a malicious website, email, blog, instant message, or program causes a user’s Web browser to perform an unwanted action on a trusted site for which the user is currently authenticated.

**Cross-site scripting (XSS)**

Cross-site scripting (XSS) is a class of security vulnerability that can enable an attacker to inject script code into a user's session with a website. The vulnerability can affect web servers that dynamically generate HTML pages. If these servers embed browser input in the dynamic pages that they send back to the browser, these servers can be manipulated to include maliciously supplied content in the dynamic pages. This can allow malicious script to be executed. Web browsers may perpetuate this problem through their assumptions of trusted sites and their use of cookies to maintain persistent state with the websites that they frequent. An XSS attack does not modify website content. Instead, it inserts new, malicious script that can execute at the browser in the context that is associated with a trusted server. 

**Cryptography**

Cryptography is the science of securing information by converting it between its normal, readable state (called plaintext) and one in which the data is obscured (known as ciphertext).

In all forms of cryptography, a value known as a key is used in conjunction with a procedure called a crypto algorithm to transform plaintext data into ciphertext. In the most familiar type of cryptography, secret-key cryptography, the ciphertext is transformed back into plaintext using the same key. However, in a second type of cryptography, public-key cryptography, a different key is used to transform the ciphertext back into plaintext.

**Cryptography Next Generation (CNG)**

Cryptography Next Generation (CNG) provides a flexible cryptographic development platform to create, update, and use custom cryptography algorithms in cryptography-related applications.

## D

**Defense-in-depth**

In information security, defense-in-depth refers to an approach in which multiple layers of defense are in place to help prevent attackers from compromising the security of a network or system. 

**Digital Certificate**

In [public-key cryptography](http://msdn.microsoft.com/en-us/library/92f9ye3s.aspx), one of the keys, known as the private key, must be kept secret. The other key, known as the public key, is intended to be shared with the world. Digital certificates are used primarily to verify the identity of a person or device, authenticate a service, or encrypt files. A digital certificate is a tamperproof piece of data that packages a public key together with information about it - who owns it, what it can be used for, when it expires, and so forth.  

**Document Type Definition (DTD)**

DTD, standing for document type definition, is a file format type that is used in XML and other markup languages to identify the markup to be used to format a document.

**Domain Name System (DNS)**

Domain Name System (DNS), a locator service in Microsoft Windows, is an industry-standard protocol that locates computers on an IP-based network. IP networks, such as the Internet and Windows networks, rely on number-based addresses to process data.

## E

**Enhanced Mitigation Experience Toolkit (EMET)**

The Enhanced Mitigation Experience Toolkit (EMET) is designed to help customers with their defense in depth strategies against cyberattacks, by helping detect and block exploitation techniques that are commonly used to exploit memory corruption vulnerabilities. EMET helps protect against new and undiscovered threats even before they are formally addressed through security updates or antimalware software. EMET includes 14 security mitigations that complement other defense in-depth security measures, such as Windows Defender and antivirus software. EMET installs with default protection profiles, which are XML files that contain preconfigured settings for common Microsoft and third-party applications. For more information about EMET, see the [Enhanced Mitigation Experience Toolkit](http://technet.microsoft.com/security/jj653751). 

**Enhanced Metafile (EMF)**

EMF is a 32-bit format that can contain both vector information and bitmap information. This format is an improvement over the Windows Metafile Format (WMF) and contains extended features.

For more information about image types and formats, see [Microsoft Knowledge Base Article 320314](http://support.microsoft.com/kb/320314). For additional information about graphics file formats, see MSDN article, [Metafiles](https://msdn.microsoft.com/en-us/library/ms536391.aspx).

## H

**HTML Injection**

HTML injection is a class of security vulnerability that can enable an attacker to inject HTML code into a user's session with a website. The vulnerability can affect web servers that dynamically generate HTML pages. If these servers embed browser input in the dynamic pages that they send back to the browser, these servers can be manipulated to include maliciously supplied content in the dynamic pages. This can allow malicious script to be executed. Web browsers may perpetuate this problem through their assumptions of trusted sites and their use of cookies to maintain persistent state with the websites that they frequent. An HTML injection attack does not modify website content. Instead, it inserts new, malicious HTML code that can execute at the browser in the context that is associated with a trusted server.

**Hypervisor Code Integrity (HVCI)**

The HVCI service in Windows 10 determines whether code executing in kernel mode is securely designed and trustworthy. It offers Zero Day and vulnerability exploit protection capabilities by ensuring that all software running in kernel mode, including drivers, securely allocate memory and operate as they are intended. In Windows 10, kernel mode code integrity is configurable, which allows organizations to scope preboot code execution to their desired configuration.

## I

**Internet Authentication Service (IAS)**

In Microsoft Windows 2000 Server, Internet Authentication Service (IAS) is the Microsoft implementation of a Remote Authentication Dial-in User Service (RADIUS) server. As a RADIUS server, IAS performs centralized connection authentication, authorization, and accounting for many types of network access, including wireless and virtual private network (VPN) connections. On Microsoft Windows 2000 Server, IAS does not support RADIUS Proxy because it is based on the Option Pack version.

In Windows Server 2003, Internet Authentication Service (IAS) is the Microsoft implementation of a Remote Authentication Dial-in User Service (RADIUS) server and proxy. As a RADIUS server, IAS performs centralized connection authentication, authorization, and accounting for many types of network access, including wireless and virtual private network (VPN) connections. As a RADIUS proxy, IAS forwards authentication and accounting messages to other RADIUS servers. 

**Internet Protocol Security (IPSec)**

Internet Protocol security (IPSec) is a framework of open standards for helping to ensure private, secure communications over Internet Protocol (IP) networks through the use of cryptographic security services. IPSec supports network-level data integrity, data confidentiality, data origin authentication, and replay protection. Because IPSec is integrated at the Internet layer (layer 3), it provides security for almost all protocols in the TCP/IP suite, and because IPSec is applied transparently to applications, there is no need to configure separate security for each application that uses TCP/IP.

**Input Method Editor (IME)**

Input Method Editors (IMEs) help solve an issue associated with entering information in certain languages via a keyboard. Languages like Chinese and Japanese contain thousands of different characters, and it isn't feasible to build a keyboard that includes all of them. IMEs allow the characters to be built using a standard 101-key keyboard, by specifying the strokes that compose each character.

An IME consists of an engine that converts keystrokes into phonetic and ideographic characters and a dictionary of commonly-used ideographic words. As the user enters keystrokes via the keyboard, the IME identifies the keystrokes and converts them into characters.  

**Input/Output Control (IOCTL)**

Windows provides the ability for applications to directly request services of device drivers. The interface through which this is done is called an input/output control, or IOCTL. 

**Internet Information Service (IIS)**

The Web Server (IIS) role in Windows Server provides a secure, easy-to-manage, modular and extensible platform for reliably hosting websites, services, and applications. For more information, see the TechNet article, [Web Server IIS Overview](http://technet.microsoft.com/library/hh831725.aspx). 

**IP Address and Domain Restrictions**

IP Address and Domain Restrictions is a Web Server (IIS) feature that allows the creation of rules that allow or deny access to content for a specific IP address, a range of IP addresses, or a domain name or set of domain names. These rules are also known as "white list" or “black list” rule sets.

All IP addresses, computers, and domains can access your site by default. To enhance security, you can restrict access to your site by creating a restriction rule for all IP addresses, a specific IP address, a range of IP addresses, or a specific domain or domains.

For example, if you have a site on an intranet server that is connected to the Internet, you can prevent Internet users from accessing your intranet site by allowing access only to members of your intranet, and explicitly denying access to outside users, see the article, [IP security](http://www.iis.net/configreference/system.webserver/security/ipsecurity). 

## J

**JPEG**

JPEG is a platform-independent image format that supports a high level of compression. JPEG is a widely supported Internet standard developed by the Joint Photographic Experts Group.

**JPEG XR**

JPEG XR (.XJR) is a Microsoft-developed JPEG file format for continuous tone images that supports higher compression ratios and color accuracy than the standard JPEG format.

## K

**Kerberos**

Kerberos is a protocol that is used to mutually authenticate users and services on an open and unsecured network. It allows services to correctly identify the user of a Kerberos ticket without having to authenticate the user at the service. It does this by using shared secret keys.

The Kerberos protocol uses shared secret keys to encrypt and sign users' credentials. A client is authenticated by a Kerberos Key Distribution Center (KDC). After that authentication, the user can request a service ticket to access a specific service on the network. This ticket includes the encrypted and signed identity of the user.

Kerberos Key Distribution Center (KDC) is a network service that supplies session tickets and temporary session keys to users and computers within an Active Directory domain. The KDC runs on each domain controller as part of Active Directory Domain Services (AD DS).

**Kill Bits**

A security feature in Microsoft Internet Explorer makes it possible to prevent an ActiveX control from ever being loaded by the Internet Explorer HTML-rendering engine. This is done by making a registry setting and is referred to as setting the kill bit. After the kill bit is set, the control can never be loaded, even when it is fully installed. Setting the kill bit makes sure that even if a vulnerable component is introduced or is re-introduced to a system, it remains inert and harmless.

For more information on kill bits, see [Microsoft Knowledge Base Article 240797](http://support.microsoft.com/kb/240797).

## M

**Man-in-the-middle (MiTM) attack**

A man-in-the-middle (MiTM) attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users. Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all the while thinking they are communicating only with the intended user.

**Microsoft .NET Remoting**

Microsoft .NET Remoting is a technology that simplifies how applications communicate and share objects with other applications.

**Microsoft DirectShow**

DirectX consists of a set of low-level Application Programming Interfaces (APIs) used by Windows programs for multimedia support. Within DirectX, the DirectShow technology performs client-side audio and video sourcing, manipulation and rendering.

Microsoft DirectShow is used for streaming media on Microsoft Windows operating systems. DirectShow is used for high-quality capture and playback of multimedia streams. It automatically detects and uses video and audio acceleration hardware when available, but also supports systems without acceleration hardware. DirectShow is also integrated with other DirectX technologies. Some examples of applications that use DirectShow include DVD players, video editing applications, AVI to ASF converters, MP3 players, and digital video capture applications.

**Microsoft XML Core Services (MSXML)**

Microsoft XML Core Services (MSXML) allows customers who use JScript, Visual Basic Scripting Edition (VBScript), and Microsoft Visual Studio 6.0 to develop XML-based applications that provide interoperability with other applications that adhere to the XML 1.0 standard. For more information, see the MSDN site, [MSXML](http://msdn.microsoft.com/en-us/library/ms763742.aspx).

**Mitigation**

Refers to a setting, common configuration, or general best-practice, existing in a default state that could reduce the severity of exploitation of a vulnerability. 

## N

**Network Driver Interface Standard (NDIS)**

The Network Driver Interface Standard (NDIS) is part of the Windows Driver Kit, which is a fully integrated driver development system that contains the Windows Driver Device Kit and tests for stability and reliability of Windows drivers. The NDIS library abstracts the network hardware from network drivers. NDIS also specifies a standard interface between layered network drivers, thereby abstracting lower-level drivers that manage hardware from upper-level drivers, such as network transports. NDIS also maintains state information and parameters for network drivers, including pointers to functions, handles, and parameter blocks for linkage, and other system values.

**Network Location Awareness (NLA) service**

The Network Location Awareness service enables network-interacting programs to change their behavior based on how the computer is connected to the network. In the case of Windows Firewall with Advanced Security, you can create rules that apply only when the profile associated with a specific network location type is active on your computer.

**Network Policy Server (NPS)**

Network Policy Server (NPS) is the Microsoft implementation of a Remote Authentication Dial-in User Service (RADIUS) server and proxy in Windows Server 2008. NPS is the replacement for Internet Authentication Service (IAS) in Windows Server 2003. As a RADIUS server, NPS performs authentication, authorization, and accounting for wireless, authenticating switch, and remote access dial-up and virtual private network (VPN) connections.

**NT LAN Manager (NTLM) Authentication Protocol**

NT LAN Manager (NTLM) Authentication Protocol is a protocol that uses a challenge-response mechanism for authentication in which clients are able to verify their identities without sending a password to the server. It consists of three messages, commonly referred to as Type 1 (negotiation), Type 2 (challenge), and Type 3 (authentication).

## O

**Object Linking and Embedding (OLE)**

A technology that allows applications to share data and functionality, such as the ability to create and edit compound data. Compound data is data that contains information in multiple formats. For example, a compound Microsoft Word document may contain an embedded Microsoft Excel spreadsheet (or OLE object). This technology also enables in-place editing; instead of launching a new application when an OLE object is activated, the user instead sees a new set of menu items inside their existing application. For more information about OLE, see [Compound Documents](http://msdn.microsoft.com/library/ms693383). 

## P

**PFS**

PFS is a property of key-agreement protocols that makes sure that a session key derived from a set of long-term keys will not be compromised if one of the long-term keys is compromised in the future.

**PGM**

PGM is a reliable and scalable multicast protocol that enables receivers to detect loss, request retransmission of lost data, or notify an application of unrecoverable loss. PGM is a receiver-reliable protocol, which means the receiver is responsible for ensuring all data is received, absolving the sender of responsibility for the reliability of communications. PGM is appropriate for applications that require duplicate-free multicast data delivery from multiple sources to multiple receivers. PGM does not support acknowledged delivery, nor does it guarantee ordering of packets from multiple senders. For more information on PGM, see the following [MSDN Article](https://msdn.microsoft.com/en-us/library/ms740125(vs.85).aspx).

**PNG**

PNG stands for Portable Network Graphics. The Portable Network Graphics (PNG) format was designed to replace the older and simpler GIF format and, to some extent, the much more complex TIFF format. Additional information about PNG can be found at the following [website](http://www.libpng.org/pub/png/pngintro.html).

## R

**Remote Authentication Dial-in User Service (RADIUS)**

Remote Authentication Dial-In User Service (RADIUS) is a client-server networking protocol that provides centralized Authentication, Authorization, and Accounting (AAA or Triple A) management for users who connect to a network service. RADIUS provided a central authentication and authorization service for all access requests that are sent by RADIUS clients. The RADIUS protocol manages access to the Internet or internal networks, wireless networks, and integrated e-mail services. These networks may incorporate modems, DSL, access points, VPNs, network ports, web servers, etc. Network Policy Server (NPS) can be used as a Remote Authentication Dial-In User Service (RADIUS) server to perform authentication, authorization, and accounting for RADIUS clients.

**Remote Desktop Protocol (RDP)**

Remote Desktop Protocol (RDP) lets users create a virtual session on their desktop computers. RDP allows remote users to access all of the data and applications on their computers. For more information, see the MSDN article, [Remote Desktop Protocol](http://msdn.microsoft.com/en-us/library/aa383015(v=vs.85).aspx).

**Remote Procedure Call (RPC)**

Microsoft Remote Procedure Call (RPC) is an inter-process communication (IPC) mechanism that enables data exchange and invocation of functionality residing in a different process. That process can be on the same computer, on the local area network (LAN), or across the Internet. The Microsoft RPC mechanism uses other IPC mechanisms, such as named pipes, NetBIOS, or Winsock, to establish communications between the client and the server. With RPC, essential program logic and related procedure code can exist on different computers, which is important for distributed applications. For more information, see the TechNet article, [What Is RPC?](https://technet.microsoft.com/library/cc787851)

**RPC NDR Engine**

The Remote Procedure Call (RPC) Network Data Representation (NDR) Engine is the marshaling engine of the RPC and DCOM components. The NDR Engine handles all stub-related issues of a remote call. As a process, NDR marshaling is driven by the C code from MIDL-generated stubs, a MIDL JIT-type generator, or by stubs generated by other tools or written manually. In turn, the NDR engine drives the underlying run time (DCOM or RPC) that communicates with specific transports.

## S

**Same Origin Policy**

The same-origin policy is used by web browsers to prevent a script loaded from one domain from getting or manipulating properties of a webpage from another domain. This means that, by default, the domain of a requested URL must be the same as the domain of the current webpage.

**Secure Channel (Schannel)**

The Secure Channel (Schannel) security package is a Security Support Provider (SSP) that implements the Secure Sockets Layer (SSL) and Transport Layer Security (TLS) Internet standard authentication protocols. These components are used to implement secure communications in support of several common internet and network applications, such as web browsing. Schannel is part of the security package that helps provide an authentication service to provide secure communications between client and server. For more information, see [Secure Channel](http://msdn.microsoft.com/en-us/library/aa380123(vs.85).aspx).


**Secure Sockets Layer (SSL)**

The Secure Sockets Layer (SSL) protocol is a predecessor of the Transport Layer Security protocol. It performs the same functions and supports secure network communications using a combination of public and secret key technology. For more information, see How [TLS/SSL works](http://technet.microsoft.com/en-us/library/cc783349(ws.10).aspx).

**Server Side Request Forgery (SSRF)**

Server Side Request Forgery (SSFR) is a type of attack that can allow an attacker to target internal systems behind the firewall that are normally inaccessible from the outside world. The attacker could then create requests which appear to come from the vulnerable server. In addition, an attacker can use SSRF attacks to:

-   Scan and attack systems from the internal network that are not normally accessible
-   Enumerate and attack services that are running on these hosts
-   Exploit host-based authentication services

## T

**Task Scheduler**

Task Scheduler is a Windows feature that enables you to automatically perform routine tasks on a chosen computer. The Task Scheduler can be used to execute tasks such as starting an application, sending an email message, or showing a message box.

**Telnet**

By using Telnet Client and Telnet Server, you can run command-line programs, shell commands, and scripts in a remote command console session just as though you were locally logged on to the remote host.

**Transport Layer Security (TLS) Handshake Protocol**

The Transport Layer Security (TLS) Handshake Protocol is responsible for the authentication and key exchange necessary to establish or resume secure sessions. For more information, see How [TLS/SSL works](http://technet.microsoft.com/en-us/library/cc783349(ws.10).aspx).

**Trusted Boot**

Trusted Boot is a Windows 8.1 feature that secures the entire Windows boot process. It prevents malware from hiding and taking up permanent residence within the PC by ensuring none of the Windows components loaded during boot have been tampered with. Trusted Boot also ensures that anti-malware software is loaded before any third-party drivers and applications using its Early Launch Anti-Malware (ELAM) capability. This prevents malware from inserting itself in front of the anti-malware engine so that it can compromise the anti-malware engine’s ability to protect the system. In the event that malware was able to successfully compromise the any of the Windows boot process, Trusted Boot will attempt to automatically remediate the issue.

## U

**Uniscribe**

Uniscribe is a set of APIs that allow a high degree of control for fine typography and for processing complex scripts. Both complex scripts and simple scripts with fine typography effects require special processing to display and edit because the characters ("glyphs") are not laid out in a simple way. For complex scripts, the rules governing the shaping and positioning of glyphs are specified and catalogued in [The Unicode Standard](http://go.microsoft.com/fwlink/p/?linkid=161643). For more information see [Uniscribe](https://msdn.microsoft.com/en-us/library/windows/desktop/dd374091(v=vs.85).aspx).

## V

**VBScript**

VBScript (Visual Basic Script) is an interpreted, object-based scripting language that is often used to make websites more flexible or interactive. VBScript scripts can run only in the presence of an interpreter or host, such as Active Server Pages (ASP), Internet Explorer, or Windows Script Host. For more information, see [VBScript Fundamentals](http://msdn.microsoft.com/library/0ad0dkea).

## W

**WebDAV**

Web Distributed Authoring and Versioning (WebDAV) is an extension to the Hypertext Transfer Protocol (HTTP) that defines how basic file functions such as copy, move, delete and create are performed by a computer using HTTP.

**WebDAV Redirector**

A WebDAV Redirector is a remote file system over the WebDAV protocol that allows Windows client machines to connect to your WebDAV publishing directory through the command line. The WebDAV Redirector enables you to manipulate files on the Web as though the files exist on a mapped network drive.

**WebDAV Mini-Redirector**

The WebDAV Mini-Redirector is also known as the WebClient service. This service lets DAV-enabled folders appear as Universal Naming Convention (UNC) shares.

**Windows Error Reporting**

Windows Error Reporting (WER) is a flexible event-based feedback infrastructure designed to gather information about the hardware and software problems that Windows can detect, report the information to Microsoft, and provide users with any available solutions. For more information about WER, see the Microsoft Developer Network (MSDN) article [About WER](http://msdn.microsoft.com/library/windows/desktop/bb513613(v=vs.85).aspx).

**Windows Forms (WinForms)**

Windows Forms is a smart client technology for the .NET Framework, a set of managed libraries that simplify common application tasks such as reading and writing to the file system. When you use a development environment like Visual Studio, you can create Windows Forms smart-client applications that display information, request input from users, and communicate with remote computers over a network. For more information, see [Windows Forms Overview](https://msdn.microsoft.com/en-us/library/8bxxy49h.aspx).

**Windows kernel**

The Windows kernel is the core of the operating system. It provides system-level services such as device management and memory management, allocates processor time to processes, and manages error handling.

**Windows kernel-mode driver (win32k.sys)**

Win32k.sys is a kernel-mode device driver and is the kernel part of the Windows subsystem. It contains the window manager, which controls window displays; manages screen output; collects input from the keyboard, mouse, and other devices; and passes user messages to applications. It also contains the Graphics Device Interface (GDI), which is a library of functions for graphics output devices. Finally, it serves as a wrapper for DirectX support that is implemented in another driver (dxgkrnl.sys).

**Windows Registry Virtualization**

Windows Registry Virtualization is an application compatibility technology that enables registry write operations that have global impact to be redirected to per-user locations. This redirection is transparent to applications reading from or writing to the registry.

**Windows Shell**

The Windows UI provides users with access to a wide variety of objects necessary for running applications and managing the operating system. The most numerous and familiar of these objects are the folders and files that reside on computer disk drives. There are also a number of virtual objects that allow the user to perform tasks such as sending files to remote printers or accessing the Recycle Bin. The Shell organizes these objects into a hierarchical namespace and provides users and applications with a consistent and efficient way to access and manage objects.

**Workaround**

Refers to a setting or configuration change that does not correct the underlying vulnerability but would help block known attack vectors before you apply the update.

**Web Proxy Automatic Discovery (WPAD) protocol**

The Web Proxy Automatic Discovery (WPAD) protocol allows automatic discovery of Web Proxy servers. WPAD provides a mechanism for clients to locate a WPAD entry containing a URL that points to a server on which the Wpad.dat and Wspad.dat files are generated. The Wpad.dat file is a JavaScript file containing a default URL template, constructed by Internet Explorer. The Wpad.dat file is used by Web Proxy clients for automatic discovery information.
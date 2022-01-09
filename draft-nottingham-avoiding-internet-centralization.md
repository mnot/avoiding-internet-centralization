---
title: Centralization and Internet Standards
abbrev:
docname: draft-nottingham-avoiding-internet-centralization-latest
date: {DATE}
category: info

ipr: trust200902
area: General
workgroup:
keyword: Internet-Draft

stand_alone: yes
smart_quotes: no
pi: [toc, tocindent, sortrefs, symrefs, strict, compact, comments, inline]

venue:
  github: mnot/avoiding-internet-centralization

author:
 -
    ins: M. Nottingham
    name: Mark Nottingham
    organization:
    postal:
      - Prahran
    country: Australia
    email: mnot@mnot.net
    uri: https://www.mnot.net/

normative:

informative:
  RAND:
    target: https://www.rand.org/pubs/research_memoranda/RM3420.html
    title: "On Distributed Communications: Introdution to Distributed Communications Networks"
    date: 1964
    author:
     -
       name: Paul Baran
       orgnaization: RAND Corporation
  HTTP: I-D.draft-ietf-httpbis-semantics
  SOAP: W3C.REC-soap12-part0-20070427
  SCALE-FREE:
    target: https://barabasi.com/f/67.pdf
    title: Emergence of Scaling in Random Networks
    date: October 1999
    author:
     -
       ins: A. Barabási
       name: Albert-László Barabási
       organization: University of Notre Dame
       email: alb@nd.edu
    author:
     -
       ins: R. Albert
       name: Réka Albert
       organization: University of Notre Dame
  INTERMEDIARY-INFLUENCE:
    target: https://scholarship.law.columbia.edu/faculty_scholarship/1856
    title: Intermediary Influence
    date: 2014
    author:
     -
        ins: K. Judge
        name: Kathryn Judge
        organization: Columbia Law School
        email: kjudge@law.columbia.edu
  WEAPONIZED-INTERDEPENDENCE:
    target: https://doi.org/10.1162/ISEC_a_00351
    title: "Weaponized Interdependence: How Global Economic Networks Shape State Coercion"
    date: 2019
    author:
     -
        ins: H. Farrell
        name: Henry Farrell
        organization: George Washington University
     -
        ins: A. L. Newman
        name: Abraham L. Newman
        organization: Georgetown University
  MOXIE:
    target: https://signal.org/blog/the-ecosystem-is-moving/
    title: "Reflections: The ecosystem is moving"
    date: 10 May 2016
    author:
     -
       ins: M. Marlinspike
       name: Moxie Marlinspike
       organization: Signal
  LEGITIMACY-MULTI:
    title: "Legitimacy, Power, and Inequalities in the Multistakeholder Internet Governance"
    date: 2020
    author:
     -
       name: Nicola Palladino
     -
       name: Nauro Santaniello
  NEW-CHICAGO:
    title: "The New Chicago School"
    date: June 1998
    author:
     -
       name: Laurence Lessig
  POLYCENTRIC:
    title: "Polycentricity: From Polanyi to Ostrom, and Beyond"
    date: April 2012
    author:
     -
       name: Paul D. Aligia
     -
       name: Vlad Tarko
  PIR:
    title: Revisiting the Computational Practicality of Private Information Retrieval
    date: 2010
    author:
     -
      name: Femi Olumofin
     -
      name: Ian Goldberg
  ACCESS:
    title: Defending Competition in a Digitised World, Address at the European Consumer and Competition Day
    date: 4 April 2019
    target: https://wayback.archive-it.org/12090/20191129202059/https://ec.europa.eu/commission/commissioners/2014-2019/vestager/announcements/defending-competition-digitised-world_en
    author:
     -
      name: Margrethe Vestager
  TECH-SUCCESS-FACTORS:
    title: Study on the Internet's Technical Success Factors
    date: December 2021
    target: https://blog.apnic.net/wp-content/uploads/2021/12/MKGRA669-Report-for-APNIC-LACNIC-V3.pdf
    author:
     -
       name: Michael Kende
     -
       name: Amund Kvalbein
     -
       name: Julia Allford
     -
       name: David Abecassis
  OECD:
    title: Data portability, interoperability and digital platform competition
    date: 9 June 2021
    target: https://www.oecd.org/daf/competition/data-portability-interoperability-and-digital-platform-competition-2021.pdf
    author:
     -
      organization: OECD

--- abstract

Despite being designed and operated as a decentralized network-of-networks, the Internet is continuously subjected to forces that encourage centralization.

This document offers a definition of centralization, explains why it is undesirable, identifies different types of centralization, catalogues limitations of common approaches to controlling it, and explores what Internet standards efforts can do to address it.

--- middle

# Introduction

The Internet has succeeded in no small part because of its purposeful avoidance of any single controlling entity. While this approach may reflect a desire to prevent a single technical failure from having wide impact,{{RAND}} it has also enabled the Internet's rapid adoption and broad spread, because internetworking did not require obtaining permission from or ceding control to another entity -- thereby accommodating a spectrum of requirements and positioning the Internet as a public good.

While avoiding centralization is a widely shared goal for the Internet, meeting that goal has proven difficult. Many successful protocols and applications on the Internet today are designed or operated in a centralized fashion -- to the point where some proprietary, centralized services have become so well-known that they are commonly mistaken for the Internet itself. Even when protocols incorporate techniques intended to prevent centralization, economic and social factors can drive users to prefer centralized solutions built with or on top of supposedly decentralized technology.

These difficulties call into question what role architectural regulation -- in particular, open standards bodies such as at the IETF -- should be play in preventing, mitigating, and controlling centralization of the Internet.

This document discusses aspects of centralization that relate to Internet standards efforts. {{what}} provides a definition of centralization. {{why}} explains why centralization of Internet's functions is undesirable. {{kinds}} surveys the different kinds of centralization that might surface on the Internet. {{decentralization}} then catalogues high-level approaches to mitigating centralization and discusses their limitations. Finally, {{considerations}} considers the role that Internet standards play in avoiding centralization and mitigating its effects.

Engineers who design and standardize Internet protocols are the primary audience for this document. However, designers of proprietary protocols can benefit from considering aspects of centralization, especially if they intend their protocol to be considered for eventual standardisation. Likewise, policymakers can use this document to help identify and remedy inappropriately centralized protocols and applications.


# What is Centralization {#what}

This document defines "centralization" as the ability of a single entity (e.g., a person, company, or government) -- or a small group of them -- to observe, control, or extract rent from the operation or use of a given function on the Internet.

Here, "function" is defined broadly. It might be an enabling protocol already defined by standards, such as IP {{?RFC791}}, BGP {{?RFC4271}}, TCP {{?RFC793}}, or HTTP {{HTTP}}. It might also be a proposal for a new enabling protocol, or an extension to an existing one.

However, centralization is not limited to standards-defined protocols. User-visible applications built on top of the functions provided by standards are also vulnerable to centralization -- for example, social networking, file sharing, financial services, and news dissemination. Likewise, the supply of hardware, operating systems, and software can exhibit centralization.

Centralization risk is strongest when it necessarily affects the entire Internet. However, it can also be present when a substantial portion of the Internet's users lack options for a given function. For example, if there is only one provider a function in a given region or legal jurisdiction, that function is effectively centralized for those users.

"Decentralization" is the process of identifying centralization risk in the functions of a protocol or application, followed by application of appropriate techniques to prevent or mitigate centralization.

Decentralization does not require that a given function need be so widely distributed that other important factors, such as efficiency, resiliency, latency, or availability are sacrificed. In some cases, a function that is only available through a relatively small number of providers can be  effectively decentralized, given the appropriate circumstances (see, for example, the DNS).

Therefore, discussions of centralization and architectural efforts at decentralization need to be made on a case-by-base basis, depending on the function in question, surrounding circumstances, and other regulatory mechanisms.

Note that it is important to distinguish centralization from anti-competitive concerns (also known as "anti-trust"). While there are many interactions between them and making the Internet more competitive may be a motivation for avoiding centralization, only courts are authoritative in determining what is and is not anti-competitive in a given market, not standards bodies and other technical fora.


# Why Avoid Centralization {#why}

Centralization is undesirable because it is counter to the nature of the Internet, because it violates the end users' expectations, and because of the many negative effects it can have on the networks operation and evolution.

Firstly, the Internet's very nature is incompatible with centralization of its functions. As a 'large, heterogeneous collection of interconnected systems' {{?BCP95}} the Internet is often characterised as a 'network of networks'. As such, these networks relate as peers who agree to facilitate communication, rather than having a relationship of subservience to others' requirements or coercion by them.

Secondly, as the Internet's first duty is to the end user {{?RFC8890}}, allowing such power to be concentrated into few hands is counter to the IETF's mission of creating an Internet that 'will help us to build a better human society.' {{?BCP95}} When a third party has unavoidable access to communications, the 'informational and positional advantages' {{INTERMEDIARY-INFLUENCE}} gained can be used to observe behavior (the 'panopticon effect') and shape or even deny behaviour (the 'chokepoint effect') -- which can be used by those parties (or the states that have authority over them) for coercive ends. {{WEAPONIZED-INTERDEPENDENCE}}

Finally, concentration of power has deleterious effects on the Internet itself, including:

* _Limiting Innovation_: Centralization can preclude the possibility of 'permissionless innovation' -- the ability to deploy new, unforeseen applications without requiring coordination with parties other than those you are communicating with.

* _Constraining Competition_: The Internet and its users benefit from robust competition when applications and services are available from many different providers -- especially when those users can build their own applications and services based upon interoperable standards. When dependencies are formed on a centralized service or platform, it effectively becomes an essential facility, which encourages abuse of power.

* _Reducing Availability_: The Internet's availability (as well as applications and services built upon it) improves when there are many ways to obtain access to it. While centralized services typically benefit from the focused attention that their elevated role requires, when they do fail the resulting loss of availability can have disproportionate impact.

* _Creating Monoculture_: At the scale available to a centralized service or application, minor flaws in features such as recommendation algorithms can be magnified to a degree that can have broad (even societal) consequences. Diversity in the implementation of these functions is significantly more robust, when viewed systemically. {{POLYCENTRIC}}

* _Self-Reinforcement_: As widely noted (see, eg., {{ACCESS}}), a centralized service benefits from access to data which can be used to further improve its offerings, while denying such access to others.

See also {{TECH-SUCCESS-FACTORS}}.

To summarize, centralization would allow the Internet (or some part of it) to be captured, effectively turning it into a 'walled garden' that fails to meet both architectural design goals and users' expectations, and endangering its ongoing viability at the same time.


# Kinds of Centralization {#kinds}

Centralization of the Internet is not uniform; it presents in a variety of ways, depending on its relationship to the function in question and underlying causes. The subsections below offer the start of a classification system for Internet centralization.


## Direct Centralization {#direct}

The most straightforward kind of centralization creates a fixed role for a specific party. For example, most proprietary messaging, videoconferencing, chat, and similar protocols operate in this fashion.

While it has been argued that such protocols are simpler to design, more amenable to evolution, and more likely to meet user needs {{MOXIE}}, this approach most often reflects commercial goals -- in particular, a strong desire to capture the financial benefits of the protocol by 'locking in' users to a proprietary service.

Directly centralised protocols and applications are not considered to be part of the Internet per se; instead, they are more properly characterized as proprietary protocols that are built on top of the Internet. As such, they are not regulated by the Internet architecture or standards, beyond the constraints that the underlying protocols (e.g., TCP, IP, HTTP) impose.


## Necessary Centralization {#necessary}

Some protocols require the introduction of centralization risk that is unavoidable by nature.

For example, when there is a need a single, globally coordinated 'source of truth', that function is by nature centralized. The most obvious instance is seen in the Domain Name System (DNS), which allows human-friendly naming to be converted into network addresses in a globally consistent fashion.

Allocation of IP addresses is another example of a necessary function being a centralization risk. Internet routing requires addresses to be allocated uniquely, but if the addressing function were captured by a single government or company, the entire Internet would be at risk of abuse by that entity.

Similarly, the need for coordination in the Web's trust model brings centralization risk, because a Certificate Authority (CA) can control communication between the Web sites that they sign certificates for and users whose browsers trust the CA's root certificates.

Protocols that need to solve the "rendezvous problem" to coordinate communication between two parties that are not in direct contact also suffer from this kind of centralization risk. For example, chat protocols need a way to coordinate communication between two parties that wish to talk; while the actual communication can be direct between them (so long as the protocol facilitates that), the endpoints' mutual discovery typically requires a third party.

Internet protocols often attempt to mitigate necessary centralization risk using measures such as mandated federation {{federation}} and multi-stakeholder administration {{multi}}.

Because of the inherent risks and costs of these approaches, functions that successfully use these techniques are often reused by others with similar requirements. For example, if a protocol requires a coordinated, global naming function, reusing the Domain Name System is usually preferable to establishing a new system, because its centralization risk is known and understood, and the risks inherent in establishing new mitigations are avoided.


## Indirect Centralization {#indirect}

Even when a protocol avoids direct centralization and does not exhibit any necessary centralization, it might become centralized in practice when external factors influence its deployment. Indirect centralization can be caused by factors that encourage use of a central function despite the absence of such a requirement in the protocol itself. Such factors might be economic, social, or legal.

Often, the factors driving indirect centralization are related to the network effects that are so often seen on the Internet. While in theory every node on the Internet is equal, in practice some nodes are much more connected than others: for example, just a few sites drive much of the traffic on the Web. While expected and observed in many kinds of networks {{SCALE-FREE}}, network effects award asymmetric power to nodes that act as intermediaries to communication.

Left unchecked, these factors can cause a potentially decentralized application to become directly centralised, because the central function has leverage to "lock in" users. For example, social networking is an application that is currently supplied by a small number of directly centralized, proprietary platforms despite standardization efforts (see, e.g., {{?W3C.CR-activitystreams-core-20161215}}), due to the powerful network effects associated.

By its nature, indirect centralization is difficult to avoid in protocol design, and federated protocols are particularly vulnerable to it (see {{federation}}).


## Inherited Centralization {#network}

Most Internet protocols depend on other, "lower-layer" protocols. The features, deployment, and operation of these dependencies can surface centralization risk into functions and applications build "on top" of them.

For example, the network between endpoints can introduce centralization risk to application-layer protocols, because it is necessary for communication and therefore has power over it. A given network might block access to, slow down, or modify the content of various application protocols or specific services for financial, political, operational, or criminal reasons, thereby creating pressure to use other services, which can in turn result in centralization of them.

Inherited centralization risk is only present when users cannot use an alternative means of accessing the desired service. For example, users often have flexibility in choice of Internet access, so they could just "route around" a network that impacts their chosen service. However, such choices are often not available in the moment, and the Internet's topology means that a choke point upstream could still affect their Internet access.

When deployed at scale, encryption can be an effective technique to control many inherited centralization risks. By reducing the number of parties who have access to content of communication, the ability of lower-layer protocols and intermediaries at those layers to interfere with or observe is precluded. Even when they can still prevent communication, the use of encryption makes it more difficult to discriminate the target from other traffic.

Note that the prohibitive effect on inherited centralization is most pronounced when most (if not all) traffic is encrypted -- providing yet more motivation for that goal (see also {{?RFC7258}}).


## Platform Centralization {#platform}

The complement to inherited centralization is platform centralization -- where a function does not directly define a central role, but could facilitate centralization in the applications it supports.

For example, HTTP {{HTTP}} in itself is not considered a centralized protocol; interoperable servers are relatively easy to instantiate, and multiple clients are available. It can be used without central coordination beyond that provided by DNS, as discussed above.

However, applications built on top of HTTP (as well as the rest of the 'Web Platform') often exhibit centralization. As such, HTTP is an example of a platform for centralization -- while the protocol itself is not centralized, it does facilitate the creation of centralized services and applications.

Like indirect centralization, platform centralization is difficult to completely avoid in protocol design. Because of the layered nature of the Internet, most protocols are designed to allow considerable flexibility in how they are used, often in a way that it becomes attractive to form a dependency on one party's operation. Notably, this can happen even if the protocol does not accommodate intermediation explicitly.


# The Limits of Decentralization {#decentralization}

Over time, various techniques have been developed to decentralize protocols and applications. While these approaches can be used to create a function which is less centralized or less amenable to some kinds of centralization, they are not adequate to completely avoid centralization on their own. As such, while the use of these techniques is often appropriate and sometimes effective, they are not indicators of whether a protocol is centralized without further analysis.


## Federation isn't Enough {#federation}

A widely known technique for managing centralization in Internet protocols is federation -- that is, designing them in such a way that new instances of any intermediary or otherwise centralized function are relatively easy to create, and they are able to maintain interoperability and connectivity with other instances.

For example, SMTP {{?RFC5321}} is the basis of the e-mail suite of protocols, which has two functions that are necessarily centralized:

1. Giving each user a globally unique address, and
2. Routing messages to the user, even when they change network locations or are disconnected for long periods of time.

E-mail reuses DNS to help mitigate the first risk. To mitigate the second, it defines an intermediary role for routing users' messages, the Message Transfer Agent (MTA). By allowing anyone to deploy a MTA and defining rules for interconnecting them, the protocol's users avoid a requirement for a single, central router.

Users can (and often do) choose to delegate that role to someone else, or run their own MTA. However, running your own mail server has become difficult, due to the likelihood of a small MTA being classified as a spam source. Because large MTA operaters are widely known and have greater impact if their operation is affected, they are less likely to be classified as such, thereby indirectly centralizing the protocol's operation (see {{indirect}}).

Another example of a federated Internet protocol is XMPP {{?RFC6120}}, supporting "instant messaging" and similar functionality. Like e-mail, it reuses DNS for naming and requires federation to facilitate rendezvous of users from different systems.

While some deployments of XMPP do support truly federated messaging (i.e., a person using service A can interoperably chat with someone using service B), many of the largest do not. Because federation is voluntary, some operators made a decision to capture their users into a single service, rather than provide the benefits of global interoperability.

The examples above illustrate that federation can be a useful technique to avoid direct centralization and manage necessary centralization, but on its own is not sufficient to avoid indirect and platform centralization. If the value provided by a protocol can be captured by a single entity, they may use the protocol as a platform to obtain a 'winner take all' outcome -- a significant risk with many Internet protocols, since network effects often promote such outcomes. Likewise, external factors (such as spam control) might naturally 'tilt the table' towards a few operators of these protocols.


## Multi-Stakeholder Administration is Hard {#multi}

Delegating the administration of a necessarily centralized function (see {{necessary}}) to a multi-stakeholder body is occasionally used to mitigate its effects.

A multi-stakeholder body is an institution that includes representatives of the different kinds of parties that are affected by the system's operation ("stakeholders") in an attempt to make well-reasoned, broadly agreed-to, and authoritative decisions.

The most relevant example of this technique is the administration of the Domain Name System {{?RFC1035}}, which as a "single source of truth" exhibits necessary centralization of the naming function, as well as the operation of the system. To mitigate operational centralization, this task is carried out by multiple root servers that are administered by separate operators -- themselves diverse in geography and a selection of corporate entities, non-profits and government bodies from many jurisdictions and affiliations. Furthermore, the name space itself is [regulated by ICANN](https://www.icann.org/resources/pages/governance/governance-en), which is defined as a globally multi-stakeholder body with representation from end users, governments, operators, and others.

Another example of multi-stakeholderism is the standardization of Internet protocols themselves. Because a specification effectively controls the behavior of implementations that are conformant with it, the standardization process can be seen as a single point of control. As a result, Internet standards bodies like the IETF allow open participation and contribution, make decisions in an open and accountable way, have a well-defined process for making (and when necessary, appealing) decisions, taking into account the views of different stakeholder groups {{?RFC8890}}.

Yet another example is the administration of the Web's trust model, implemented by Web browsers as relying parties and Certificate Authorities as trust anchors. To assure that all parties meet the operational and security requirements necessary to provide the desired properties, the [CA/Browser Forum](https://cabforum.org) was established as an oversight body that involves both of those parties as stakeholders.

In each of these examples, setup and ongoing operation of a multi-stakeholder organization is not trivial. This is a major downside of this approach. Additionally, the legitimacy of such an organization cannot be assumed, and may be difficult to establish and maintain (see, eg, {{LEGITIMACY-MULTI}}). This concern is especially relevant if the function being coordinated is broad, complex, and/or contentious.


## Blockchains Are Not Magical {#distributed}

Increasingly, distributed consensus technologies such as the blockchain are touted as a solution to centralization issues. A complete survey of this rapidly-changing area is beyond the scope of this document, but at a high level, we can generalise about their properties.

These techniques attempt to avoid centralization risk by distributing intermediary or otherwise potentially centralized functions to members of a large pool of protocol participants. Verification of proper performance of a function is typically guaranteed using cryptographic techniques (often, an append-only transaction ledger). The assignment of a particular task to a node for handling usually cannot be predicted or controlled.

Sybil attacks (where enough participants coordinate their activity to affect the protocol's operation) are a major concern for these protocols. Diversity in the pool of participants is encouraged using indirect techniques such as proof-of-work (where each participant has to demonstrate significant consumption of resources) or proof-of-stake (where each participant has some other incentive to execute correctly).

Appropriate use of these techniques can create barriers to direct and inherited centralization. However, depending upon the application in question, indirect and platform centralization can still be possible.

Furthermore, distributed consensus technologies have several potential shortcomings that may make them inappropriate -- or at least difficult to use -- for many Internet applications, because their use conflicts with other important goals:

1. Distributed consensus protocols can have significant implications for privacy. Because activity (such as queries or transactions) are shared with many unknown parties, they have very different privacy properties than traditional client/server protocols. Mitigations (e.g., Private Information Retrieval; see, eg, {{PIR}}) are still not suitable for broad deployment.

2. Their complexity and "chattiness" typically result in significantly less efficient use of the network (often, to several orders of magnitude). When distributed consensus protocols use proof-of-work, energy consumption can become significant (to the point where some jurisdictions have banned its use).

3. Distributed consensus protocols are still not proven to scale to the degree expected of successful Internet protocols. In particular, relying on unknown third parties to deliver functionality can introduce variability in latency, availability, and throughput. This is a marked change for applications with high expectations for these properties (e.g., commercial Web services).

4. By design, distributed consensus protocols diffuse responsibility for a function among several, difficult-to-identify parties. While this may be an effective way to prevent some kinds of centralization, it also means that making someone accountable for how the function is performed is impossible, beyond the bounds of the protocol's design.

It is also important to recognise that a protocol or an application can use distributed consensus for some functions, but still have centralization risk elsewhere. Even when distributed consensus is used exclusively (which is uncommon, due to the associated costs), some degree of coordination is still necessary -- whether that be through governance of the function itself, creation of shared implementations, or documentation of shared wire protocols. That represents centralization risk, just at a different layer (inherited or platform, depending on the circumstances).

These potential shortcomings do not rule out the use of distributed consensus technologies for every use case. They do, however, caution against relying upon these technologies to avoid centralization uncritically.


# What Should Internet Standards Do? {#considerations}

Centralization is driven by powerful forces -- both economic and social -- as well as the network effects that come with Internet scale. Moreover, because permissionless innovation is a core value for the Internet, and yet much of the centralization seen on the Internet is performed by proprietary platforms that take advantage of this nature, the controls available to standards efforts on their own are very limited.

Nevertheless, while standards bodies on their own cannot prevent centralization, there are meaningful steps that can be taken to prevent some functions from exhibiting some forms of centralization. There are also valuable contributions that standards efforts can make to other, more effective forms of regulation.


## Manage Centralization Risk Where Effective {#target}

Some types of centralization risk are relatively easy to manage in standards efforts. A directly centralized protocol, were it to be proposed, would be rejected out of hand by the IETF. There is a growning body of knowledge and experience with necessary centralization, and a strong inclination to reuse existing infrastructure where possible. As discussed above, encryption is often a way to manage inherited centralization. All of these responses are appropriate ways for Internet standards to manage centralization risk.

However, precluding indirect and platform centralization are much more difficult in standards efforts. Because we have no "protocol police", it's not possible to demand that someone stop building a proprietary service using a purportedly federated protocol. We also cannot stop someone from building centralized services "on top" of standard protocols without violating architectural goals like permissionless innovation.

Therefore, committing significant resources to scrutinizing protocols for hidden or latent centralization risk -- especially for indirect and platform risks -- is unlikely to actually prevent Internet centralization. Almost all existing Internet protocols -- including IP, TCP, HTTP, and DNS -- suffer some form of indirect or platform centralization. Refusing to standardize a newer protocol because it faces similar risks would not be equitable, proportionate, or effective.

Centralization risk is sometimes perceived to be in tension with other goals, such as privacy. While there is rarely a pure tradeoff between two abstract goals such as these, when it does occur attention should be paid to how effective architectural regulation (such as a standards effort) is in achieving each goal. In this example, a technical mechanism might be much more effective at improving privacy, whereas centralization might be better controlled by other regulators -- leading to the conclusion that the standards effort should focus on privacy.


## Create Standards to Decentralize Proprietary Functions {#up}

Standards efforts should focus on creating new specifications for functions that are currently only satisfied by proprietary, centralized protocols. For example, if social networking is thought to be a centralized function, this might mean creating specifications that enable decentralized social networking, perhaps using some or all of the techniques described in {{decentralization}}.

Keen readers will point out that social networking is effectively centralized despite the existence of such standards (see, e.g., {{W3C.CR-activitystreams-core-20161215}}), because the IETF and W3C create voluntary standards, not mandatory regulations.

However, architecture is not the only form of regulation; legal mechanisms combined with changing norms and the resulting market forces have their own regulatory effects {{NEW-CHICAGO}}. While for much of its lifetime the Internet has only been subject to limited legal regulation, that period appears to be ending.

It is far from certain that a legal mandate for interoperability based upon Internet standards will eventuate, but it is increasingly discussed as a remedy for competition issues (see, e.g., {{OECD}}). It is also not certain that legally-mandated standards will fully address centralization risks. However, if such specifications are not available from the Internet community, they may be created elsewhere without reference to the Internet's architectural goals.

Even absent a legal mandate, changes in norms and the market -- due to increasing knowledge and distrust of centralized functions -- can create demand for such specifications and the corresponding implementations.


## Limit Intermediary Power {#intermediation}

The introduction of an intermediary role -- i.e., one that performs a function but is not a first party to communication -- adds indirect and platform centralization risk to Internet protocols, because it brings opportunities for control and observation. At the same time, intermediation often adds significant value to a protocol, or enables what is considered a necessary function.

While (as discussed above) standards efforts have a very limited capability to prevent or control indirect and platform centralization, constraints on intermediary functions -- when designed explicitly into a protocol -- and prevent at least the most egregious outcomes. In general, this can be achieved by limiting the nature of the intermediary role to the most minimal function possible.

For example, HTTP allows intermediaries to see the full content of traffic by default, even when they are only performing basic functions such as routing. However, with the introduction of HTTPS and the CONNECT method (see {{Section 9.3.6 of HTTP}}), combined with market forces to adopt HTTPS, those intermediaries now only have access to the appropriate routing information.

When carefully considered, intermediation can be a powerful way to enforce functional boundaries -- for example, to reduce the need for users to trust potentially malicious endpoints, as seen in
the so-called 'oblivious' protocols currently in development (e.g., {{?I-D.pauly-dprive-oblivious-doh}}) that allow end users to hide their identity from services, while still accessing them.

The same advice applies in these cases; the observation and control potential SHOULD be as minimal as possible, while still meeting the design goals of the protocol.

See {{?I-D.thomson-tmi}} for more guidance.

Another kind of intermediation is created when a new feature or service is built using a standard as a substrate. For example, many Web sites offer new functions like social networking and aggregated news updates that can be viewed as a proprietary intermediary function on the Internet. These intermediaries may not be a format part of the underlying protocol (in the case of Web sites, HTTP), but they can still interpose a third party into communication. This kind of intermediation is more effectively dealt with by standardising the function, rather than restricting the capability of the protocol; see {{up}}.


## Avoid Over-Extensibility {#evolution}

An important feature of Internet protocols is their ability to evolve over time, so that they can meet new requirements and adapt to new conditions without requiring a "flag day" to upgrade implementations. Typically, protocol evolution is accommodated through extension mechanisms, where optional features can be added over time in an interoperable fashion.

However, protocol extensions can also increase the risk of platform centralization if a powerful entity can change the target for meaningful interoperability by adding proprietary extensions to a standard protocol. This is especially true when the core standard does not itself provide sufficient utility on its own.

For example, the SOAP protocol {{SOAP}} was an extremely flexible framework, allowing vendors to attempt to capture the market by requiring use of their preferred extensions to interoperate.

Therefore, standards efforts should be focused on providing concrete utility to the majority of their users as published, rather than being a "framework" where interoperability is not immediately available.  Furthermore, Internet protocols should not make every aspect of their operation extensible; extension points should be reasoned, appropriate boundaries for flexibility and control. When extension points are defined, they should not allow an extension to declare itself to be mandatory-to-interoperate, as that pattern invites abuse.


# Security Considerations

This document does not have direct security impact on Internet protocols. However, failure to consider centralization risks might result in a myriad of security issues.


--- back


# Acknowledgements

This document benefits from discussions with Brian Trammell during our shared time on the Internet Architecture Board.

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
    title: "On Distributed Communications: Introduction to Distributed Communications Networks"
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
  MIX:
    title: Untraceable Electronic Mail, Return Addresses, and Digital Pseudonyms
    date: 1 February 1981
    target: https://dl.acm.org/doi/10.1145/358549.358563
    author:
     -
      name: David L. Chaum


--- abstract

Despite being designed and operated as a decentralized network-of-networks, the Internet is continuously subjected to forces that encourage centralization.

This document offers a definition of centralization, explains why it is undesirable, identifies different types of centralization, catalogues limitations of common approaches to controlling it, and explores what Internet standards efforts can do to address it.

--- middle

# Introduction

The Internet has succeeded in no small part because of its purposeful avoidance of any single controlling entity. While this approach may reflect a desire to prevent a single technical failure from having wide impact {{RAND}}, it has also enabled the Internet’s rapid adoption and broad spread. Because internetworking does not require networks to get permission from or cede control to another entity, it accommodates a spectrum of requirements and is positioned as a public good.

While avoiding centralization of control over the Internet remains a widely shared goal, achieving it consistently has proven difficult. Many successful protocols and applications on the Internet today work in a centralized fashion -- to the point where some proprietary, centralized services have become so well-known that they are commonly mistaken for the Internet itself. Even when protocols incorporate techniques intended to prevent centralization, economic and social factors can drive users to prefer centralized solutions built with or on top of supposedly decentralized technology.

These difficulties call into question what role architectural regulation -- in particular, open standards bodies such as the IETF -- should play in preventing, mitigating, and controlling Internet centralization.

This document discusses aspects of centralization that relate to Internet standards efforts. {{what}} provides a definition of centralization. {{why}} explains when and why centralization of the Internet's core functions is undesirable. {{kinds}} surveys the different kinds of centralization that might surface on the Internet. {{decentralization}} then catalogues high-level approaches to mitigating centralization and discusses their limitations. Finally, {{considerations}} considers the role that Internet standards play in avoiding centralization and mitigating its effects.

Engineers who design and standardize Internet protocols are the primary audience for this document. However, designers of proprietary protocols can benefit from considering aspects of centralization, especially if they intend their protocol to be considered for eventual standardisation. Likewise, policymakers can use this document to help identify and remedy inappropriately centralized protocols and applications.


# What is Centralization? {#what}

This document defines "centralization" as the ability of a single entity (e.g., a person, company, or government) -- or a small group of them -- to exclusively observe, capture, control, or extract rent from the operation or use of a Internet function.

Here, "Internet function" is defined broadly. It might be an enabling protocol already defined by standards, such as IP {{?RFC791}}, BGP {{?RFC4271}}, TCP {{?RFC793}}, or HTTP {{HTTP}}. It might also be a proposal for a new enabling protocol, or an extension to an existing one.

However, the Internet's functions are not limited to standards-defined protocols. User-visible applications built on top of standard protocols are also vulnerable to centralization -- for example, social networking, file sharing, financial services, and news dissemination. Likewise,  networking equipment, hardware, operating systems, and software act as enabling technologies that can exhibit centralization risk. The supply of Internet connectivity itself can also be subject to the forces of centralization.

Centralization risk is strongest when it affects the entire Internet. However, it can also be present when a substantial portion of the Internet's users lack options for a function. For example, if there is only one provider for a function in a region or legal jurisdiction, that function is effectively centralized for those users.

"Decentralization" is the process of identifying centralization risk related to a function, followed by the application of techniques used to prevent or mitigate that risk.

Decentralization does not require that provision of a function need be so widely distributed that other important factors are sacrificed. Because centralization can have beneficial effects (see {{direct}}), the techniques used to decentralize a given function might vary, with the optimal balance being determined by many factors. Notably, a function that is only available through a relatively small number of providers can still be effectively decentralized (see, for example, the Domain Name System {{?RFC1035}}).

Therefore, discussions of centralization and architectural efforts at decentralization need to be made on a case-by-base basis, depending on the function in question, surrounding circumstances, and other regulatory mechanisms.

Note that it is important to distinguish centralization from anti-competitive concerns (also known as "anti-trust"). While there are many interactions between these concepts and making provision of the Internet's functions more competitive may be a motivation for avoiding centralization, only courts are authoritative in determining what is and is not anti-competitive in a market, not standards bodies and other technical fora.


# When Centralization is Undesirable {#why}

Centralization is not always problematic, and is sometimes even desirable. If a function is specific to a given entity -- for example, a person's web site, or a government service -- it is expected that it be controlled by them alone. Furthermore, emerging applications and other functions can often gain significant benefits from being centralized, especially considering the potential costs of decentralization (see {{necessary}} for more discussion of the benefits of centralization).

However, when a function becomes widespread enough in use and especially when it becomes a platform for other functions to be built upon, it deserves more scrutiny for centralization risk. Centralization of such functions is undesirable because it is counter to the Internet's nature, because it violates the end users' expectations, and because of the many negative effects it can have on the network's operation and evolution.

First, the Internet's very nature is incompatible with centralization of its functions. As a "large, heterogeneous collection of interconnected systems" {{?BCP95}} the Internet is often characterised as a "network of networks". These networks relate as peers who agree to facilitate communication, rather than having a relationship of subservience to others' requirements or coercion by them. This focus on independence of action carries through the way the network is architected -- for example, in the concept of an "autonomous system".

Second, when a third party has unavoidable access to communications, the "informational and positional advantages" {{INTERMEDIARY-INFLUENCE}} gained can be used to observe behavior (the "panopticon effect") and shape or even deny behaviour (the "chokepoint effect") -- which can be used by those parties (or the states that have authority over them) for coercive ends {{WEAPONIZED-INTERDEPENDENCE}} or to disrupt society itself.

Finally, centralization has deleterious effects on the Internet itself, including:

* _Limiting Innovation_: Centralization can preclude the possibility of "permissionless innovation" -- the ability to deploy new, unforeseen applications without requiring coordination with parties other than those you are communicating with.

* _Constraining Competition_: The Internet and its users benefit from robust competition when applications and services are available from many providers -- especially when those users can build their own applications and services based upon interoperable standards. When functions form dependencies on a centralized service or platform because no substitutes are suitable, it effectively becomes an essential facility, which encourages abuse of power.

* _Reducing Availability_: The Internet's availability (as well as applications and services built upon it) improves when there are many ways to obtain access. While centralized services typically benefit from the focused attention that their elevated role requires, when they fail, the resulting loss of availability can have a disproportionate impact.

* _Creating Monoculture_: The scale available to a centralized service or application can magnify minor flaws in features such as recommendation algorithms to a degree that can have broad (even societal) consequences. Diversity in these functions’ implementation is significantly more robust when viewed systemically. {{POLYCENTRIC}}

* _Self-Reinforcement_: As widely noted (see, e.g., {{ACCESS}}), a centralized service’s access to data allows it the opportunity to make improvements to its offerings, while denying such access to others.

See also {{TECH-SUCCESS-FACTORS}} for further exploration of how centralization can affect the Internet.

To summarize, centralization would allow the Internet (or some part of it) to be captured, effectively turning it into a "walled garden" that cannot meet both architectural design goals and users' expectations, and endangering its ongoing viability at the same time.


# Kinds of Centralization {#kinds}

Centralization on the Internet is not uniform; it presents in a variety of ways, depending on its relationship to the function in question and underlying causes. The subsections below describe different aspects of Internet centralization.


## Proprietary Centralization {#direct}

Creating of a protocol or application with a fixed role for a specific party is the most straightforward kind of centralization. Currently, many widely used messaging, videoconferencing, chat, and similar protocols operate in this fashion.

While some argue that such protocols are simpler to design, more amenable to evolution, and more likely to meet user needs {{MOXIE}}, proprietary centralization most often reflects commercial goals -- in particular, a strong desire to capture the protocols' financial benefits by "locking in" users to a proprietary service.

Proprietary protocols and applications are not considered to be part of the Internet per se; instead, they are more properly characterized as being built on top of the Internet. As such, the Internet architecture and associated standards do not regulate them, beyond the constraints that the underlying protocols (e.g., TCP, IP, HTTP) impose.


## Beneficial Centralization {#necessary}

Some protocols introduce centralization risk that is unavoidable, because the protocol's goals requires a centralized function.

For example, when there is a need for a single, globally coordinated “source of truth”, that function is by nature centralized -- such as in the Domain Name System (DNS), which allows human-friendly naming to be converted into network addresses in a globally consistent fashion.

IP addresses allocation is another example of a function having this kind of centralization risk. Internet routing requires addresses to be allocated uniquely, but if a single government or company captured the addressing function, the entire Internet would be at risk of abuse by that entity.

Similarly, the need for coordination in the Web's trust model brings centralization risk, because of the Certificate Authority's role in communication between clients and servers.

Protocols that need to solve the "rendezvous problem" to coordinate communication between two parties who are not in direct contact also suffer from this kind of centralization risk. For example, chat protocols need to coordinate communication between two parties that wish to talk; while the actual communication can be direct between them (so long as the protocol facilitates that), the endpoints' mutual discovery typically requires a third party.

Internet protocols often attempt to mitigate beneficial centralization risk using measures such as federation (see {{federation}}) and multi-stakeholder administration (see {{multi}}).

Protocols that successfully mitigate beneficial centralization are often reused, to avoid the considerable cost and risk of re-implementing those mitigations. For example, if a protocol requires a coordinated, global naming function, reusing the Domain Name System is usually preferable to establishing a new system.


## Concentrated Centralization {#indirect}

Even when a protocol avoids proprietary centralization and does not require any beneficial centralization, it might become centralized in practice when external factors influence its deployment, so that relatively few or even just one entity provides the function. This is often referred to as "concentration." Economic, legal, and social factors that encourage use of a central function despite the absence of such a requirement in the protocol itself can cause concentration.

Often, the factors driving concentration are related to the network effects that are so often seen on the Internet. While in theory every node on the Internet is equal, in practice some nodes are much more connected than others: for example, just a few sites drive much of the traffic on the Web. While expected and observed in many kinds of networks,{{SCALE-FREE}} network effects award asymmetric power to nodes that act as intermediaries to communication.

Left unchecked, these factors can cause a potentially decentralized application to become effectively controlled by one party, because the central function has leverage to "lock in" users. For example, social networking is an application that is currently supplied by a few proprietary platforms despite standardization efforts (see, e.g., {{?W3C.CR-activitystreams-core-20161215}}), because of the powerful network effects associated.

By its nature, concentration is difficult to avoid in protocol design, and federated protocols are particularly vulnerable to it (see {{federation}}).


## Inherited Centralization {#network}

Most Internet protocols and applications depend on other, "lower-layer" protocols and their implementations. The features, deployment, and operation of these dependencies can surface centralization risk into functions and applications build "on top" of them.

For example, the network between endpoints can introduce centralization risk to application-layer protocols, because it is necessary for communication and therefore has power over it. A network might block access to, slow down, or change the content of various application protocols or specific services for financial, political, operational, or criminal reasons, thereby creating pressure to use other services, which can result in centralization of them.

Likewise, having only a single implementation of a protocol is an inherited centralization risk, because applications that use it are vulnerable to the control it has over their operation. Even if it is Open Source, there might be inherited centralization risk if there are factors that make forking difficult (for example, the cost of maintaining that fork).

Inherited centralization risk is often present when users cannot find a substitute because network effects reduce the choices available to them. This kind of centralization can also be created by legal mandates and incentives that restrict the options for Internet access, the provision of a given function, or the range of implementations available.

Some kinds of inherited centralization can be prevented by enforcing layer boundaries through use of techniques like encryption. When the number of parties who have access to content of communication are limited, parties at lower layers can be prevented from interfering with and observing it. Although those lower-layer parties might still be able to prevent communication, encryption also makes it more difficult to discriminate a target from other traffic.

Note that the prohibitive effect of encryption on inherited centralization is most pronounced when most (if not all) traffic is encrypted. See also {{?RFC7258}}.


## Platform Centralization {#platform}

The complement to inherited centralization is platform centralization -- where a function does not directly define a central role, but could facilitate centralization in the applications it supports.

For example, HTTP {{HTTP}} is not considered a centralized protocol; interoperable servers are relatively easy to instantiate, and multiple clients are available. It can be used without central coordination beyond that provided by DNS, as discussed above.

However, applications built on top of HTTP (as well as the rest of the “Web Platform”) often exhibit centralization. As such, HTTP is an example of a platform for centralization -- while the protocol itself is not centralized, it facilitates the creation of centralized services and applications.

Like concentration, platform centralization is difficult to prevent with protocol design. Because of the layered nature of the Internet, most protocols allow considerable flexibility in how they are used, often in a way that it becomes attractive to form a dependency on one party’s operation.


# The Limits of Decentralization {#decentralization}

Various techniques have been developed to decentralize protocols and applications. While use of these approaches can result in a function which is less centralized or less amenable to some kinds of centralization, they are not adequate to avoid centralization completely. They are also not indicators of whether a protocol is centralized without further analysis.


## Federation isn't Enough {#federation}

A widely known technique for managing centralization in Internet protocols is federation -- designing them in such a way that new instances of any centralized function are relatively easy to create and can maintain interoperability and connectivity with other instances.

For example, SMTP {{?RFC5321}} is the basis of the e-mail suite of protocols, which has two functions that have centralization risk:

1. Giving each user a globally unique address, and
2. Routing messages to the user, even when they change network locations or are disconnected for long periods of time.

E-mail reuses DNS to help mitigate the first risk. To mitigate the second, it defines a specific role for routing users' messages, the Message Transfer Agent (MTA). By allowing anyone to deploy an MTA and defining rules for interconnecting them, the protocol's users avoid a requirement for a single central router.

Users can (and often do) choose to delegate that role to someone else, or run their own MTA. However, running your own mail server has become difficult, because of the likelihood of a small MTA being classified as a spam source. Because large MTA operators are widely known and have greater impact if their operation is affected, they are less likely to be classified as such, concentrating the protocol’s operation (see {{indirect}}).

Another example of a federated Internet protocol is XMPP {{?RFC6120}}, supporting "instant messaging" and similar functionality. Like e-mail, it reuses DNS for naming and requires federation to facilitate rendezvous of users from different systems.

While some deployments of XMPP do support truly federated messaging (i.e., a person using service A can interoperably chat with someone using service B), many of the largest do not. Because federation is voluntary, some operators captured their users into a single service, rather than provide the benefits of global interoperability.

The examples above illustrate that federation can be a useful technique to avoid proprietary centralization and manage beneficial centralization, but on its own does not avoid concentration and platform centralization. If a single entity can capture the value provided by a protocol, they may use the protocol as a platform to get a “winner take all” outcome -- a significant risk with many Internet protocols, since network effects often promote such outcomes. Likewise, external factors (such as spam control) might naturally “tilt the table” towards a few operators.


## Multi-Stakeholder Administration is Hard {#multi}

The risks associated with a beneficial centralized function (see {{necessary}}) are sometimes mitigated by delegating that function's administration to a multi-stakeholder body -- an institution that includes representatives of the different kinds of parties that are affected by the system's operation ("stakeholders") in an attempt to make well-reasoned, legitimate, and authoritative decisions.

The most widely-studied example of this technique is the administration of the DNS, which as a “single source of truth” exhibits beneficial centralization in its naming function, as well as the operation of the system overall. To mitigate operational centralization, multiple root servers that are administered by separate operators (themselves diverse in geography) and a selection of corporate entities, non-profits, and government bodies from many jurisdictions and affiliations carry this task out. Administration of the name space itself is overseen by [the Internet Corporation for Assigned Names and Numbers (ICANN)](https://www.icann.org/resources/pages/governance/governance-en), a global multi-stakeholder body with representation from end users, governments, operators, and others.

Another example is the administration of the Web's trust model, implemented by Web browsers as relying parties and Certificate Authorities as trust anchors. To assure that all parties meet the operational and security requirements necessary to provide the desired properties, the [CA/Browser Forum](https://cabforum.org) was established as an oversight body that involves both of those parties as stakeholders.

Yet another example of multi-stakeholderism is the standardization of Internet protocols themselves. Because a specification effectively controls implementation behavior, the standardization process can be seen as a single point of control. As a result, Internet standards bodies like the IETF allow open participation and contribution, make decisions in an open and accountable way, have a well-defined process for making (and when necessary, appealing) decisions, considering the views of different stakeholder groups {{?RFC8890}}.

A major downside of this approach is that setup and ongoing operation of multi-stakeholder bodies is not trivial. Additionally, their legitimacy cannot be assumed, and may be difficult to establish and maintain (see, e.g., {{LEGITIMACY-MULTI}}). This concern is especially relevant if the function being coordinated is broad, complex, and/or contentious.


## Blockchains Are Not Magical {#distributed}

Increasingly, distributed consensus technologies (such as blockchain) are touted as a solution to centralization issues. A complete survey of this rapidly changing area is beyond the scope of this document, but we can generalise about their properties.

These techniques attempt to avoid centralization risk by distributing potentially centralized functions to members of a sometimes large pool of protocol participants. Proper performance of a function is typically guaranteed using cryptographic techniques (often, an append-only transaction ledger). A particular task's assignment to a node for handling usually cannot be predicted or controlled.

Sybil attacks (where enough participants coordinate their activity to affect the protocol's operation) are a major concern for these protocols. Diversity in the pool of participants is encouraged using indirect techniques such as proof-of-work (where each participant has to demonstrate significant consumption of resources) or proof-of-stake (where each participant has some other incentive to execute correctly).

Use of these techniques can create barriers to proprietary and inherited centralization. However, depending upon the application in question, concentration and platform centralization can still be possible.

Furthermore, distributed consensus technologies have several potential shortcomings that may make them inappropriate -- or at least difficult to use -- for many Internet applications, because their use conflicts with other important goals:

1. Distributed consensus has significant implications for privacy. Because activity (such as queries or transactions) are shared with many unknown parties (and often publicly visible due to the nature of the blockchain) they have very different privacy properties than traditional client/server protocols. Potential mitigations (e.g., Private Information Retrieval; see, e.g., {{PIR}}) are still not suitable for broad deployment.

2. Their complexity and "chattiness" typically result in significantly less efficient use of the network (often, to several orders of magnitude). When distributed consensus protocols use proof-of-work, energy consumption can become significant (to the point where some jurisdictions have banned its use).

3. Distributed consensus protocols are still not proven to scale to the degree expected of successful Internet protocols. In particular, relying on unknown third parties to deliver functionality can introduce significant variability in latency, availability, and throughput. This is a marked change for applications with high expectations for these properties (e.g., consumer-oriented Web sites).

4. By design, distributed consensus protocols diffuse responsibility for a function among several difficult-to-identify parties. While this may be an effective way to prevent some kinds of centralization, it also means that making someone accountable for how the function is performed difficult, and often impossible. While the protocol might use cryptographic techniques to assure correct operation, they may not capture all requirements, and may not be correctly used by the protocol designers.

5. Distributed consensus protocols typically rely on cryptography for identity, rather than trusting a third party's assertions about identity. When a participant loses their keys, recovering their identity is not possible -- an unacceptable usability impact for many applications.

It is also important to recognise that a protocol or an application can use distributed consensus for some functions, but still have centralization risk elsewhere -- either because those functions cannot be decentralized (most commonly, rendezvous and global naming; see {{necessary}}) or because the service provider has chosen not to because of the associated costs and lost opportunities.

Even when distributed consensus is used exclusively for all technical functions of a service, some coordination is still necessary -- whether that be through governance of the function itself, creation of shared implementations, or documentation of shared wire protocols. That represents centralization risk, just at a different layer (inherited or platform).

These potential shortcomings do not rule out the use of distributed consensus technologies in every instance. They do, however, caution against relying upon these technologies to avoid centralization uncritically.


# What Should Internet Standards Do? {#considerations}

Centralization is driven by powerful forces -- both economic and social -- as well as the network effects that come with Internet scale. Because permissionless innovation is a core value for the Internet, and yet much of the centralization seen on the Internet is performed by proprietary platforms that take advantage of this nature, the controls available to standards efforts are very limited.

While standards bodies on their own cannot prevent centralization, there are meaningful steps that can be taken to prevent some functions from exhibiting centralization. There are also valuable contributions that standards efforts can make to other relevant forms of regulation.


## Be Realistic {#target}

Some kinds of centralization risk are relatively easy to manage in standards efforts. For example, if a proprietary protocol were to be proposed to the IETF, it would be rejected out of hand. There is a growing body of knowledge and experience with beneficial centralization, and a strong inclination to reuse existing infrastructure where possible. As discussed above, encryption is often a way to manage inherited centralization, and has become the norm in standard protocols. These responses are appropriate ways for Internet standards to manage centralization risk.

However, preventing concentration and platform centralization is much more difficult in standards efforts. Because we have no “protocol police”, it’s not possible to demand that someone stop building a proprietary service using a purportedly federated protocol. We also cannot stop someone from building centralized services “on top” of standard protocols without abandoning architectural goals like permissionless innovation.

Therefore, committing significant resources to scrutinizing protocols for latent centralization risk -- especially for concentration and platform risks -- is unlikely to be effective in preventing Internet centralization. Almost all existing Internet protocols -- including IP, TCP, HTTP, and DNS -- suffer some form of concentration or platform centralization. Refusing to standardize a newer protocol because it faces similar risks would not be equitable, proportionate, or effective.

When we do find centralization risk, we should consider its relationship with other goals, such as privacy. While there is rarely a pure tradeoff between two abstract goals such as these, when it surfaces attention should be paid to how effective architectural regulation (such as a standards effort) is in achieving each goal. In this example, a technical mechanism might be much more effective at improving privacy, whereas centralization might be better controlled by other regulators -- leading to the conclusion that the standards effort should focus on privacy.


## Decentralize Proprietary Functions {#up}

It is worthwhile to create specifications for functions that are currently only satisfied by proprietary providers. By building open specifications on top of already established standards, centralization of emerging Internet functions can be avoided.

A common objection to such efforts is that adoption is voluntary, not mandatory; there are no "standards police" to mandate their use or enforce correct implementation. For example, specifications like {{W3C.CR-activitystreams-core-20161215}}) have been available for some time without broad adoption by social networking providers.

However, while standards aren't mandatory, legal regulation is, and regulators around the globe are now focusing their efforts on the Internet. In particular, legal mandates for interoperability are increasingly discussed as a remedy for competition issues (see, e.g., {{OECD}}).

As such, emerging regulation presents an opportunity to create new specifications to decentralize these functions, backed by a legal mandate in combination with changing norms and the resulting market forces {{NEW-CHICAGO}}.

If the Internet community does not produce specifications for these mandates to reference, it is likely that the need will be filled by other means -- most likely, with less transparency, more narrow input, limited experience, and without reference to the Internet’s architectural goals.


## Build Robust Ecosystems {#balance}

To minimize inherited centralization risk, standards-defined functions should have an explicit goal of broad, diverse implementation and deployment so that users have as many choices as possible.

{{Section 2.1 of ?RFC5218}} explores some factors in protocol design that encourage this outcome.

This goal can also be furthered by ensuring that the cost of switching to a different implementation or deployment is as low as possible to facilitate subsequent substitution. This implies that the standard is functionally complete and specified precisely enough to result in meaningful interoperability.

The goals of completeness and diversity are sometimes in tension. If a standard is extremely complex, it may discourage implementation diversity because the cost of a complete implementation is too high (consider: Web browsers). On the other hand, if the specification is too simple, it may not offer enough functionality to be complete, and the resulting proprietary extensions may make switching difficult (see {{evolution}}).

Furthermore, if a new protocol is perceived as completely commoditized (so that no implementation can differentiate itself, and there is no barrier to switching), it may have difficulty achieving broad implementation -- at least by commercial entities.

Balancing these factors is difficult, but is often helped by community building and good design -- in particular, appropriate use of layering.


## Limit Intermediary Power {#intermediation}

Some functions might see substantial benefits if intermediation -- i.e., adding a new party to communication to perform a function -- is introduced. When used well, intermediation can help improve:

* _Efficiency_: Many functions on the Internet are significantly more efficient when performed at a higher scale. For example, a Content Delivery Network can offer services at a fraction of the financial and environmental cost that would otherwise be paid by someone serving content themselves, because of the scale they operate at.

* _Complexity_: Completely disintermediating communication can shift the burden of functions onto endpoints. This can cause increased cognitive load for users; for example, compare commercial social networking platforms with self-hosted efforts.

* _Specialization_: Having a function concentrated into relatively few hands can improve outcomes because of the resulting specialization. For example, services overseen by professional administrators are often seen to have a better security posture and improved availability.

* _Privacy_: For some functions, user privacy can be improved by concentrating their activity to prevent individual behaviors from being discriminated from each other.{{MIX}} Intermediation can also enforce functional boundaries -- for example, to reduce the need for users to trust potentially malicious endpoints, as seen in the so-called “oblivious” protocols (e.g., {{?I-D.pauly-dprive-oblivious-doh}}) that allow end users to hide their identity from services, while still accessing them.

However, introducing an intermediary role adds concentration and platform centralization risk to Internet protocols, because it brings opportunities for control and observation. While (as discussed above) standards efforts have a very limited capability to prevent or control these types of centralization, constraints on intermediary functions can prevent at least the most egregious outcomes.

As a result, intermediaries should only be interposed as a result of the positive action of at least one endpoint, and should have their ability to observe or control communication limited to what is necessary to perform their intended function.

For example, early deployments of HTTP allowed intermediaries to be interposed by the network without knowledge of the endpoints, and those intermediaries could see and change the full content of traffic by default -- even when they are only intended to perform basic functions such as caching. Because of the introduction of HTTPS and the CONNECT method (see {{Section 9.3.6 of HTTP}}), combined with efforts to encourage its adoption, those intermediaries are now required to be explicitly interposed by one endpoint.

See {{?I-D.thomson-tmi}} for more guidance on protocol intermediation.

The term "intermediary" is also used (often in legal and regulatory contexts) more broadly than it has been in protocol design; for example, an auction Web site intermediates between buyers and sellers is considered an intermediary, even though it is not formally an intermediary in HTTP (see {{Section 3.7 of HTTP}}). Protocol designers can address the centralization risk associated with this kind of intermediation by standardising the function, rather than restricting the capabilities of the underlying protocols; see {{up}}.


## Avoid Over-Extensibility {#evolution}

An important feature of Internet protocols is their ability to evolve, so that they can meet new requirements and adapt to new conditions without requiring a “flag day” to upgrade implementations. Typically, protocols accommodate evolution through extension mechanisms, which allow optional features to be added over time in an interoperable fashion.

However, protocol extensions can also increase the risk of platform centralization if a powerful entity can change the target for meaningful interoperability by adding proprietary extensions to a standard protocol. This is especially true when the core standard does not itself provide sufficient utility on its own.

For example, the SOAP protocol's {{SOAP}} extreme flexibility and failure to provide significant standalone value allowed vendors to require use of their preferred extensions, favouring those who had more market power.

Therefore, standards efforts should focus on providing concrete utility to the majority of their users as published, rather than being a “framework” where interoperability is not immediately available.  Internet protocols should not make every aspect of their operation extensible; extension points should be reasoned, appropriate boundaries for flexibility and control. When a protocol defines extension points, they should not allow an extension to declare itself to be mandatory-to-interoperate, as that pattern invites abuse.


# Security Considerations

This document does not have direct security impact on Internet protocols. However, failure to consider centralization risks might cause a myriad of security issues.


--- back


# Acknowledgements

This document benefits from discussions with Brian Trammell during our shared time on the Internet Architecture Board.

Thanks to Jari Arkko and Eliot Lear for their comments and suggestions.

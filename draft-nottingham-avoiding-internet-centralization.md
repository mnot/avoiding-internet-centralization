---
title: Centralization, Decentralization, and Internet Standards
abbrev: Centralization
docname: draft-nottingham-avoiding-internet-centralization-latest
date: {DATE}
category: info

ipr: trust200902
area: General
workgroup:
keyword: decentralization
keyword: concentration
keyword: regulation
keyword: governance

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
    display: BARAN
    target: https://www.rand.org/pubs/research_memoranda/RM3420.html
    title: "On Distributed Communications: Introduction to Distributed Communications Networks"
    date: 1964
    author:
     -
       name: Paul Baran
       organization: RAND Corporation
  HTTP: RFC9110
  SOAP: W3C.REC-soap12-part0-20070427
  SCALE-FREE:
    display: BARABASI
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
    refcontent: SCIENCE, Vol. 286, No. 15, p. 509
  INTERMEDIARY-INFLUENCE:
    display: JUDGE
    target: https://scholarship.law.columbia.edu/faculty_scholarship/1856
    title: Intermediary Influence
    date: 2014
    author:
     -
        ins: K. Judge
        name: Kathryn Judge
        organization: Columbia Law School
    refcontent: University of Chicago Law Review, Vol. 82, p. 573
  INTERDEPENDENCE:
    display: FARRELL
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
    refcontent: International Security, Vol. 44, No. 1, p. 42
  MOXIE:
    target: https://signal.org/blog/the-ecosystem-is-moving/
    title: "Reflections: The ecosystem is moving"
    date: 10 May 2016
    author:
     -
       ins: M. Marlinspike
       name: Moxie Marlinspike
       organization: Signal
  MULTISTAKEHOLDER:
    display: PALLADINO
    title: "Legitimacy, Power, and Inequalities in the Multistakeholder Internet Governance"
    date: 2020
    author:
     -
       name: Nicola Palladino
     -
       name: Nauro Santaniello
    target: https://link.springer.com/book/10.1007/978-3-030-56131-4
  NEW-CHICAGO:
    display: LESSIG
    title: "The New Chicago School"
    date: June 1998
    author:
     -
       name: Laurence Lessig
    refcontent: "Journal of Legal Studies, Vol. 27"
    target: https://www.journals.uchicago.edu/doi/10.1086/468039
  POLYCENTRIC:
    display: ALIGIA
    title: "Polycentricity: From Polanyi to Ostrom, and Beyond"
    date: April 2012
    author:
     -
       name: Paul D. Aligia
     -
       name: Vlad Tarko
    target: https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2149165
    refcontent: "Governance: An International Journal of Policy, Administration, and Institutions, Vol. 25, No. 2, p. 237"
  PIR:
    display: OLUMOFIN
    title: Revisiting the Computational Practicality of Private Information Retrieval
    date: 2010
    author:
     -
      name: Femi Olumofin
     -
      name: Ian Goldberg
    target: https://link.springer.com/chapter/10.1007/978-3-642-27576-0_13
  ACCESS:
    display: VESTAGER
    title: Defending Competition in a Digitised World, Address at the European Consumer and Competition Day
    date: 4 April 2019
    target: https://wayback.archive-it.org/12090/20191129202059/https://ec.europa.eu/commission/commissioners/2014-2019/vestager/announcements/defending-competition-digitised-world_en
    author:
     -
      name: Margrethe Vestager
  SUCCESS:
    display: KENDE
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
    display: CHAUM
    title: Untraceable Electronic Mail, Return Addresses, and Digital Pseudonyms
    date: 1 February 1981
    target: https://dl.acm.org/doi/10.1145/358549.358563
    author:
     -
      name: David L. Chaum
    refcontent: Communications of the ACM, Vol. 24, No. 2
  FEDERALIST-51:
    display: MADISON
    title: The Structure of the Government Must Furnish the Proper Checks and Balances Between the Different Departments
    date: 8 February 1788
    author:
     -
       name: James Madison
    refcontent: The Federalist Papers, No. 51
  ATTRACTIVE-PROFITS:
    display: CHRISTENSEN
    title: The Law of Conservation of Attractive Profits
    date: February 2004
    author:
     -
       name: Clayton Christensen
    refcontent: Harvard Business Review, "Breakthrough Ideas for 2004"
  ACTIVITYSTREAMS: W3C.CR-activitystreams-core-20161215
  CIRCULAR-CONUNDRUM:
    display: SPULBER
    title: "Solving The Circular Conundrum: Communication And Coordination In Internet Markets"
    date: 2010
    author:
     -
      name: Daniel F. Spulber
    refcontent: "Northwestern University Law Review, Vol. 104, No. 2"
    target: https://wwws.law.northwestern.edu/research-faculty/clbe/workingpapers/documents/spulber_circularconundrum.pdf
  YAO:
    title: Protocols for secure computations
    date: November 1982
    author:
     -
      name: Andrew C. Yao
    target: https://dl.acm.org/doi/10.5555/1382436.1382751
    refcontent: SFCS '82
  ENPA:
    title: Exposure Notification Privacy-preserving Analytics (ENPA) White Paper
    date: April 2021
    author:
     -
      organization: Apple
     -
      organization: Google
    target: https://covid19-static.cdn-apple.com/applications/covid19/current/static/contact-tracing/pdf/ENPA_White_Paper.pdf
  PRIO:
    title: "Prio: Private, Robust, and Scalable Computation of Aggregate Statistics"
    date: March 2017
    author:
     -
      name: Henry Corrigan-Gibbs
     -
      name: Dan Boneh
    target: https://crypto.stanford.edu/prio/paper.pdf
  AMBITION:
    display: SCHNEIDER
    title: "Decentralization: an incomplete ambition"
    date: 2019
    author:
     -
      name: Nathan Schneider
    target: https://osf.io/m7wyj/
    refcontent: "Journal of Cultural Economy, Vol. 12, No. 4"
  AREWEDECENTRALIZEDYET:
    title: "Are We Decentralized Yet?"
    date: 2022
    author:
      -
       organization: bitcoinera
    target: https://bitcoinera.app/arewedecentralizedyet/
  PERSPECTIVE:
    display: BODO
    title: "Decentralization: a multidisciplinary
perspective"
    date: 16 June 2021
    author:
     -
      name: Balázs Bodó
      organization: University of Amsterdam
     -
      name: Jaya Klara Brekke
      organization: Durham University
     -
      name: Jaap-Henk Hoepman
      organization: Radboud University
    target: https://doi.org/10.14763/2021.2.1563
    refcontent: "Internet Policy Review, Vol. 10, No. 2"
  MUSIANI:
    title: "Alternative Technologies as Alternative Institutions: The Case of the Domain Name System"
    date: 2016
    author:
      - name: Francesca Musiani
    target: https://link.springer.com/chapter/10.1057/9781137483591_4
    refcontent: "The Turn to Infrastructure in Internet Governance"
  STRUCTURELESS:
    display: FREEMAN
    title: The Tyranny of Structurelessness
    date: 1972
    author:
     -
      name: Jo Freeman
    target: https://www.jstor.org/stable/41035187
    refcontent: Berkeley Journal of Sociology, Vol. 17
  ISOC:
    title: Consolidation in the Internet Economy
    date: 2019
    author:
      -
       organization: Internet Society
    target: https://future.internetsociety.org/2019/
    refcontent: Internet Society Global Internet Report

--- abstract

Despite being designed and operated as a decentralized network-of-networks, the Internet is continuously subjected to forces that encourage centralization.

This document offers a definition of centralization, explains why it is undesirable, identifies different types of it, catalogues limitations of common approaches to decentralization, and explores what Internet standards efforts can do to address it.

--- middle

# Introduction

The Internet has succeeded in no small part because of its purposeful avoidance of any single controlling entity. Originating in a desire to prevent a single technical failure from having a wide impact {{RAND}}, this stance has also enabled the Internet’s rapid adoption and broad spread. The Internet can accommodate a spectrum of requirements and is now positioned as a global public good because joining, deploying an application on, or using the Internet does not require permission from or ceding control to another entity.

While avoiding centralization of the Internet remains a widely shared goal, achieving it consistently has proven difficult. Today, many successful protocols and applications on the Internet operate in a centralized fashion -- to the point where some proprietary, centralized services have become so well-known that they are commonly mistaken for the Internet itself. Even when protocols incorporate techniques intended to prevent centralization, economic and social factors can drive users to prefer centralized solutions built with or on top of supposedly decentralized technology.

These difficulties call into question what role architectural regulation -- in particular, that performed by open standards bodies such as the IETF -- should play in preventing, mitigating, and controlling Internet centralization. This document discusses aspects of centralization that relate to Internet standards efforts, and argues that while the IETF may not be able to prevent centralization, there are still meaningful steps we can take to counteract it.

{{centralization}} defines centralization, explains why it is undesirable, and surveys some kinds of centralization seen on the Internet. {{decentralization}} explores decentralization and highlights some relevant techniques, along with their limitations. Finally, {{considerations}} considers the role that Internet standards play in avoiding centralization and mitigating its effects.

The primary audience for this document is the engineers who design and standardize Internet protocols. However, designers of proprietary protocols can benefit from considering aspects of centralization, especially if they intend their protocol to be considered for eventual standardisation. Likewise, policymakers can use this document to help identify and remedy inappropriately centralized protocols and applications.


# Centralization {#centralization}

This document defines "centralization" as the ability of a single entity or a small group of them to exclusively observe, capture, control, or extract rent from the operation or use of an Internet function.

Here, "entity" could be a single person, a corporation, or a government. It does not include an organisation that operates in a manner that effectively mitigates centralization (see, e.g., {{multi}}).

"Internet function" is defined broadly. It might be an enabling protocol already defined by standards, such as IP {{?RFC791}}, BGP {{?RFC4271}}, TCP {{?RFC793}}, or HTTP {{HTTP}}. It might also be a proposal for a new enabling protocol, or an extension to an existing one.

However, the Internet's functions are not limited to standards-defined protocols. User-visible applications built on top of standard protocols are also vulnerable to centralization -- for example, social networking, file sharing, financial services, and news dissemination. Likewise,  networking equipment, hardware, operating systems, and software act as enabling technologies that can exhibit centralization. The supply of Internet connectivity to end users in a particular area or situation can also be subject to the forces of centralization, as can supply of transit between networks (so called "Tier 1" networks).

Centralization is not a binary condition; it is a continuum. At one extreme, a function absolutely controlled by a single entity (see {{direct}}) represents complete centralization; at the other extreme, a function whose value can be realised by any two parties without the possibility of any external interference or influence represents complete decentralization (sometimes referred to as "distributed" or "peer-to-peer").

While a few functions might occupy the ends of this spectrum, most reside somewhere between the extremes. Therefore, it is often useful to consider the amount of _centralization risk_ associated with a function, depending on the scale, scope, and nature of the influences on it. Note that a function might have more than one source of centralization risk, each with its own characteristics.

Centralization risk is strongest when it affects the entire Internet. However, it can also be present when a substantial portion of the Internet's users lack options for a function. For example, if there is only one provider for a function in a region or legal jurisdiction, that function is effectively centralized for those users.

Centralization risk is most obviously created by the direct assignment of a role to a single entity, but it is also created when a single entity takes on that role for other reasons. For example, friction against switching to a substitute provider of a function often leads to concentration (see {{indirect}}). If switching requires a significant amount of time, resources, expertise, coordination, loss of functionality, or effort, centralization risk is indicated. Conversely, a function based on a well-defined, open specification designed to minimize switching costs might be considered to have less centralization risk even when there are only a few large providers.

This definition of centralization focuses largely upon the relationships between parties to communication, rather than systems design. For example, a cloud service might use decentralized techniques to improve its resilience but still be operated by a single entity, thereby exhibiting the kind of centralization that this document is concerned with. A failure due to a cut cable, power outage, or failed server is qualitatively different from the issues encountered when a core Internet function has a gatekeeper.

As a result, the concept of availability is distinct from centralization, and any relationship between them cannot be assumed without careful analysis of where and how centralization occurs. Centralized systems might be more available due to factors like the resources available to them, but also have greater impact when they have a fault; decentralized systems might be more resilient in the face of local failures, but less able to react to systemic issues.

For example, a large variety of Web sites might depend upon a cloud hosting provider or content delivery network; if it were to become unavailable (whether for technical or other reasons), many people's experience of the Internet might be disrupted. Likewise, a mobile Internet access provider might have an outage that affects hundreds, thousands, or more of its users. In both cases, centralization is not engaged by the loss of availability or its scale, but it well might be if the parties relying on the function don't have reasonable options to switch to if they are unhappy with the availability of the service provided, or if friction against switching to an alternative is too great.

Also, it is important to distinguish centralization from anti-competitive concerns (also known as "anti-trust"). While there are many interactions between these concepts and making the Internet more competitive may be a motivation for avoiding centralization, only courts have the authority to define a relevant market and determine that behaviour is anti-competitive. Furthermore, what might be considered undesirable consolidation by the technical community might not attract competition regulation, and conversely what might attract competition regulation might not be of great concern to the technical community if other mitigations are felt to be adequate.


## When Centralization is Undesirable {#why}

There are three overarching reasons why centralization of Internet functions can be concerning.

First, the Internet's very nature is incompatible with centralization. As a "large, heterogeneous collection of interconnected systems" {{?BCP95}} the Internet is often characterised as a "network of networks". These networks relate as peers who agree to facilitate communication, rather than having a relationship of subservience to others' requirements or coercion by them. This focus on independence of action carries through the way the network is architected -- for example, in the concept of an "autonomous system".

Second, when a third party has unavoidable access to communications, the informational and positional advantages gained allow observation of behaviour (the "panopticon effect") and shaping or even denial of behaviour (the "chokepoint effect") {{INTERMEDIARY-INFLUENCE}} -- capabilities that those parties (or the states that have authority over them) can use for coercive ends {{INTERDEPENDENCE}} or even to disrupt society itself. Just as good governance of states requires separation of powers {{FEDERALIST-51}}, so too does good governance of the Internet require that power not be concentrated in one place without appropriate checks and balances.

Finally, centralization of a function can have deleterious effects on the Internet itself, including:

* _Limiting Innovation_: Centralization can preclude the possibility of "permissionless innovation" -- the ability to deploy new, unforeseen applications without requiring coordination with parties other than those you are communicating with.

* _Constraining Competition_: The Internet and its users benefit from robust competition when applications and services are available from many providers -- especially when those users can build their own applications and services based upon interoperable standards. When a centralized service or platform must be used because no substitutes are suitable, it effectively becomes an essential facility, which encourages abuse of power.

* _Reducing Availability_: Availability of the Internet (and applications and services built upon it) improves when there are many ways to obtain access. While centralized services' availability can benefit from the focused attention that their elevated role requires, failure of a large, centralized provider can have a disproportionate impact on availability.

* _Creating Monoculture_: The scale available to a centralized service or application can magnify minor flaws in features to a degree that can have broad consequences. For example, a single codebase for routers elevates the impact of a bug or vulnerability; a single recommendation algorithm for content can have severe social impact. Diversity in these functions’ implementation leads to a more robust outcome when viewed systemically. {{POLYCENTRIC}}

* _Self-Reinforcement_: As widely noted (see, e.g., {{ACCESS}}), a centralized service’s access to data allows it the opportunity to make improvements to its offerings, while denying such access to others.

See also {{SUCCESS}} for further exploration of how centralization can affect the Internet.

As discussed below in {{necessary}}, not all centralization is undesirable or avoidable. {{AMBITION}} notes that "centralized structures can have virtues, such as enabling publics to focus their limited attention for oversight, or forming a power bloc capable of challenging less-accountable blocs that might emerge. Centralized structures that have earned widespread respect in recent centuries – including governments, corporations, and nonprofit organizations – have done so in no small part because of the intentional design that went into those structures."

With that in mind, centralization risk on the Internet is most concerning when it is not broadly held to be necessary, when it has no checks, balances, or other mechanisms of accountability, when it selects "favourites" which are difficult (or impossible) to displace, and when it has the damaging effects outlines above, or the potential for them.


## Kinds of Centralization {#kinds}

Centralization on the Internet is not uniform; it presents in a variety of ways, depending on its relationship to the function in question and underlying causes. The subsections below describe different aspects of Internet centralization.


### Proprietary Centralization {#direct}

Creating of a protocol or application with a fixed role for a specific party is the most straightforward kind of centralization. Many messaging, videoconferencing, chat, social networking, and similar applications operate in this fashion currently.

Because they allow control by a single entity, proprietary protocols are often considered simpler to design, more amenable to evolution, and more likely to meet user needs {{MOXIE}}, compared to decentralized alternatives. However, they have corresponding centralization risk -- if the function has no alternative providers, or switching to those providers is too difficult, its users are "locked in."

Proprietary protocols and applications are not considered as being part of the Internet per se; instead, they are more properly characterized as being built on top of the Internet. The Internet architecture and associated standards do not regulate them, beyond the constraints that the underlying protocols (e.g., TCP, IP, HTTP) impose.


### Beneficial Centralization {#necessary}

Some protocols and applications have goals that require the introduction of a centralized function. In doing so, they are explicitly relying on centralization to deliver a particular benefit.

For example, a function that needs a single, globally coordinated “source of truth” is by nature centralized -- such as in the Domain Name System (DNS), which allows human-friendly naming to be converted into network addresses in a globally consistent fashion.

Another function exhibiting beneficial centralization is IP addresses allocation. Internet routing requires addresses to be allocated uniquely, but if a single government or company captured the addressing function, the entire Internet would be at risk of abuse by that entity. Similarly, the need for coordination in the Web's trust model brings centralization risk, because of the Certificate Authority's role in communication between clients and servers.

Protocols that need to solve the "rendezvous problem" to coordinate communication between two parties who are not in direct contact also suffer from this kind of centralization. For example, chat protocols need to coordinate communication between two parties that wish to talk; while the actual communication can be direct between them (so long as the protocol facilitates that), the endpoints' mutual discovery typically requires a third party at some point. From the perspective of those two users, the rendezvous function has centralization risk.

Likewise, when a function requires governance to realize common goals and protect minority interests, a "choke point" is naturally formed by the chosen governance mechanism, increasing centralization risk. For example, defining and applying a content moderation policy both have centralization risk.

Deciding what is beneficial is a judgment call. Some protocols cannot function without a centralized function; others might be significantly enhanced for certain use cases if a function is centralized, or might merely be more efficient. Such judgments should be made in light of established architectural principles and how benefits accrue to end users.

When beneficial centralization is present, Internet protocols often attempt to mitigate the associated risks using measures such as federation (see {{federation}}) and multi-stakeholder governance (see {{multi}}). Protocols that successfully mitigate beneficial centralization are often reused, to avoid the considerable cost and risk of re-implementing those mitigations. For example, if a protocol requires a coordinated, global naming function, reusing the Domain Name System is usually preferable to establishing a new system.


### Concentrated Centralization {#indirect}

Even when a function avoids proprietary centralization and mitigates any beneficial centralization present, it might become centralized in practice when external factors influence its deployment, so that few or even just one entity provides the function. This is often referred to as "concentration." Economic, legal, and social factors that encourage use of a central function despite the absence of such a requirement in the protocol itself can cause concentration.

Often, the factors driving concentration are related to the network effects that are so often seen on the Internet. While in theory every node on the Internet is equal, in practice some nodes are much more connected than others: for example, just a few sites drive much of the traffic on the Web. While expected and observed in many kinds of networks, network effects award asymmetric power to nodes that act as intermediaries to communication. {{SCALE-FREE}}

For example, social networking is an application that is currently supplied by a few proprietary platforms despite standardization efforts (see, e.g., {{ACTIVITYSTREAMS}}), because of the powerful network effects associated. While there has been some competition in social networking, a group of people who wish to communicate are often locked in by the choices that their peers make, because of the coordination required to move to a new service.

See {{ISOC}} for a deeper exploration of concentration.

Concentration is difficult to avoid in protocol design, and federated protocols are particularly vulnerable to it (see {{federation}}).


### Inherited Centralization {#network}

Most Internet protocols and applications depend on other, "lower-layer" protocols and their implementations. The features, deployment, and operation of these dependencies can surface centralization into functions and applications built "on top" of them.

For example, the network between endpoints can introduce centralization risk to application-layer protocols, because it is necessary for communication and therefore has power over it. A network might block access to, slow down, or change the content of various application protocols or specific services for financial, political, operational, or criminal reasons, creating pressure to use other services, which can cause their centralization.

Likewise, having only a single implementation of a protocol is an inherited centralization risk, because applications that use it are vulnerable to the control it has over their operation. Even if it is Open Source, there might be inherited centralization if there are factors that make forking difficult (for example, the cost of maintaining that fork).

Inherited centralization is often present when network effects restrict choices, but can also be created by legal mandates and incentives that restrict the options for a function (such as Internet access), its provision, or the range of implementations available.

Some kinds of inherited centralization can be prevented by enforcing layer boundaries through use of techniques like encryption. When the number of parties who have access to content of communication are limited, parties at lower layers can be prevented from interfering with and observing it. Although those lower-layer parties might still prevent communication, encryption also makes it more difficult to discriminate a target from other traffic.

Note that the prohibitive effect of encryption on inherited centralization is most pronounced when most (if not all) traffic is encrypted. See also {{?RFC7258}}.


### Platform Centralization {#platform}

The complement to inherited centralization is platform centralization -- where a function does not directly define a central role, but could facilitate centralization in the applications it supports.

For example, HTTP {{HTTP}} is not considered a centralized protocol; interoperable servers are  easy to instantiate, and multiple clients are available. It can be used without central coordination beyond that provided by DNS, as discussed above.

However, applications built on top of HTTP (as well as the rest of the “Web Platform”) often exhibit centralization (for example, social networking). HTTP is therefore an example of a platform for centralization -- while the protocol itself is not centralized, it facilitates the creation of centralized services and applications.

Like concentration, platform centralization is difficult to prevent with protocol design. Because of the layered nature of the Internet, most protocols allow considerable flexibility in how they are used, often in a way that it becomes attractive to form a dependency on one party’s operation.


# Decentralization {#decentralization}

While the term "decentralization" has a long history of use in economics, politics, religion, and international development, In {{RAND}}, Barans gave one of the first definitions relevant to computer networking, as a condition when "complete reliance upon a single point is not always required."

This seemingly straightforward technical definition hides several issues.

First, identifying what aspects of a protocol or application to decentralize and how to achieve it can be difficult, both because there are often many paths that can lead to a function's centralization, and because centralization sometimes only becomes evident after the function is deployed at scale.

For example, a cloud storage function might be implemented using a distributed consensus protocol, assuring that the failure of any single node will not affect the system's operation or availability. However, if it is operated by a single legal entity, that brings a very different kind of centralization risk, especially if there are few other options available, or if there is friction against choosing other options.

Another example is the Web, which was envisioned and widely held to be a decentralizing force in its early life. Its inherent platform centralization only became apparent when large sites successfully leveraged network effects for dominance of social networking, marketplaces, and similar functions.

Second, different parties might have good-faith differences on what "sufficiently decentralized" means based upon their beliefs, perceptions and goals. Just as centralization is a continuum, so is decentralization, and not everyone agrees one what the "right" level or type is, how to weigh different forms of centralization against each other, or how to weigh centralization against other architectural goals (such as security or privacy).

This is seen in the DNS as a single, global "source of truth" with inherent (if beneficial) centralization. The associated risk is mitigated through its administration by ICANN, a multistakeholder organization (see {{multi}}). While many believe that this arrangement is sufficient and might even have desirable qualities (such as the ability to impose community standards over the operation of the name space), others reject ICANN's oversight of the DNS as illegitimate, favouring decentralization based upon distributed consensus protocols rather than multistakeholderism. {{MUSIANI}}

Third, decentralization unavoidably involves adjustments to the power relationships between protocol participants, especially when decentralizing a function opens up the possibility of centralization elsewhere. As Schneider notes in {{AMBITION}}, decentralization "appears to operate as a rhetorical strategy that directs attention toward some aspects of a proposed social order and away from others", so "we cannot accept technology as a substitute for taking social, cultural, and political considerations seriously." Or, as more bluntly stated in {{PERSPECTIVE}}, "without governance mechanisms in place, nodes may collude, people may lie to each other, markets can be rigged, and there can be significant cost to people entering and exiting markets."

For example, while blockchain-based cryptocurrencies might address the centralization inherent in traditional currencies through technical means, the concentration of power that many exhibit in terms of voting/mining power, distribution of funds, and diversity of codebase causes some to question how decentralized they actually are. {{AREWEDECENTRALIZEDYET}} The lack of formal structures brings an opportunity for latent, informal power structures that have their own risks -- including centralization. {{STRUCTURELESS}}

In practice, this means that decentralizing a function requires considerable work, is inherently political, and involves a large degree of uncertainty about the outcome. In particular, if one considers decentralization as a larger social goal (in the spirit of how the term is used in other, non-computing contexts), merely rearranging technical functions may lead to frustration. "A distributed network does not automatically yield an egalitarian, equitable or just social, economic, political landscape." {{PERSPECTIVE}}


## Decentralization Techniques {#techniques}

In the context of Internet standardization, decentralization is implemented as a two-step process: assessing the nature of centralization risk, followed by the application of techniques to reduce or mitigate it. The subsections below examine some of these techniques.

Choosing the appropriate techniques for decentralization requires balancing the goals of the function against centralization risk, because completely precluding all forms of centralization through technical means is rarely achievable. When performed properly, decentralization might produce an outcome that still has centralization risk, but that risk should be understood, acceptable, and, where possible and appropriate, mitigated.

Notably, decentralization does not require that provision of a function need be distributed in a particular fashion, or to a particular degree. For example, the Domain Name System {{?RFC1035}} is widely agreed to have acceptable centralization risk, despite it being provided by a limited set of entities.

While using these techniques can reduce centralization risk or make a function less amenable to some kinds of centralization, none are adequate to avoid centralization completely. They are also not indicators of whether a protocol is centralized without further analysis.


### Federation {#federation}

A widely known technique for managing centralization in Internet protocols is federation -- designing them in such a way that new instances of any centralized function are easy to create and can maintain interoperability and connectivity with other instances.

For example, SMTP {{?RFC5321}} is the basis of the e-mail suite of protocols, which has two functions that have centralization risk:

1. Giving each user a globally unique address, and
2. Routing messages to the user, even when they change network locations or become disconnected for long periods of time.

E-mail reuses DNS to help mitigate the first risk. To mitigate the second, it defines a specific role for routing users' messages, the Message Transfer Agent (MTA). By allowing anyone to deploy an MTA and defining rules for interconnecting them, the protocol's users avoid a requirement for a single central router.

Users can (and often do) choose to delegate that role to someone else, or run their own MTA. However, running your own mail server has become difficult, because of the likelihood of a small MTA being classified as a spam source. Because large MTA operators are widely known and have greater impact if their operation is affected, they are less likely to be classified as such, concentrating the protocol’s operation (see {{indirect}}).

Another example of a federated Internet protocol is XMPP {{?RFC6120}}, supporting "instant messaging" and similar functionality. Like e-mail, it reuses DNS for naming and requires federation to facilitate rendezvous of users from different systems.

While some deployments of XMPP do support truly federated messaging (i.e., a person using service A can interoperably chat with someone using service B), many of the largest do not. Because federation is voluntary, some operators captured their users into a single service, denying them the benefits of global interoperability.

The examples above illustrate that, while federation can be a useful technique to avoid proprietary centralization and manage beneficial centralization, it does not prevent concentration or platform centralization. If a single entity can capture the value provided by a protocol, they may use the protocol as a platform to get a “winner take all” outcome -- a significant risk with many Internet protocols, since network effects often promote such outcomes. Likewise, external factors (such as spam control) might naturally “tilt the table” towards a few operators.


### Multi-Stakeholder Governance {#multi}

Protocol designers sometime mitigate the risks associated with a beneficial centralized function (see {{necessary}}) by delegating that function's governance to a multi-stakeholder body -- an institution that includes representatives of the different kinds of parties that are affected by the system's operation ("stakeholders") in an attempt to make well-reasoned, legitimate, and authoritative decisions.

The most widely studied example of this technique is the governance of the DNS, which as a “single source of truth” exhibits beneficial centralization in its naming function, as well as the operation of the system overall. To mitigate operational centralization, multiple root servers that are administered by separate operators (themselves diverse in geography) and a selection of corporate entities, non-profits, and government bodies from many jurisdictions and affiliations carry this task out.The name space itself is administered by [the Internet Corporation for Assigned Names and Numbers (ICANN)](https://www.icann.org/resources/pages/governance/governance-en), a global multi-stakeholder body with representation from end users, governments, operators, and others.

Another example is the governance of the Web's trust model, implemented by Web browsers as relying parties and Certificate Authorities as trust anchors. To assure that all parties meet the operational and security requirements necessary to provide the desired properties, the [CA/Browser Forum](https://cabforum.org) was established as an oversight body that involves both parties as stakeholders.

Yet another example of multi-stakeholderism is the standardization of Internet protocols themselves. Because a specification controls implementation behavior, the standardization process can be seen as a single point of control. As a result, Internet standards bodies like the IETF allow open participation and contribution, make decisions in an open and accountable way, have a well-defined process for making (and when necessary, appealing) decisions, considering the views of different stakeholder groups {{?RFC8890}}.

A major downside of this approach is that setup and ongoing operation of multi-stakeholder bodies is not trivial. Additionally, their legitimacy cannot be assumed, and may be difficult to establish and maintain (see, e.g., {{MULTISTAKEHOLDER}}). This concern is especially relevant if the function being coordinated is broad, complex, and/or contentious.


### Distributed Consensus {#distributed}

Increasingly, distributed consensus technologies (such as the blockchain) are touted as a solution to centralization issues. A complete survey of this rapidly changing area is beyond the scope of this document, but we can generalise about their properties.

These techniques attempt to avoid centralization risk by distributing functions to members of a sometimes large pool of protocol participants. They typically guarantee proper performance of a function using cryptographic techniques (often, an append-only transaction ledger). A particular task's assignment to a node for handling usually cannot be predicted or controlled.

Sybil attacks (where a party or coordinated parties cheaply create enough protocol participants to affect how consensus is judged) are a major concern for these protocols. They encourage diversity in the pool of participants using indirect techniques, such as proof-of-work (where each participant has to show significant consumption of resources) or proof-of-stake (where each participant has some other incentive to execute correctly).

Use of these techniques can create barriers to proprietary and inherited centralization. However, depending upon the application in question, both concentration and platform centralization are still possible.

Furthermore, distributed consensus technologies have several potential shortcomings that may make them inappropriate -- or at least difficult to use -- for many Internet applications, because their use conflicts with other important goals:

1. Distributed consensus has significant implications for privacy. Because user activity (such as queries or transactions) is shared with many unknown parties (and often publicly visible due to the nature of the blockchain) they have very different privacy properties than traditional client/server protocols. Potential mitigations (e.g., Private Information Retrieval; see, e.g., {{PIR}}) are still not suitable for broad deployment.

2. Their complexity and "chattiness" typically result in significantly less efficient use of the network (often, to several orders of magnitude). When distributed consensus protocols use proof-of-work, energy consumption can become significant (to the point where some jurisdictions have banned its use).

3. Distributed consensus protocols are still not proven to scale to the degree expected of successful Internet protocols. In particular, relying on unknown third parties to deliver functionality can introduce significant variability in latency, availability, and throughput. This is a marked change for applications with high expectations for these properties (e.g., consumer-oriented Web sites).

4. By design, distributed consensus protocols diffuse responsibility for a function among several difficult-to-identify parties. While this may be an effective way to prevent some kinds of centralization, it also means that making someone accountable for how the function is performed is difficult, and often impossible. While the protocol might use cryptographic techniques to assure correct operation, they may not capture all requirements, and may not be correctly used by the protocol designers.

5. Distributed consensus protocols typically rely on cryptography for identity, rather than trusting a third party's assertions about identity. When a participant loses their keys, the process of recovering their identity exposes additional centralization risk.

It is also important to recognise that a protocol or an application can use distributed consensus for some functions, but still have centralization risk elsewhere -- either because those functions cannot be decentralized (most commonly, rendezvous and global naming; see {{necessary}}) or because the designer has chosen not to because of the associated costs and lost opportunities.

Even when distributed consensus is used for all technical functions of a service, some coordination is still necessary -- whether that be through governance of the function itself, creation of shared implementations, or documentation of shared wire protocols. That represents centralization risk, just at a different layer (inherited or platform).

These potential shortcomings do not rule out the use of distributed consensus technologies in every instance. They do, however, caution against uncritically relying upon these technologies to avoid centralization.


# What Should Internet Standards Do? {#considerations}

Centralization is driven by powerful forces -- both economic and social -- as well as the network effects that come with Internet scale. Because permissionless innovation is a core value for the Internet, and yet much of the centralization seen on the Internet is performed by proprietary platforms that take advantage of this nature, the controls available to standards efforts are very limited.

While standards bodies on their own cannot prevent centralization, the subsections below suggest meaningful steps that can be taken. There are also valuable contributions that standards efforts can make to other relevant forms of regulation.


## Be Realistic {#target}

Some kinds of centralization risk are easy to manage in standards efforts. For example, if a proprietary protocol were to be proposed to the IETF, it would be rejected out of hand. There is a growing body of knowledge and experience in managing the risk of beneficial centralization, and a strong inclination to reuse existing infrastructure where possible. As discussed above, encryption is often a way to manage inherited centralization, and has become the norm in standard protocols. These responses are appropriate ways for Internet standards to manage centralization risk.

However, mitigating concentration and platform centralization is much more difficult in standards efforts. Because we have no “protocol police”, it’s not possible to demand that someone stop building a proprietary service using a purportedly federated protocol. We also cannot stop someone from building centralized services “on top” of standard protocols without abandoning architectural goals like permissionless innovation. While the imprimatur of an Internet Standard is not without value, merely withholding it cannot prevent these kinds of centralization.

Therefore, committing significant resources to scrutinizing protocols for latent centralization risk -- especially for concentration and platform risks -- is unlikely to be effective in preventing Internet centralization. Almost all existing Internet protocols -- including IP, TCP, HTTP, and DNS -- exhibit concentration or platform centralization. Refusing to standardize a newer protocol because it faces similar risks would not be equitable, proportionate, or effective.

When we find centralization risk, we should consider its relationship with other architectural goals as we consider how to address it. In particular, attention should be paid to how effective standards (as a form of architectural regulation) is in achieving each goal.

For example, privacy is often more effectively ensured by ex ante technical constraints, as compared to ex post legal regulation. Conversely (as discussed) some kinds of centralization are likely better addressed through legal regulation. Thus, as a first order concern, a standards effort balancing these concerns might focus primarily on privacy. However, often these are not completely separable goals -- concentration can result in one or a few entities having greater volume and variety of data available exclusively to them, raising significant privacy and security concerns.


## Decentralize Proprietary Functions {#up}

It is worthwhile to create specifications for functions that are currently only satisfied by proprietary providers. By building open specifications on top of already established standards, an alternative to a centralized function can be created.

A common objection to such efforts is that adoption is voluntary, not mandatory; there are no "standards police" to mandate their use or enforce correct implementation. For example, specifications like {{ACTIVITYSTREAMS}}) have been available for some time without broad adoption by social networking providers.

However, while standards aren't mandatory, legal regulation is, and regulators around the globe are now focusing their efforts on the Internet. In particular, legal mandates for interoperability are increasingly discussed as a remedy for competition issues (see, e.g., {{OECD}}).

As such, appetite for Internet regulation presents not just a risk to the Internet; it also constitutes an opportunity for new specifications to decentralize these functions, backed by a legal mandate in combination with changing norms and the resulting market forces {{NEW-CHICAGO}}.

Successfully creating standards that work in concert with legal regulation is new ground for the IETF, presents many potential pitfalls, and will require new capabilities (especially liaison, likely originating in the IAB) and considerable effort. If the Internet community does not make that effort, it is likely that regulators will turn to other sources of interoperability specifications -- most likely, with less transparency, more narrow input, limited experience, and without reference to the Internet’s architectural goals.


## Evaluate New Decentralization Techniques {#new}

The decentralization techniques listed in {{techniques}} are not a closed set; wide interest has spurred development of new approaches, both in general and as solutions to specific problems.

For example, secure multi-party computation techniques (see, e.g., {{YAO}}) can be composed to allow parties to compute over private inputs without revealing them. Protocols like {{ENPA}} and {{PRIO}} use them to limit the information available to participants in protocols to realise privacy goals; as discussed in {{intermediation}} doing so might also counteract some kinds of centralization. However, as in other cases these techniques do not automatically preclude all centralization; such systems often still require trust, even if it is limited. That might cause other forms of centralization.

Whether use of these techniques (or others) can meaningfully counteract centralization is still uncertain. Standards bodies (including the IETF) can serve an important function by incubating them, applying (and, where necessary, developing) architectural guidelines for privacy, security, operability, and other goals, and assuring interoperability. When appropriate, publication on the standards track or as experimental can signal implementers, users, and regulators about their fitness.


## Build Robust Ecosystems {#balance}

To minimize inherited centralization risk, standards-defined functions should have an explicit goal of broad, diverse implementation and deployment so that users have as many choices as possible.

{{Section 2.1 of ?RFC5218}} explores some factors in protocol design that encourage this outcome.

This goal can also be furthered by ensuring that the cost of switching to a different implementation or deployment is as low as possible to facilitate subsequent substitution. This implies that the standard is functionally complete and specified precisely enough to result in meaningful interoperability.

The goals of completeness and diversity are sometimes in tension. If a standard is extremely complex, it may discourage implementation diversity because the cost of a complete implementation is too high (consider: Web browsers). On the other hand, if the specification is too simple, it may not offer enough functionality to be complete, and the resulting proprietary extensions may make switching difficult (see {{evolution}}).

Also worthy of attention are the underlying incentives for implementation. While a completely commoditized protocol might not allow implementations to differentiate themselves, they provide opportunities for specialization and improvement elsewhere in the value chain {{ATTRACTIVE-PROFITS}}. Well-timed standards efforts leverage these forces to focus proprietary interests on top of open technology, rather than as a replacement for it.

Balancing these factors to build robust ecosystems is difficult, but is often helped by community building and good design -- in particular, appropriate use of layering. It also requires continuing maintenance and evolution of protocols, to assure that they are still relevant and appropriate to their use.


## Control Delegation of Power {#intermediation}

Some functions might see substantial benefits if they are performed by a third party in communication. When used well, adding a new party to communication can improve:

* _Efficiency_: Many functions on the Internet are more efficient when performed at a higher scale. For example, a content delivery network can offer services at a fraction of the financial and environmental cost that someone serving content themselves would otherwise pay, because of the scale they operate at. Likewise, a two-sided market platform can introduce sizeable efficiencies over pair-wise buyer/seller trading {{CIRCULAR-CONUNDRUM}}.

* _Simplicity_: Completely disintermediating communication can shift the burden of functions onto endpoints. This can cause increased cognitive load for users; for example, compare commercial social networking platforms with self-hosted efforts.

* _Specialization_: Having a function concentrated into a few hands can improve outcomes because of the resulting specialization. For example, services overseen by professional administrators are often seen to have a better security posture and improved availability.

* _Privacy_: For some functions, user privacy can be improved by concentrating their activity to prevent individual behaviors from being discriminated from each other.{{MIX}} Introduction of a third party can also enforce functional boundaries -- for example, to reduce the need for users to trust potentially malicious endpoints, as seen in the so-called “oblivious” protocols (e.g., {{?RFC9230}}) that allow end users to hide their identity from services, while still accessing them.

However, introducing a new party to communication adds concentration and platform centralization risk to Internet protocols, because it brings opportunities for control and observation. While (as discussed above) standards efforts have a very limited capability to prevent or control these types of centralization, designing protocols with thoughtful constraints on third party functions can prevent at least the most egregious outcomes.

Most often, third parties are added to protocols as "intermediaries" or in designated "agent" roles. In general, they should only be interposed because of the positive action of at least one endpoint, and should have their ability to observe or control communication limited to what is necessary to perform their intended function.

For example, early deployments of HTTP allowed intermediaries to be interposed by the network without knowledge of the endpoints, and those intermediaries could see and change the full content of traffic by default -- even when they are only intended to perform basic functions such as caching. Because of the introduction of HTTPS and the CONNECT method (see {{Section 9.3.6 of HTTP}}), combined with efforts to encourage its adoption, those intermediaries are now required to be explicitly interposed by one endpoint.

See {{?I-D.thomson-tmi}} for more guidance on protocol intermediation.

The term "intermediary" is also used (often in legal and regulatory contexts) more broadly than it has been in protocol design; for example, an auction Web site intermediates between buyers and sellers is considered an intermediary, even though it is not formally an intermediary in HTTP (see {{Section 3.7 of HTTP}}). Protocol designers can address the centralization risk associated with this kind of intermediation by standardising the function, rather than restricting the capabilities of the underlying protocols; see {{up}}.


## Target Extensibility {#evolution}

An important feature of Internet protocols is their ability to evolve, so that they can meet new requirements and adapt to new conditions without requiring a “flag day” to upgrade implementations. Typically, protocols accommodate evolution through extension mechanisms, which allow optional features to be added over time in an interoperable fashion.

Extensibility can be viewed as a mechanism for decentralization as well -- by allowing uncoordinated evolution, it promotes autonomy and adaption of a function for local needs. However, protocol extensions can also increase the risk of platform centralization if a powerful entity can change the target for meaningful interoperability by adding proprietary extensions to a standard protocol. This is especially true when the core standard does not itself provide sufficient utility on its own.

For example, the SOAP protocol's {{SOAP}} extreme flexibility and failure to provide significant standalone value allowed vendors to require use of their preferred extensions, favouring those who had more market power.

Therefore, standards efforts should focus on providing concrete utility to the majority of their users as published, rather than being a “framework” where interoperability is not immediately available.  Internet protocols should not make every aspect of their operation extensible; extension points should be reasoned, appropriate boundaries for flexibility and control. When a protocol defines extension points, they should not allow an extension to declare itself to be mandatory-to-interoperate, as that pattern invites abuse.

Where extensions are allowed, attention should be paid to those that emerge; where appropriate, widely adopted extensions should be put through a standards process to assure that the result adheres to architectural principles and shared goals (see also {{up}}).


# Security Considerations

This document does not have a direct security impact on Internet protocols. However, failure to consider centralization risks might cause a myriad of security issues.


--- back


# Acknowledgements

This document benefits from discussions with Brian Trammell during our shared time on the Internet Architecture Board.

Thanks to Jari Arkko, Christian Huitema, Eliot Lear, and Martin Thomson for their comments and suggestions.

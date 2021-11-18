---
title: Avoiding Internet Centralization
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
  RFC2119:

informative:
  HTTP: I-D.draft-ietf-httpbis-semantics
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

--- abstract

Avoiding centralization is an important goal for Internet protocols. This document discusses why it is necessary for Internet protocol designers to consider centralization risks, identifies different kinds of centralization, lists techniques used to manage centralization, and recommends practices to avoid it.


--- middle

# Introduction

One reason the Internet is successful is its purposeful avoidance of any single controlling entity. While originally this approach may have been driven by a desire to prevent a single technical failure from having wide impact, it has also enabled the rapid adoption and broad spread of the Internet, because internetworking does not require obtaining permission from or ceding control to another entity -- thereby accommodating a spectrum of political and social requirements.

This means that protocols that are considered part of the Internet share a common design goal: avoiding centralization, which we define as the ability of a single person, company, or government -- or a small group of them -- to observe, control, or extract rent from the protocol's operation or use.

At the same time, the utility of many Internet protocols is enabled or significantly enhanced by ceding some aspect of communication to another party -- often, in a manner that has centralization risk. For example, there might be a need for a 'single source of truth' or a rendezvous facility to allow endpoints to find each other. How should such protocols be designed?

Furthermore, many successful proprietary protocols and applications on the Internet are de facto centralized. Some have become so well-known that they are commonly mistaken for the Internet itself. In other cases, Internet protocols seem to favour centralized deployments due to economic and social factors. Should standards efforts attempt to mitigate centralization in these cases, and if so, how?

Finally, some autonomous networks have requirements to control the operation of Internet protocols internally, and some users or groups of users might cede control of some aspect of how they use the Internet to a central authority, either voluntarily or under legal compulsion. In both of these cases, should Internet protocols accommodate such requirements, and if so, how?

This document discusses aspects of centralization with regard to Internet protocol design. {{why}} explains why it is necessary for Internet protocols to avoid centralization when possible. {{kinds}} surveys the different kinds of centralization that Internet protocols might be involved in. {{how}} explores techniques that can be used to manage centralization. Finally, {{considerations}} discusses cross-cutting interactions between centralization and protocol design.

The primary audience for this document is those involved in designing and standardising Internet protocols. However, designers of proprietary protocols can benefit from considering aspects of centralisation, especially if they intend their protocol to be considered for standardisation. Likewise, policymakers can use this document to help identify centralised protocols and applications, as they might attract different kinds of regulation.


## Notational Conventions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT",
"RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as
described in BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when, they appear in all capitals, as
shown here.


# Why Avoid Centralization {#why}

While in theory every node on the Internet is equal, in practice some nodes are much more connected than others: for example, just a few sites drive much of the traffic on the Web. While expected and observed in many kinds of networks {{SCALE-FREE}}, these network effects award asymmetric power to nodes that act as intermediaries to communication, thereby obtaining 'informational and positional advantages' {{INTERMEDIARY-INFLUENCE}}. That power can be used to observe behavior (the 'panopticon effect') and shape or even deny behaviour (the 'chokepoint effect') -- which can be used those parties (or the states that have authority over them) for coercive ends {{WEAPONIZED-INTERDEPENDENCE}}.

As a 'large, heterogeneous collection of interconnected systems' {{?BCP95}} the Internet is often characterised as a 'network of networks'. Protocols that are to considered a part of the Internet need to be suitable for deployment in this model -- where networks are peers who agree to facilitate communication, rather than subservient to each others' requirements or subject to coercion by them.

When applications and services are available from many different providers, the Internet and its users benefit from the resulting competition -- especially when those users can build their own applications and services based upon interoperable standards. When a broad set of users become dependent upon a centralised protocol, the central authority effective becomes an essential facility, which encourages abuse of that power.

Centralized protocols can also preclude the possibility of 'permissionless innovation' -- the ability to deploy new, unforeseen applications without requiring coordination with parties other than those you are communicating with.

Likewise, the availability of the Internet (as well as applications and services based upon it) improves when there are many ways to obtain access to them. While centralized services typically benefit from the focused attention that their elevated role requires, when they do fail, the resulting loss of availability can have disproportionate impact.

To summarize, Internet protocols avoid centralization because allowing it would allow the Internet (or some part of it) to be captured by a single entity, effectively turning it into a 'walled garden' that fails to meet the architectural design goals of and user expectations for the Internet.


# How Centralization Happens {#kinds}

Not all centralization of Internet protocols is equal; there are several different types, each with its own properties. The subsections below list some and recommend how they should be handled.


## Direct Centralization {#direct}

The most straightforward kind of centralized protocol creates a fixed role for a specific party.

For example, most proprietary messaging, videoconferencing, chat, and simliar protocols operate in this fashion because doing so simplifies their design and evolution {{MOXIE}}, and often there is a strong desire to capture the financial benefits of the protocol by 'locking in' users to that service.

Directly centralised protocols and applications are not considered to be part of the Internet per se; instead, they are more properly located as being built on top of the Internet.


## Necessary Centralization {#necessary}

Depending upon a protocol's requirements, it is not always possible to avoid introducing centralization risk -- in particular:

* when there is a requirement for a single, global 'source of truth' (e.g., for unambiguous naming), or
* when endpoints need to solve the 'rendezvous problem' in order to communicate without prior arrangement, or
* when direct communication isn't possible due to lower-layer constraints (e.g., due to Network Address Translation).

For example, the Domain Name Sytem (DNS) demonstrates the first kind of necessary centralization risk, because its purpose is to serve as a global source of naming.

Chat protocols are an example of the second kind of necessary centralization risk, because it is necessary to know where the party you wish to converse with is currently located on the network.

The third kind of necessary centralisation risk is faced by many applications, due to the uncertainty of direct connectivity between endpoints on the modern Internet. Network Address Translation, firewalls, and other barriers to direct communication hobble applications like chat, gaming, and file-sharing.


## Indirect Centralization {#indirect}

Even when defined to allow direct endpoint-to-endpoint communication, a protocol might become centralized if indirect factors influence its deployment, making it difficult or impossible to realize the value provided unless a central facility is used.

Such factors might be economic, social, or legal. Often, they are related to the network effects that are so often seen on the Internet.

For example, cloud computing is used to deploy many Internet protocols. Although the base concepts and control protocols for it are decentralized in the sense that there is no need for a single, central cloud provider, the economics of providing compute at scale as well as some social factors regarding developer familiarity and comfort encourage convergence on a small number of cloud providers.

Social networking is another Internet application that suffers from this type of centralization, despite standardization efforts (see, e.g., {{?W3C.CR-activitystreams-core-20161215}}), due to the powerful network effects associated.

Some have been concerned that DoH {{?RFC8484}} also has this type of centralization risk, because initial deployments defaulted to a pre-selected service run by one commercial operator.


## Inherited Centralization {#network}

Most Internet protocols depend on other, 'lower-layer' protocols to function. The features, deployment, and operation of these dependent protocols can surface centralization risk into protocols operation 'on top.'

For example, the network between endpoints can introduce centralization risk to application-layer protocols, because it is necessary for communication and therefore has power over it. A given network might block access to, slow down, or modify the content of various application protocols or specific services for financial, political, security, or criminal reasons, thereby creating pressure to centralize.

While users often have flexibility in their choices for Internet access, that is typically only true on longer timescales; in the moment, most users' choices are limited. Likewise, while the Internet's topology is in theory decentralized, there are in practice various 'choke points' that represent possibilities for observation and control, and therefore centralization.

Note that individual networks might have a legitimate need to control communication within their bounds. This requirement does not justify accommodation of centralization in Internet protocols, but might motivate accommodations for endpoints to opt into such mechanisms, provided that they are appropriately authenticated.


## Platform Centralization {#platform}

The complement to inherited centralization is platform centralization -- where a protocol does not directly define a central role, but could facilitate centralization in the applications it supports.

For example, HTTP {{HTTP}} in itself is not considered a centralized protocol; interoperable servers are relatively easy to instantiate, and multiple clients are available. It can be used without central coordination beyond that provided by DNS, as discussed above.

However, applications built on top of HTTP (as well as the rest of the 'Web Platform') often exhibit centralisation. As such, HTTP is an example of a platform for centralization -- while the protocol itself is not centralized, it's possible to build centralized services and applications using it.


# Techniques for Avoiding Internet Centralization {#how}

When a protocol designer is specifying a given function, several techniques to avoid centralization are available, depending on the nature of the protocol and its specific requirements. The following subsections discuss some of these options, as well as their advantages and disadvantages.


## Encryption

XXX


## Decentralization

The preferred method for mitigating Internet Centralization is to avoid it completely -- in other words, to design protocols where no centralized coordination, rendezvous or communication is necessary, but instead communication happens directly between the endpoints that wish to communicate.

This approach can be seen in many aspects of the Internet. Access to the Internet itself is decentralised; one does not need to gain permission from any authority to connect a network to the Internet, and there are several ways one can do so. Local conditions might change this (for example, when there are limited choices for access providers, due to legal or market circumstances), but that is not a limitation of the Internet itself.

Likewise, Internet routing does not require central coordination; instead, protocols like BGP {{?RFC4271}} allow peers to coordinate routing information in a decentralized way.

At the application layer, Atom {{?RFC4287}} allows an end user to obtain updates (often, news and simliar information) from publishers who they select, again without any central coordination or authority. While some Atom clients were built as services available over the Web, thereby intermediating that communication, the protocol does not require (or even encourage) that
style of deployment.


## Multi-Stakeholder Administration

When a function's nature requires it to be centralized, delegating the administraiton of that function to a multi-stakeholder body is one way to mitigate the effects of doing so.

A multi-stakeholder body is one that XXX

The most relevant example of this technique is the administration of the Domain Name System {{?RFC1035}}, which as a 'single source of truth' requires centralization of the naming function. To mitigate the effects, the function is carried out by multiple root servers that are administered by separate operators -- themselves diverse in geography and a selection of corporate entities, non-profits and government bodies from many jurisdictions and affiliations. Furthermore, those operators are regulated by ICANN, which is defined as a globally multi-stakeholder body with representation from a end users, governments, operators, and others.

Another example of multi-stakeholderism is the standardization of Internet protocols themselves. Because a specification effectively controls the behavior of implementations that are conformant with it, the standarization process can be seen as a single point of control. As a result, Internet standards bodies like the IETF allow open participation and contribution, make decisions in an open and accountable way, have a well-defined process for making (and when necessary, appealing) decisions, and take into account the views of different stakeholder groups {{?RFC8890}}.

Yet another example is the administration of the Web's trust model, implemented by Web browsers as relying parties and Certificate Authorities as trust anchors. To assure that all parties meet the operational and security requirements necessary to provide the desired properties, the CAB Forum was established as an oversight body that involves both of those parties as stakeholders.

In each of these examples, setup and ongoing operation of a multi-stakeholder organization is not trivial. This is the major downside of such an approach. Additionally, the legitimacy of such an organization cannot be assumed, and may be difficult to establish and maintain. This concern is especially relevant if the function being coordinated is broad, complex, and/or contentious.


## Federation

Another technique for mitigating centralization in Internet protocols is federation - that is, designing them in such a way that new instances of the centralized function are relatively easy to create while maintaining interoperability and connectivity with other instances, so that communication between two endpoints might traverse one or more intermediate servers.

The most prevalent (and successful) example of a federated Internet protocol is SMTP {{?RFC5321}}, as part of the e-mail suite of protocols. While e-mail uses DNS as the basis of naming, it still requires a way to route a message to a specific user based upon that name.

E-mail resolves this issue by defining a role for routing users' messages, the Message Transfer Agent (MTA). By allowing anyone to deploy a MTA and rules for interconnecting them, users can receive messages from other systems using SMTP.

Users can (and often do) choose to delegate that role to someone else. Running your own mail server has become difficult, due to the likelihood of a small MTA being classified as a spam source. Because large MTA operaters are widely known and have greater impact if their operation is affected, they are less likely to be classified as such, thereby indirectly centralizing the protocol's operation (see {{indirect}}).

Another example of a federated Internet protocol is XMPP {{?RFC6120}}, supporting 'instant messaging' and similar functionality. Again using DNS for naming, XMPP requires federation to facilitate rendezvous of users from different systems.

While some deployments of XMPP do support truly federated messaging (i.e., a person using service A can interoperably chat with someone using service B), many of the largest do not. Because federation is voluntary, some operators made a decision to attempt to capture their users into a single service, rather than provide the benefits of global interoperability (see {{platform}}).

The examples above show that federation can be a useful technique, but on its own is not sufficient to avoid centralization. If the value provided by a protocol can be captured by a single entity, they may use the protocol as a platform to obtain a 'winner take all' outcome -- a significant risk with many Internet protocols, since network effects often promote such outcomes. Likewise, external factors (such as spam control) might naturally 'tilt the table' towards a few operators of these protocols.


## Distributed Consensus

XXX


# Considerations for Protocol Design {#considerations}

While the following recommendations are not a complete guide, they can be a starting point for judging and mitigating centralization in protocols.


## Use Intermediation Carefully {#intermediation}

The introduction of an intermediary role -- i.e., a party that is required for communication to take place between endpoints -- adds centralization risk to Internet protocols, because it brings the opportunity for control.

However, intermediation can sometimes be necessary. When a function cannot be performed in a fully decentralized fashion (for example, rendezvous), introducing an intermediary or server of some sort is necessary to realize the benefits of the protocol. As discussed above, this is the case for XMPP and SMTP.

In such cases, the centralized function SHOULD be as minimal as possible, and expose only the information and pontential for control necessary for that function to be performed.

Intermediation can also be introduced to allow functions or access to information to be separated in a controlled way, thereby reducing the need to trust the other endpoint. For example, there are a number of so-called 'oblivious' protocols currently in development that allow end users to hide details that might identify them from services, while still accessing those services.

The same guidance applies in these cases; the information and control potential SHOULD be as minimal as possible, while still meeting the design goals of the protocol.


## Protocol Evolution Can Be a Centralization Risk {#evolution}

An important feature of Internet protocols is their ability to evolve over time, so that they can meet new requirements and adapt to new conditions without requiring a 'flag day' to convert users. Typically, protocol evolution is accommodated through extension mechanisms, where optional features can be added over time in an interoperable fashion.

Protocol extensions can become a centralization risk if a powerful entry can change the target for meaningful interoperability by adding proprietary extensions to a standard protocol. This is especially true when the core standard does not itself provide sufficient utility to be appealing on its own.

This kind of centralization risk can be mitigated in a few ways. First and foremost, Internet protocols SHOULD provide concrete utility to the majority of their users as published; 'framework' standards facilitate this kind of risk.

Furthermore, Internet protocols SHOULD NOT make every aspect of their operation extensible; extension points SHOULD be reasoned, appropriate boundaries for flexibility and control. When extension points are defined, they SHOULD NOT allow an extension to declare itself to be mandatory-to-interoperate, as that pattern invites abuse.


# Security Considerations

This document does not have direct security impact on Internet protocols. However, failure to consider centralization risks might result in a myriad of security issues.


--- back


# Acknowledgements

This document benefits from discussions with Brian Trammell during our shared time on the Internet Architecture Board.

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
  LEGITIMACY-MULTI:
    title: "Legitimacy, Power, and Inequalities in the Multistakeholder Internet Governance"
    date: 2020
    author:
     -
       name: Nicola Palladino
     -
       name: Nauro Santaniello

--- abstract

Avoiding centralization is an important goal for Internet protocols. This document defines the term, discusses why it is necessary for Internet protocol designers to consider centralization risks, identifies different kinds of centralization, catalogues some limitations of current approaches to controlling it, and recommends best practices for protocol designers.


--- middle

# Introduction

The Internet is successful in no small part because of its purposeful avoidance of any single controlling entity. While originally this may have been due to a desire to prevent a single technical failure from having wide impact, it has also enabled the rapid adoption and broad spread of the Internet, because internetworking does not require obtaining permission from or ceding control to another entity -- thereby accommodating a spectrum of political and social requirements.

This means that protocols that are considered part of the Internet share a common design goal: avoiding centralization, which we define as the ability of a single person, company, or government -- or a small group of them -- to observe, control, or extract rent from the protocol's operation or use.

At the same time, the utility of many Internet protocols is enabled or significantly enhanced by ceding some aspect of communication between two parties to a third party -- often, in a manner that has centralization risk. For example, there might be a need for a 'single source of truth' or a rendezvous facility to allow endpoints to find each other. How should such protocols be designed?

Furthermore, many successful proprietary protocols and applications on the Internet are de facto centralized. Some have become so well-known that they are commonly mistaken for the Internet itself. In other cases, Internet protocols seem to favour centralized deployments due to economic and social factors. Should standards efforts attempt to mitigate centralization in these cases, and if so, how?

Finally, some autonomous networks have requirements to control the operation of Internet protocols internally, and some users or groups of users might cede control of some aspect of how they use the Internet to a central authority, either voluntarily or under legal compulsion. In both of these cases, should Internet protocols accommodate such requirements, and if so, how?

This document discusses aspects of centralization with regard to Internet protocol design. {{why}} explains why it is necessary for Internet protocols to avoid centralization when possible. {{kinds}} surveys the different kinds of centralization that Internet protocols might be involved in. {{decentralization}} then catalogues current high-level approaches to mitigating centralization and discusses their limitations. Finally, {{considerations}} discusses cross-cutting interactions between centralization and protocol design, recommending best practices where appropriate.

Engineers who design and standardize Internet protocols are the primary audience for this document. However, designers of proprietary protocols can benefit from considering aspects of centralisation, especially if they intend their protocol to be considered for standardisation. Likewise, policymakers can use this document to help identify and remedy inappropriately centralized protocols and applications.


## Notational Conventions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT",
"RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as
described in BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when, they appear in all capitals, as
shown here.


# Why Avoid Centralization {#why}

As a 'large, heterogeneous collection of interconnected systems' {{?BCP95}} the Internet is often characterised as a 'network of networks'. As such, networks relate as peers who agree to facilitate communication, rather than having a relationship of subservience to others' requirements or coercion by them.

Many Internet protocols allow a third party to be interposed into communication between two other parties -- by necessity, by happenstance, or at the option of one or both of the participants. This is often characterised as _intermediation_, and is often used to help provide a protocol's functions, and may be necessary for some of them. However, the 'informational and positional advantages' {{INTERMEDIARY-INFLUENCE}} gained can be used to observe behavior (the 'panopticon effect') and shape or even deny behaviour (the 'chokepoint effect') -- which can be used those parties (or the states that have authority over them) for coercive ends {{WEAPONIZED-INTERDEPENDENCE}}.

As Internet protocols' first duty is to the end user {{?RFC8890}}, allowing such power to be concentrated into few hands is counter to the goals of the Internet.

Additionally, concentration of power has deleterious effects on the Internet itself, including:

* _Innovation_: Centralized protocols can preclude the possibility of 'permissionless innovation' -- the ability to deploy new, unforeseen applications without requiring coordination with parties other than those you are communicating with.

* _Competition_: The Internet and its users benefit from robust competition when applications and services are available from many different providers -- especially when those users can build their own applications and services based upon interoperable standards. When dependencies are formed on a centralized service or platform, it effectively becomes an essential facility, which encourages abuse of power.

* _Availability_: The Internet's availability (as well as applications and services built upon it) improves when there are many ways to obtain access to it. While centralized services typically benefit from the focused attention that their elevated role requires, when they do fail, the resulting loss of availability can have disproportionate impact.

To summarize, Internet protocols avoid centralization because allowing it would allow the Internet (or some part of it) to be captured, effectively turning it into a 'walled garden' that fails to meet its architectural design goals and users' expectations.


# Kinds of Centralization {#kinds}

Not all centralization of Internet protocols is equal; there are several different types, each with its own properties. The subsections below list some.


## Direct Centralization {#direct}

The most straightforward kind of centralized protocol creates a fixed role for a specific party.

For example, most proprietary messaging, videoconferencing, chat, and simliar protocols operate in this fashion. While it has been argued that such protocols are simpler to design and evolve,{{MOXIE}} this approach most often reflects commercial goals -- in particular, a strong desire to capture the financial benefits of the protocol by 'locking in' users to a proprietary service.

Directly centralised protocols and applications are not considered to be part of the Internet per se; instead, they are more properly characterized as proprietary protocols that are built on top of the Internet.


## Necessary Centralization {#necessary}

Some protocol requirements require the introduction of centralization risk -- in particular:

* When there is a requirement for a single, global 'source of truth' (e.g., for unambiguous naming), or
* When endpoints need to solve the 'rendezvous problem' in order for two parties to communicate without prior arrangement, or
* When direct communication isn't possible due to lower-layer constraints (e.g., due to Network Address Translation).

For example, the Domain Name Sytem (DNS) demonstrates the first kind of necessary centralization risk, because its purpose is to serve as a global source of naming.

Chat protocols are an example of the second kind of necessary centralization risk, because it is necessary to know where the party you wish to converse with is currently located on the network.

The third kind of necessary centralisation risk is faced by many applications, due to the uncertainty of direct connectivity between endpoints on the modern Internet. Network Address Translation, firewalls, and other barriers to direct communication hobble applications like chat, gaming, and file-sharing.


## Indirect Centralization {#indirect}

Even if a protocol disallows direct centralization (perhaps using one of the techniques discussed in {{decentralization}}) and does not exhibit any necessary centralization, it might become centralized in practice when external factors influence its deployment.

Indirect centralization is caused by factors making it difficult or impossible to realize the protocol's value unless a central facility is used. Such factors might be economic, social, or legal.

Often, they are related to the network effects that are so often seen on the Internet. While in theory every node on the Internet is equal, in practice some nodes are much more connected than others: for example, just a few sites drive much of the traffic on the Web. While expected and observed in many kinds of networks {{SCALE-FREE}}, the resulting network effects award asymmetric power to nodes that act as intermediaries to communication.

For example, cloud computing is used to deploy many Internet protocols. Although the base concepts and control protocols for it are decentralized in the sense that there is no need for a single, central cloud provider, the economics of providing compute at scale as well as some social factors regarding developer familiarity and comfort encourage convergence on a small number of cloud providers.

In some cases, these factors cause a directly centralized protocol or application to be favoured over a decentralized one. For example, social networking is an application that is currently supplied by a small number of directly centralized, proprietary platforms despite standardization efforts (see, e.g., {{?W3C.CR-activitystreams-core-20161215}}), due to the powerful network effects associated.

Some have expressed concern that DoH {{?RFC8484}} also has this type of centralization risk, because initial deployments defaulted to a pre-selected service run by one commercial operator.


## Inherited Centralization {#network}

Most Internet protocols depend on other, 'lower-layer' protocols. The features, deployment, and operation of these dependencies can surface centralization risk into protocols operating 'on top' of them.

For example, the network between endpoints can introduce centralization risk to application-layer protocols, because it is necessary for communication and therefore has power over it. A given network might block access to, slow down, or modify the content of various application protocols or specific services for financial, political, operational, or criminal reasons, thereby creating pressure to use other services, which can in turn result in centralization.

Inherited centralization risk is only present when users cannot use an alternative means of accessing the desired service. For example, users often have flexibility in choice of Internet access, so they could just 'route around' a network that impacts their chosen service. However, such choices are often not available in the moment, and the Internet's topology means that a 'choke point' upstream could still affect their Internet access.


## Platform Centralization {#platform}

The complement to inherited centralization is platform centralization -- where a protocol does not directly define a central role, but could facilitate centralization in the applications it supports.

For example, HTTP {{HTTP}} in itself is not considered a centralized protocol; interoperable servers are relatively easy to instantiate, and multiple clients are available. It can be used without central coordination beyond that provided by DNS, as discussed above.

However, applications built on top of HTTP (as well as the rest of the 'Web Platform') often exhibit centralisation. As such, HTTP is an example of a platform for centralization -- while the protocol itself is not centralized, it does facilitate the creation of centralized services and applications.


# The Limits of Decentralization {#decentralization}

## Federation isn't Enough {#federation}

A widely known technique for avoiding centralization in Internet protocols is federation - that is, designing them in such a way that new instances of any intermediary or otherwise centralized function are relatively easy to create, and they are able to maintain interoperability and connectivity with other instances.

The most prevalent (and successful) example of a federated Internet protocol is SMTP {{?RFC5321}}, as part of the e-mail suite of protocols. While e-mail uses DNS as the basis of naming (thus mitigating the centralisation of that function; see {{reuse}}), it still requires a way to route a message to a specific user based upon that name.

E-mail resolves this issue by defining an intermediary role for routing users' messages, the Message Transfer Agent (MTA). By allowing anyone to deploy a MTA and rules for interconnecting them, users can receive messages from other systems using SMTP.

Users can (and often do) choose to delegate that role to someone else, or run their own MTA. However, running your own mail server has become difficult, due to the likelihood of a small MTA being classified as a spam source. Because large MTA operaters are widely known and have greater impact if their operation is affected, they are less likely to be classified as such, thereby indirectly centralizing the protocol's operation (see {{indirect}}).

Another example of a federated Internet protocol is XMPP {{?RFC6120}}, supporting 'instant messaging' and similar functionality. Again using DNS for naming, XMPP requires federation to facilitate rendezvous of users from different systems.

While some deployments of XMPP do support truly federated messaging (i.e., a person using service A can interoperably chat with someone using service B), many of the largest do not. Because federation is voluntary, some operators made a decision to attempt to capture their users into a single service, rather than provide the benefits of global interoperability.

The examples above show that federation can be a useful technique to avoid direct centralization, but on its own is not sufficient to avoid indirect centralization. If the value provided by a protocol can be captured by a single entity, they may use the protocol as a platform to obtain a 'winner take all' outcome -- a significant risk with many Internet protocols, since network effects often promote such outcomes. Likewise, external factors (such as spam control) might naturally 'tilt the table' towards a few operators of these protocols.


## Multi-Stakeholder Administration is Hard {#multi}

Delegating the administration of a necessarily centralized function (see {{necessary}}) to a multi-stakeholder body is an onerous but sometimes necessary way to mitigate any resulting centralization.

A multi-stakeholder body is an institution that includes representatives of the different kinds of parties that are affected by the system's operation ('stakeholders') in an attempt to make well-reasoned, broadly agreed-to, and authoritative decisions.

The most relevant example of this technique is the administration of the Domain Name System {{?RFC1035}}, which as a 'single source of truth' requires centralization of the naming function. To mitigate centralization, this task is carried out by multiple root servers that are administered by separate operators -- themselves diverse in geography and a selection of corporate entities, non-profits and government bodies from many jurisdictions and affiliations. Furthermore, those operators are regulated by ICANN, which is defined as a globally multi-stakeholder body with representation from a end users, governments, operators, and others.

Another example of multi-stakeholderism is the standardization of Internet protocols themselves. Because a specification effectively controls the behavior of implementations that are conformant with it, the standardization process can be seen as a single point of control. As a result, Internet standards bodies like the IETF allow open participation and contribution, make decisions in an open and accountable way, have a well-defined process for making (and when necessary, appealing) decisions, and take into account the views of different stakeholder groups {{?RFC8890}}.

Yet another example is the administration of the Web's trust model, implemented by Web browsers as relying parties and Certificate Authorities as trust anchors. To assure that all parties meet the operational and security requirements necessary to provide the desired properties, the CA/Browser Forum was established as an oversight body that involves both of those parties as stakeholders.

In each of these examples, setup and ongoing operation of a multi-stakeholder organization is not trivial. This is the major downside of such an approach. Additionally, the legitimacy of such an organization cannot be assumed, and may be difficult to establish and maintain (see, eg, {{LEGITIMACY-MULTI}}). This concern is especially relevant if the function being coordinated is broad, complex, and/or contentious.


## Blockchains Are Not Magical {#distributed}

Increasingly, distributed consensus technologies such as the blockchain are touted as a solution to centralization issues. A complete survey of this rapidly-changing area is beyond the scope of this document, but at a high level, we can generalise about their properties.

These techniques avoid centralization risk by distributing intermediary functions to members of a large pool of protocol participants. Verification of proper performance is typically guaranteed through a combination of cryptographic techniques and duplication of effort to check results. The assignment of a particular task to a node for handling usually cannot be predicted or controlled.

As such, they avoid direct centralization, and are robust against inherited centralization. Depending upon the application in question, indirect and platform centralization may still be possible, but in general these techniques do not lend themselves to these ends as readily as federated systems do.

However, distributed consensus technologies have several potential shortcomings that may make them inappropriate -- or at least difficult to use -- for many Internet applications:

1. They often rely diversity of participants. If significant numbers of participants are in fact operated by the same entity, or participants collude, centralization can still occur -- a so-called 'Sybil attack.'

2. Distributed consensus protocols can have significant implications for privacy. Because activity (such as queries or transactions) are shared with many unknown parties, they have very different privacy properties than traditional client/server protocols.

3. Their complexity and 'chattiness' typically results in less efficient use of the network. Some distributed consensus protocols use 'proof of work', leading to significant energy consumption when used at scale.

4. Distributed consensus protocols are still not proven to scale to the degree expected of successful Internet protocols. In particular, relying on unknown third parties to deliver functionality can introduce variability in latency, availability, and throughput.

5. By design, distributed consensus protocols diffuse responsibility for a function among several, difficult-to-identify parties. While this may be an effective way to prevent many kinds of centralization, it also means that making someone accountable for how the function is performed is impossible, beyond the bounds of the protocol's design.

These potential shortcomings do not rule out the use of distributed consensus technologies for every use case, and solutions or mitigations are maturing. They do, however, caution against applying these technologies uncritically.


# Guidelines for Protocol Designers {#considerations}

While the following recommendations are not a complete guide, they can be a starting point for avoiding or mitigating centralization in Internet protocols.


## Allow Intermediation Sparingly {#intermediation}

The introduction of an intermediary role -- i.e., a party that is required for communication to take place between endpoints -- adds centralization risk to Internet protocols, because it brings opportunities for control and observiation.

However, intermediation can sometimes add significant value to a protocol, or enable what is considered a necessary function. In such cases, the centralized function SHOULD be as minimal as possible, and expose only the information and pontential for control necessary for that function to be performed. Protocol designers SHOULD consider the likely deployment patterns for those intermediaries and how network effects and other factors will influence them.

Note that intermediation can also be used to control access to information or impose functional boundaries, so as to reduce the need to trust potentially malicious endpoints. For example, there are a number of so-called 'oblivious' protocols currently in development that allow end users to hide details that might identify them from services, while still accessing those services.

The same guidance applies in these cases; the observation and control potential SHOULD be as minimal as possible, while still meeting the design goals of the protocol.


## Encrypt, Always {#encrypt}

When deployed at scale, encryption can be an effective technique to reduce the risks of inherited centralization. By reducing the number of parties who have access to content of communication, the ability of lower-layer protocols and intermediaries at those layers to interfere with or observe is reduced.

Note that the benefits are most pronounced when the majority (if not all) traffic is encrypted. As a result, protocols SHOULD be encrypted by default. See also {{?RFC7258}}.


## Reuse Existing Tools {#reuse}

When a protocol function has necessary centralization risk and there exists an already-deployed solution with appropriate mitigations, that solution should be reused in favour of inventing a new one.

For example, if a protocol requires a coordinated, global naming function, reusing the Domain Name System is preferable to establishing a new system, because its centralization risk is known and understood (see {{multi}}).

XXX


## Protocol Evolution Can Be a Centralization Risk {#evolution}

An important feature of Internet protocols is their ability to evolve over time, so that they can meet new requirements and adapt to new conditions without requiring a 'flag day' to convert users. Typically, protocol evolution is accommodated through extension mechanisms, where optional features can be added over time in an interoperable fashion.

Protocol extensions can become a centralization risk if a powerful entry can change the target for meaningful interoperability by adding proprietary extensions to a standard protocol. This is especially true when the core standard does not itself provide sufficient utility to be appealing on its own.

This kind of centralization risk can be mitigated in a few ways. First and foremost, Internet protocols SHOULD provide concrete utility to the majority of their users as published; 'framework' standards facilitate this kind of risk.

Furthermore, Internet protocols SHOULD NOT make every aspect of their operation extensible; extension points SHOULD be reasoned, appropriate boundaries for flexibility and control. When extension points are defined, they SHOULD NOT allow an extension to declare itself to be mandatory-to-interoperate, as that pattern invites abuse.


## Accomodate Limited Domains Warily

{{?RFC8799}} explores a class of protocols that operate in 'limited domains' -- that is, they are not intended to be 'full' Internet protocols with broad applicability, but instead operation within a particular network or other constrained environment.

Often, limited-domain protocols address network requirements -- for example, imposing security policy, integrating services or application functions into the network, or differentiating different classes of network services.

Such network-centric requirements can introduce the risk of inherited centralization when they allow the network to interpose itself and its requirements between the endpoints of a given communication.

These risks can be partially mitigated by requiring such functions to be opted into by one or both endpoints (once both the network and the endpoint are authenticated to each other), so that the network is acting on their behalf. However, this approach is still vulnerable to indirect centralization, because the endpoints may have few choices to avoid acquiescing to a network's demands.


## Build Higher Level Protocols

Platform centralization can be mitigated by XXX




## Acknowledge the Limits of Protocol Design

XXX
Indirect
Platform


# Security Considerations

This document does not have direct security impact on Internet protocols. However, failure to consider centralization risks might result in a myriad of security issues.


--- back


# Acknowledgements

This document benefits from discussions with Brian Trammell during our shared time on the Internet Architecture Board.

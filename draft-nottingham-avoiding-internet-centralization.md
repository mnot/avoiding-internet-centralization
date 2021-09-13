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


--- abstract

Avoiding centralization is an important goal in the design of Internet protocols. This document discusses why it is necessary for Internet protocols to avoid centralization, how they can do so, and the design implications of centralisation upon them.


--- note_Note_to_Readers

*RFC EDITOR: please remove this section before publication*

The issues list for this draft can be found at <https://github.com/mnot/avoiding-internet-centralization/issues>.

The most recent (often, unpublished) draft is at <https://mnot.github.io/avoiding-internet-centralization/>.

See also the draft's current status in the IETF datatracker, at
<https://datatracker.ietf.org/doc/draft-nottingham-avoiding-internet-centralization/>.

--- middle

# Introduction

One of the properties that has made the Internet successful is its purposeful avoidance of any single controlling entity. While originally the primary purpose of this approach may have been a desire to prevent a single technical failure from having wide impact, it has also enabled the rapid adoption and broad spread of the Internet, because internetworking does not require obtaining permission from or ceding control to another entity -- thereby accommodating a spectrum of political and social requirements.

This means that protocols that are considered part of the Internet share a common design goal: avoiding centralization, which we define as the ability of a single person, company, or government to observe, control, or extract rent from the protocol's operation.

At the same time, the utility of many Internet protocols is enabled or significantly enhanced by ceding some aspect of communication to another party -- often, in a manner has centralization risk. For example, there might be a need for a 'single source of truth' or a rendezvous facility to allow endpoints to find each other. How should such protocols be designed?

Furthermore, many successful proprietary protocols and applications on the Internet are de facto centralized. Some Web sites and applications have become so well-known that they are commonly mistaken for the Internet itself. In other cases, Internet protocols seem to favour centralized deployments due to economic and social factors. Should standards efforts attempt to mitigate centralization in these cases, and if so, how?

Finally, some autonomous networks have requirements to control the operation of Internet protocols internally, and some users or groups of users might cede control of some aspect of how they use the Internet to a central authority, either voluntarily or under legal compulsion. In both of these cases, should Internet protocols accommodate such requirements, and if so, how?

This document discusses aspects of centralization with regard to Internet protocol design. {{why}} explains why it is necessary for Internet protocols to avoid centralization when possible. {{kinds}} surveys the different kinds of centralization that Internet protocols might be involved in, and make general recommendations about how they should be handled. {{how}} further explores specific techniques that can be used to do so. Finally, {{considerations} discusses cross-cutting interactions between centralization and protocol design.

The primary audience for this document is those involved in designing and standardising Internet protocols. However, designers of proprietary protocols can benefit from considering aspects of centralisation, especially if they intend their protocol to be considered for standardisation. Likewise, policymakers can use this document to help distinguish between Internet protocols and proprietary ones, as they might attract different kinds of regulation.


## Notational Conventions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT",
"RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as
described in BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when, they appear in all capitals, as
shown here.


# Why Avoid Centralization {#why}

By definition, the Internet is a 'large, heterogeneous collection of interconnected systems' {{?BCP95}}; it is often characterised as a 'network of networks'. If a protocol is to considered a part of the Internet, it needs to be suitable for deployment in this model, where networks are  peers who agree to facilitate communication, rather than subservient to each others' requirements. A centralised protocol is in danger of violating this requirement by conveying power to a third party.

Centralized protocols can also preclude the possibility of 'permissionless innovation' -- the ability to deploy new, unforeseen applications without requiring coordination with parties other than those you are communicating with.

The Internet and its users also benefit from competition when applications and services are available from many different providers -- especially when those users can build their own applications and services based upon interoperable standards. When a broad set of users become dependent upon a centralised protocol, the central authority effective becomes an essential facility, which encourages abuse of that power.

Likewise, the availability of the Internet (as well as applications and services based upon it) improves when there are many ways to obtain access to them. While centralized services typically benefit from the focused attention that their role requires, that does not offset the reliability problems introduced by a single point of failure.

To summarize, Internet protocols avoid centralization because allowing it would allow the Internet (or some part of it) to be captured by a single entity, effectively turning it into a 'walled garden' that fails to meet the architectural design goals of and user expectations for the Internet.


# Kinds of Centralization {#kinds}

Not all centralization of Internet protocols is equal; there are several different types, each with its own properties. The subsections below list some and recommend how they should be handled.


## Direct Centralization {#direct}

The most straightforward kind of centralized protocol creates a fixed role for a specific party. Most proprietary messaging, videoconferencing, chat, and simliar protocols operate in this fashion, because doing so simplifies their design and evolution.

Internet protocols MUST avoid direct centralization whenever possible; decentralized protocols are always preferable, for the reasons given in {{why}}. This means that communication SHOULD be directly between peers wherever possible.

However, it is not always possible for a protocol to do so -- in particular:

* when there is a requirement for a single, global 'source of truth' (e.g., for unambiguous naming), or
* when different endpoints need to solve the 'rendezvous problem' in order to communication without prior arrangement, or
* when direct communication isn't possible (e.g., due to Network Address Translation).

When this is the case, the directly centralized function SHOULD be implemented using one of the techniques described in {{how}}, or (preferably) leverage an existing function that does so, such as the DNS.

Direct centralized functions SHOULD be separated from those that do not require centralization, where possible. When separation is not possible, techniques like encryption SHOULD be used to avoid inappropriate access to content of communications and metadata by the central service.


## Optional Centralization {#optional}

Often, functions that allow a third party to participate in a protocol are defined to be optional in protocols -- either optional to implement, optional to use, or both.

When the choice of whether and how to allow a third party is in the hands of the end user(s) of the protocol, there is little centralization risk. However, when they can be compelled -- economically, legally, or socially -- to make a specific choice, there may be centralization risk present.

For example, when a protocol can operate in a decentralized fashion, but offers additional benefits when an intermediary is used, there might be centralization risk if those additional benefits accrue into few hands.

XXX


## Network-Driven Centralization {#network}

The network between endpoints can introduce centralization risk, because it is necessary for communication and therefore has power over it. While users often have flexibility in their choices for Internet access, that is typically only true on longer timescales; in the moment, most users' choices are limited. Likewise, while the Internet's topology is in theory decentralized, there are in practice various 'choke points' that represent possibilities for control, and therefore centralization.

For example, XXX

This centralization risk can be mitigated by limiting the amount of information available to the network, to deny the ability to identify and thereby control communication. Encryption is the RECOMMENDED method, e.g., as implemented by TLS {{?RFC8446}} and QUIC {{?I-D.ietf-quic-transport}}.

Note that individual networks might have a legitimate need to control communication within their bounds. This requirement does not justify accommodation of centralization in Internet protocols, but might motivate accommodations for endpoints to opt into such mechanisms, provided that they are appropriately authenticated.


## Indirect Centralization {#indirect}

Even when defined to allow direct endpoint-to-endpoint communication, a protocol might become centralized if indirect factors influence its deployment, making it difficult or impossible to realize the value provided unless a central facility is used. Such factors might be economic, social, or legal. Often, they are related to the network effects that are so often seen on the Internet.

For example, cloud computing is used to deploy many Internet protocols. Although the base concepts and control protocols for it are decentralized in the sense that there is no need for a single, central cloud provider, the economics of providing compute at scale as well as some social factors regarding developer familiarity and comfort encourage convergence on a small number of cloud providers.

Social networking is another Internet application that suffers from this type of centralization, despite standardization efforts (see, e.g., {{?W3C.CR-activitystreams-core-20161215}}), due to the powerful network effects associated with it.

Some have been concerned that DoH {{?RFC8484}} also has this type of centralization risk, because initial deployments only offered a single, pre-selected service run by one commercial operator.

In all of these cases, voluntary technical standards have limited means to address centralization risks. However, if a standard is defined for the relevant functions in a way that allows an appropriate degree of interoperability and (where appropriate) federation (see {{federation}}), other regulation modalities (such as legal) might more effectively be able to control those risks.

Therefore, definition of interoperable, widely-reviewed and openly available protocols is preferable to proprietary ones in these cases, so the standardization of such protocols SHOULD NOT be refused merely due to external centralization risk.


## Platform Centralization {#platform}

Some protocols might not directly define a central role, but they might facilitate centralization in the applications they support.

For example, HTTP {{HTTP}} in itself is not considered a centralized protocol; interoperable servers are relatively easy to instantiate, and multiple clients are available. It can be used without central coordination beyond that provided by DNS, as discussed above.

However, applications built on top of HTTP (as well as the rest of the 'Web Platform') often exhibit centralisation. As such, HTTP is an example of a platform for centralization -- while the protocol itself is not centralized, it's possible to build centralized services and applications using it.

This kind of centralization risk is not directly associated with the protocols that are standardized, but rather is a property of the applications built on top of that platform. As a result, the platform itself is not typically a viable place to avoid centralization. Rather, focus of standards efforts SHOULD be placed upon decentralizing the functions built on top of it.



# Techniques for Avoiding Internet Centralization {#how}

When a protocol designer is specifying a given function, several techniques to avoid centralization are available, depending on the nature of the protocol and its specific requirements. The following subsections discuss some of these options, as well as their advantages and disadvantages.


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

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
      - VIC
    country: Australia
    email: mnot@mnot.net
    uri: https://www.mnot.net/

normative:
  RFC2119:

informative:
  HTTP: I-D.draft-ietf-httpbis-semantics


--- abstract

This document discusses aspects of centralization with regard to Internet protocol design -- why it is necessary for Internet protocols to avoid centralization, how they can do so, and the design implications of centralisation on them.


--- note_Note_to_Readers

*RFC EDITOR: please remove this section before publication*

The issues list for this draft can be found at <https://github.com/mnot/avoiding-internet-centralization/issues>.

The most recent (often, unpublished) draft is at <https://mnot.github.io/avoiding-internet-centralization/>.

See also the draft's current status in the IETF datatracker, at
<https://datatracker.ietf.org/doc/draft-nottingham-avoiding-internet-centralization/>.

--- middle

# Introduction

One of the properties that distinguishes the Internet from other networking and communication architectures is its purposeful avoidance of control over communication between autonomous networks by any single entity.

This means that it is counter to the Internet architecture for a single person, company, organization, or government to determine what is and is not appropriate communication on the Internet, to have access to others' Internet communication, or to extract rents on Internet communication. Such concentration of power is referred to in this document as 'centralization.'

Note that this does not imply that it is inappropriate for a single autonomous network to control aspects of communication within that network. Likewise, it may be that a group of autonomous networks or their users might voluntarily decide to cede control to a central entity, or be legally compelled to do so. However, it does not follow that it is always appropriate to accommodate these use cases in Internet protocols.

This document discusses aspects of centralization with regard to Internet protocol design. {{why}} explains why it is necessary for Internet protocols to avoid centralization. {{how}} surveys the techniques that can be used to do so, with varying effectiveness. {{considerations} discusses interactions between centralization and various protocol design choices.

The primary audience for this document is those involved in designing and standardising Internet protocols. However, designers of proprietary protocols can benefit from considering aspects of centralisation, especially if they intend their protocol to be considered for standardisation. Likewise, policymakers can use this document to help distinguish between Internet protocols and proprietary ones, as they might attract different kinds of regulation.


## Notational Conventions

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT",
"RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as
described in BCP 14 {{!RFC2119}} {{!RFC8174}} when, and only when, they appear in all capitals, as
shown here.


# Why Internet Protocols Avoid Centralization {#why}

By definition, the Internet is a 'large, heterogeneous collection of interconnected systems' {{?BCP95}}; in other words, it is a network of networks. If a protocol is to have deployment and interoperation on an Internet scale, its operation needs to be suitable for use within and between any of those autonomous networks.

A centralised protocol violates this requirement by conveying power over its operation to a third party. This power might be a form of direct control, or it might make the activities of those who use the protocol legible in a way where they can extract value or use the information obtained to exert control elsewhere.

Centralized protocols also preclude the possibility of 'permissionless innovation' -- i.e., the ability to deploy new, unforeseen applications without requiring coordination with parties other than those you are communicating with. While this might be acceptable for specialized protocols with limited deployment, it becomes problematic when a broad set of users and other protocols become dependent upon a centralised protocol, thereby making it an essential facility.

The Internet and its users also benefit from competition when interoperable applications and services are available from many different providers -- and especially when those users can build their own applications and services based upon interoperable standards.

Likewise, the availability of the Internet (as well as applications and services based upon it) improves when there are many ways to obtain access to it and them. While centralized services typically benefit from the focused attention that their role requires, that does not offset the reliability problems introduced by a single point of failure. Even in cases where such services are provided by a small pool of operators, the availability risks of centralization needs to be carefully weighed.

To summarize, Internet protocols avoid centralization because allowing it would allow the Internet (or some part of it) to be captured by a single entity, effectively turning it into a 'walled garden' that fails to meet the architectural design goals of and user expectations for the Internet.


# Techniques for Avoiding Internet Centralization {#how}

Several techniques are available when protocol designers are faced with the possibility of centralization when specifying a given function, depending on the nature of the protocol and its specific requirements. The following subsections discuss some of these options, as well as their advantages and disadvantages.


## Decentralization

The preferred method for mitigating Internet Centralization is to avoid it completely -- in other words, to design protocols where no centralized coordination, rendezvous or communication is necessary.

This approach can be seen in many aspects of the Internet. Access to the Internet itself is decentralised; one does not need to gain permission from any authority to connect a network to the Internet, and there are several ways one can do so. Local conditions might change this (for example, when there are limited choices for access providers, due to legal or market circumstances), but that is not a limitation of the Internet itself.

Likewise, Internet routing does not require central coordination; instead, protocols like BGP {{?RFC4271}} allow peers to coordinate routing information in a decentralized way.

An example at the application layer is Atom {{?RFC4287}}, which allows an end user to obtain updates (often, news and simliar information) from publishers who they select, again without any central coordination or authority. While some Atom clients were built as services available over the Web, thereby intermediating that communication, Atom does not require (or even encourage) that
style of deployment; although such services might be considered as centralised themselves, they are not part of the protocol itself.

Natural decentralization has obvious merit. However, it is not possible for a decentralized protocol to address some requirements -- in particular, when there is a requirement for a single, global 'source of truth' (e.g., for unambiguous naming), and when different endpoints need to solve the 'rendezvous problem' in order to communication without prior arrangement.


## Multi-Stakeholder Administration

When a function is required to be centralized by its nature, one way to mitigate the resulting effects is to assure that the central function is as limited as possible, and to delegate the administraiton of that function to a multi-stakeholder body.

A multi-stakeholder body is one that XXX

The most relevant example of this technique is the administration of the Domain Name System {{?RFC1035}}, which as a 'single source of truth' requires centralization of the naming function. To mitigate the effects, the function is carried out by multiple root servers that are administered by separate organizations -- themselves diverse in geography and a selection of corporate entities, non-profits and government bodies from many jurisdictions and affiliations.

Another example of multi-stakeholderism is the standardization of Internet protocols themselves. Because a specification effectively controls the behavior of implementations that are conformant with it, the standarization process can be seen as a single point of control. As a result, Internet standards bodies like the IETF allow open participation and contribution, make decisions in an open and accountable way, and take into account the views of different stakeholder groups {{?RFC8890}}.

yet another example is the administration of the Web's trust model, implemented by Web browsers as relying parties and Certificate Authorities as trust anchors. To assure that all parties meet the operational and security requirements necessary to provide the desired properties, the CAB Forum was established as an oversight body that involves both of those parties as stakeholders.

In each of these examples, setup and ongoing operation of a multi-stakeholder organization is not trivial. This is the major downside of such an approach. Additionally, the legitimacy of such an organization cannot be assumed, and may be difficult to establish and maintain. This concern is especially relevant if the function being coordinated is broad, complex, and/or contentious.


## Federation

Another technique for mitigating centralization in Internet protocols is federation - that is, designing protocols in such a way that new instances of the centralized function are relatively easy to create, without reducing value provided by the protocol. Typically, this means assuring that those instances can themselves interoperate, so that communication between two endpoints might traverse one or more intermediate servers.

The most prevalent (and successful) example of a federated Internet protocol is SMTP {{?RFC5321}}, as part of the e-mail suite of protocols. While e-mail uses DNS as the basis of naming, thereby leveraging existing mitigations in place for that protocol as described above, it still requires a way to route a message to a specific user based upon that address.

E-mail resolves this issue by defining a role for routing users' messages, the Message Transfer Agent (MTA), based upon information in the message. By allowing anyone to deploy a MTA and rules for interconnecting them, users can receive messages from other systems using SMTP. Users can (and often do) choose to delegate that role to someone else, or they can run it themselves. However, the latter is nowadays difficult, due to the likelihood of a small MTA being classified as a spam source by default. Because large MTA operaters are widely known and have greater impact if their operation is affected, they are less likely to be classified as such, thereby effectively centralizing the protocol's operation.

Another example of a federated Internet protocol is XMPP {{?RFC6120}}, supporting 'instant messaging' and similar functionality. Again using DNS for naming, federation is necessary in XMPP to facilitate rendezvous of users from different systems.

While some deployments of XMPP do support truly federated messaging (i.e., a person using service A can interoperably chat with someone using service B), many of the largest do not. Because federation is voluntary, some operators made a decision to attempt to capture their users into a single service, rather than provide the benefits of global interoperability.

The examples above show that federation can be a useful technique, but on its own is not sufficient to avoid centralization. If the value provided by a protocol can be captured by a single entity, they may consciously disable federation in order to attempt a 'winner take all' outcome -- a significant risk with many Internet protocols, since they often require rendezvous functions, and network effects seen on the Internet often promote such outcomes. Likewise, external factors (such as spam control) might naturally 'tilt the table' towards a few operators of these protocols.


# Considerations for Internet Protocols {#considerations}

## Intermediaries and Centralization

By definition, the introduction of an intermediary role -- i.e., a party that is required for communication to take place between endpoints -- is a centralization risk in protocols.


## Optional Centralization

Often, potentially centralized functions are optional in protocols -- either optional to implement, optional to use, or both.


## Platform Centralization

Some protocols might not directly define a central role, but they might facilitate centralization in the applications they support.

For example, HTTP {{HTTP}} in itself is not considered a centralized protocol; interoperable servers are relatively easy to instantiate, and multiple clients are available. It can be used without central coordination beyond that provided by DNS, as discussed above.

However, applications built on top of HTTP (as well as the rest of the 'Web Platform') often exhibit centralisation.

As such, HTTP is an example of a platform for centralization -- while the protocol itself is not centralized, it's possible to build centralized services and applications using it.


## External Centralization

Similar to platform centralization, a protocol might become centralized if external factors influence its deployment, making it difficult or impossible to realize the value provided by the protocol unless a central facility is used.

DoH {{?RFC8484}}

Cloud/CDN


## Protocol Evolution and Centralization




# Security Considerations

This document does not have direct security impact on Internet protocols. However, the failure to heed its advice might result in a myriad of security issues due to the unnecessary introduction of centralized function to Internet protocols.


--- back


# Acknowledgements

This document benefits from discussions with Brian Trammell during our shared time on the Internet Architecture Board.

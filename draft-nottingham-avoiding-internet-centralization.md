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

This document discusses aspects of centralization with regard to Internet protocol design. {{why}} explains why it is necessary for Internet protocols to avoid centralization. {{how}} surveys the techniques that can be used to do so, with varying effectiveness. {{design}} discusses interactions between centralization and various protocol design choices.

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

Likewise, the availability of the Internet (as well as applications and services based upon it) improves when there are many ways to obtain access to it and them.

To summarize, Internet protocols avoid centralization because allowing it would allow the Internet (or some part of it) to be captured by a single entity, effectively turning it into a 'walled garden' that fails to meet the architectural design goals of and user expectations for the Internet.


# Techniques for Avoiding Internet Centralization {#how}

When protocol designers are faced with the possibility of centralization, several techniques are available, depending on the nature of the protocol and its specific requirements. The following subsections discuss some of these options, as well as their advantages and disadvantages.


## Natural Decentralization

The preferred method for mitigating Internet Centralization is to avoid it completely -- in other words, to design protocols where no centralized coordination, rendezvous or communication is necessary.

Internet access
Routing
Atom

## Multi-Stakeholder Administration

When a function is required to be centralized by its nature, one way to mitigate the resulting effects is to assure that the central function is as limited as possible, and to delegate the administraiton of that function to a multi-stakeholder body.

A multi-stakeholder body is one that

DNS
CAs
Internet protocol standardisation

## Federation

Another technique for mitigating centralization in Internet protocols is federation - that is, designing protocols in such a way that new instances of the centralized function are relatively easy to create, without reducing value provided by the protocol. Typically, this means assuring that those instances can themselves interoperate, so that communication between two endpoints might traverse one or more intermediate servers.

XMPP
e-mail
identity

## Interoperability

Finally, some protocols might not directly define a central role, but their deployment might result in centralization due to external factors.

HTTP
DoH


# Centralization Considerations in Protocol Design {#design}

## Intermediaries {#intermediaries}


## Opt-In and Required Centralisation {#purposeful}


## Extensibility and Versioning {#evolution}


# Security Considerations


--- back


# Acknowledgements

This document benefits from discussions with Brian Trammell during our shared time on the Internet Architecture Board.

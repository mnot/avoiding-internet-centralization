---
title: "Centralization, Decentralization, and Internet Standards"
abbrev: Internet Centralization and Standards
docname: draft-nottingham-avoiding-internet-centralization-latest
date: {DATE}
category: info

ipr: trust200902
area: General
workgroup:
stream: independent
keyword: centralization
keyword: decentralization
keyword: consolidation
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
    target: https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1468-0491.2011.01550.x
    refcontent: "Governance: An International Journal of Policy, Administration, and Institutions, Vol. 25, No. 2, p. 237"
  ACCESS:
    display: ABRAHAMSON
    title: Essential Data
    date: 2014
    target: https://www.yalelawjournal.org/comment/essential-data
    author:
     -
      name: Zachary Abrahamson
    refcontent: Yale Law Journal, Vol. 124, No. 3
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
  AMBITION:
    display: SCHNEIDERb
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
  SCHNEIDER:
    display: SCHNEIDERa
    title: What to do once you admit that decentralizing everything never seems to work
    date: 17 October 2022
    author:
      - name: Nathan Schneider
    target: https://nathanschneider.info/articles/DecentralHacker.html
    refcontent: Hacker Noon
  BACCHI:
    title: "Introducing the ‘What’s the Problem Represented to be?’ approach"
    date: 2012
    author:
      - name: Carol Bacchi
    target: https://library.oapen.org/bitstream/handle/20.500.12657/33181/560097.pdf?sequence=1#page=34
    refcontent: Chapter 2, Engaging with Carol Bacchi
  ETHEREUM:
    title: "The Merge"
    author:
      -
       organization: Ethereum
    date: 4 February 2023
    target: https://ethereum.org/en/upgrades/merge/
  FB-INTERNET:
    title: "Regulators Seem to Think That Facebook Is the Internet"
    date: 6 August 2021
    author:
     - name: Konstantinos Komaitis
    target: https://slate.com/technology/2021/08/facebook-internet-regulation.html

--- abstract

This document discusses aspects of centralization that relate to Internet standards efforts. It argues that while standards bodies have little ability to prevent many forms of centralization, they can still make contributions that improve the Internet.


--- middle

# Introduction

One of the Internet's defining features is its lack of any single point of technical, political, or economic control. Arguably, that property assisted the Internet's early adoption and broad reach: because permission is not required to connect to, deploy an application on, or use the Internet for a particular purpose, it can meet diverse needs and be deployed in many different environments.

Although maintaining that state of affairs remains a widely shared goal, consistently preserving it across the range of services and applications that people see as "the Internet" has proven elusive. Whereas early services like NNTP and email had multiple, interoperable operators, most contemporary platforms for content and services are operated by single, commercial entities -- to the point where some have become so well-known and important to people's experiences that they are commonly mistaken for the Internet itself.{{FB-INTERNET}}

These difficulties call into question what role architectural design -- in particular, that overseen by open standards bodies such as the IETF -- can and should play in controlling centralization on the Internet.

This document discusses aspects of centralization that relate to Internet standards efforts. It argues that while standards bodies might be able to promote alternatives to technical centralization, their products are not able to control centralization. That said, there are still meaningful contributions that standards bodies can make.

The primary audience for this document is the engineers who design and standardize Internet protocols. Designers of proprietary protocols and applications can benefit from considering these issues, especially if they intend their work to be considered for eventual standardization. Policymakers can use this document to help characterise abuses that involve centralized protocols and applications and evaluate proposed remedies for them.

{{centralization}} defines centralization, explains why it is often undesirable but sometimes beneficial, and surveys how it occurs on the Internet. {{decentralization}} explores decentralization and highlights some relevant strategies, along with their limitations. Then, {{considerations}} makes recommendations about the role that Internet standards can play in controlling centralization. {{conclude}} concludes by identifying areas for future work.



# Centralization {#centralization}

For the purposes of this document, "centralization" is the state of affairs where a single entity or a small group of them can observe, capture, control, or extract rent from the operation or use of an Internet function exclusively.

Here, "entity" could be a person, group, or corporation. An organization might be subject to governance that mitigates centralization risk (see {{multi}}), but that organisation is still a centralizing entity.

"Internet function" is used broadly in this document. Most directly, it might be an enabling protocol already defined by standards, such as IP {{?RFC791}}, BGP {{?RFC4271}}, TCP {{?RFC793}}, or HTTP {{HTTP}}. It might also be a proposal for a new enabling protocol, or an extension to an existing one.

Because people's experience is not limited to standards-defined protocols, this document also considers centralization in applications built on top of standard protocols -- for example, social networking, file sharing, financial services, and news dissemination. Likewise, the networking equipment, hardware, operating systems, and software that act as enabling technologies can also impact centralization. The supply of Internet connectivity to end users in a particular area or situation can exhibit centralization, as can the supply of transit between networks (so called "Tier 1" networks).

This definition does not capture all types of centralization. Notably, technical centralization (where, for example, a machine or network link is a single point of failure) is relatively well-understood by engineers, and can be mitigated by designing a design that distributes a function across multiple components. As we will see, these techniques might address that type of centralization while failing to prevent control of the function falling into few hands. A failure because of a cut cable, power outage, or failed server is well-understood by the technical community, but qualitatively different from the issues encountered when a core Internet function has a gatekeeper.

Likewise, political centralization (where a country is able to control how a function is supplied across the whole Internet) is equally concerning, but outside the scope of this document.

Centralization is not a binary condition: a function might be vulnerable to it to various degrees. For example, a function that effectively uses federation ({{federation}}) to enable easy switching between instances might have still be at risk of centralization, but not as great as one that had a single, proprietary provider. Some centralization risk is mitigated so effectively that they are not commonly perceived as being centralized at all.


## Centralization Can Be Harmful {#why}

Many engineers who participate in Internet standards efforts have an inclination to prevent and counteract centralization because they see the Internet's history and architecture as incompatible with it. As a "large, heterogeneous collection of interconnected systems" {{?BCP95}} the Internet is often characterised as a "network of networks" who relate as peers that agree to facilitate communication, rather than having a relationship of subservience to others' requirements or coercion by them. This focus on independence of action is prevalent in the Internet's design -- for example, in the concept of an "autonomous system".

This oft-seen reluctance to countenance centralization is also rooted in the many potentially damaging effects that have been associated with centralization, including:

* _Power Imbalance_: When a third party has unavoidable access to communications, the informational and positional advantages gained allow observation of behavior (the "panopticon effect") and shaping or even denial of behavior (the "chokepoint effect") {{INTERMEDIARY-INFLUENCE}} -- capabilities that those parties (or the states that have authority over them) can use for coercive ends {{INTERDEPENDENCE}} or even to disrupt society itself. Just as good governance of states requires separation of powers {{FEDERALIST-51}}, so too does good governance of the Internet require that power (whether that be economic or political) not be consolidated in one place without appropriate checks and balances.

* _Limits on Innovation_: A party with the ability to control communication can preclude the possibility of "permissionless innovation" -- the ability to deploy new, unforeseen applications without requiring coordination with parties other than those you are communicating with.

* _Constraints on Competition_: The Internet and its users benefit from robust competition when applications and services are available from many providers -- especially when those users can build their own applications and services based upon interoperable standards. When a centralized service or platform must be used because no substitutes are suitable, it effectively becomes an essential facility, which facilitates abuse of power.

* _Reduced Availability_: Availability of the Internet (and applications and services built upon it) improves when there are many ways to obtain access. While service availability can benefit from the focused attention of a large centralized provider, that provider's failure can have a disproportionate impact on availability.

* _Monoculture_: The scale available to a centralized provider can magnify minor flaws in features to a degree that can have broad consequences. For example, a single codebase for routers elevates the impact of a bug or vulnerability; a single recommendation algorithm for content can have severe social impact. Diversity in functions’ implementation leads to a more robust outcome when viewed systemically, because "progress is the outcome of a trial-and-error evolutionary process of many agents interacting freely." {{POLYCENTRIC}}

* _Self-Reinforcement_: As widely noted (see, e.g., {{ACCESS}}), a centralized provider's access to data allows it the opportunity to make improvements to its offerings, while denying such access to others.

The relationship between these harms and centralization is often complex; it is not always the case that centralization will lead to them, and when it does, there is not always a direct and simple tradeoff. This makes it important to critically evaluate claims of centralization before allowing them to influence protocol design.

For example, the relationship between availability and centralization is not a straightforward tradeoff. A centrally operated system might be more available because of factors like the resources available to a larger operator, but also have greater impact when a fault is encountered; decentralized systems might be more resilient in the face of local failures, but less able to react to systemic issues.

This tension can be seen in areas like the cloud and mobile Internet access. If a cloud hosting provider were to become unavailable (whether for technical or other reasons), many people's experience of the Internet might be disrupted. Likewise, a mobile Internet access provider might have an outage that affects hundreds, thousands, or more of its users. In both cases, centralization is not indicated by the loss of availability or its scale, but it well might be if the parties relying on the function don't have reasonable options to switch to if they are unhappy with the availability of the service provided, or if friction against switching to an alternative is too great.

Competitive constraints provide another example of a need for nuance. While making the Internet more competitive may be a motivation for many engineers, only courts (and sometimes, regulators) have the authority to define a relevant market and determine that a behavior is anti-competitive. What might be considered undesirable centralization by the technical community might not attract competition regulation. Conversely, what might attract competition regulation might not be of great concern to the technical community if other mitigations are felt to be adequate.


## Centralization Can Be Helpful {#necessary}

The potential harms of centralization listed above are widely appreciated. Less widely explored is the reliance on centralization by some protocols and applications to deliver their functionality.

Often, centralization is present due to technical necessity. For example, a single, globally coordinated “source of truth” is by nature centralized -- such as in the root zone of the Domain Name System (DNS), which allows human-friendly naming to be converted into network addresses in a globally consistent fashion.

Or, consider IP address allocation. Internet routing requires addresses to be allocated uniquely, but if a single government or company were to capture the addressing function, the entire Internet would be at risk of abuse by that entity. Similarly, the Web's trust model requires a Certificate Authority to serve as the root of trust for communication between browsers and servers, bringing centralization risk that needs to be considered in the design of that system.

Protocols that need to solve the "rendezvous problem" to coordinate communication between two parties who are not in direct contact also require centralization. For example, chat protocols need to coordinate communication between two parties that wish to talk; while the actual communication can be direct between them (so long as the protocol facilitates that), the endpoints' mutual discovery typically requires a third party at some point. From the perspective of those two users, the rendezvous function is centralized.

Even when not strictly necessary, centralization can be deployed to beneficial ends. {{AMBITION}} notes that "centralized structures can have virtues, such as enabling publics to focus their limited attention for oversight, or forming a power bloc capable of challenging less-accountable blocs that might emerge. Centralized structures that have earned widespread respect in recent centuries – including governments, corporations, and nonprofit organizations – have done so in no small part because of the intentional design that went into those structures."

This can be seen when a function requires governance to realize common goals and protect minority interests. For example, content moderation functions impose community values, but can also be viewed as a choke point. Likewise, complex and risky functions like financial services (e.g., credit card processing) can be seen as beneficially centralized into relatively few, specialized organizations, where they can receive the focused attention that they require.

When centralization is purposefully used like this, Internet protocols often attempt to mitigate the associated risks using measures such as federation (see {{federation}}) or governance structures (see {{multi}}). Protocols that successfully do so are often reused to avoid the considerable cost and risk of re-implementing those mitigations. For example, if a protocol requires a coordinated, global naming function, incorporating the Domain Name System is usually preferable to establishing a new system.

Ultimately, deciding when centralization is beneficial is a judgment call. Some protocols cannot function without a centralized function; others might be significantly enhanced for certain use cases if a function is centralized, or might merely be more efficient.


# Decentralization {#decentralization}

While the term "decentralization" has a long history of use in economics, politics, religion, and international development, Baran gave one of the first definitions relevant to computer networking, as a condition when "complete reliance upon a single point is not always required." {{RAND}}

Avoiding technical centralization -- while not a trivial topic -- is relatively well understood. Avoiding all centralization using only technical tools (like protocol design) is considerably more difficult. Several issues are encountered.

First, identifying which aspects of a function to decentralize and how to do so can be difficult, both because there are often many interactions between different types and sources of centralization, and because centralization sometimes only becomes clear after the function is deployed at scale.

Indeed, efforts to decentralize often have the effect of merely shifting centralization to a different place -- for example, in its governance, implementation, deployment, or in ancillary functions. In other words, "decentralized technology alone does not guarantee decentralized outcomes." {{SCHNEIDER}}

For example, a cloud storage function might be implemented using a distributed consensus protocol, assuring that the failure of any single node will not affect the system's operation or availability. In that sense, it is technically decentralized. However, if it is operated by a single legal entity, that implies centralization -- especially if there are few other options available, or if there is friction against choosing other options.

Another example is the Web, which was envisioned and widely held to be a decentralizing force in its early life. Its potential as an enabler of centralization only became apparent when large sites successfully leveraged network effects for dominance of social networking, marketplaces, and similar functions.

Second, different parties might have good-faith differences on what "sufficiently decentralized" means based upon their beliefs, perceptions and goals. Just as centralization is a continuum, so is decentralization, and not everyone agrees what the "right" level or type is, how to weigh different forms of centralization against each other, or how to weigh potential centralization against other architectural goals (such as security or privacy).

These tensions can be seen, for example, in the DNS. While much of the system is decentralized through the distribution of the lookup function to local servers that users have the option to override, the DNS is also a name space -- a single, global "source of truth" with inherent (if beneficial) centralization in its management. ICANN mitigates the associated risk through multi-stakeholder governance (see {{multi}}). While many believe that this arrangement is sufficient and might even have desirable qualities (such as the ability to impose community standards over the operation of the name space), others reject ICANN's oversight of the DNS as illegitimate, favoring decentralization based upon distributed consensus protocols rather than human governance. {{MUSIANI}}

Third, decentralization unavoidably involves adjustments to the power relationships between protocol participants, especially when it opens up the possibility of centralization elsewhere. As Schneider notes in {{AMBITION}}, decentralization "appears to operate as a rhetorical strategy that directs attention toward some aspects of a proposed social order and away from others", so "we cannot accept technology as a substitute for taking social, cultural, and political considerations seriously." Or, more bluntly, "without governance mechanisms in place, nodes may collude, people may lie to each other, markets can be rigged, and there can be significant cost to people entering and exiting markets." {{PERSPECTIVE}}

For example, while blockchain-based cryptocurrencies purport to address the centralization inherent in traditional currencies through technical means, many exhibit considerable concentration of power due to voting/mining power, distribution of funds, and diversity of codebase. {{AREWEDECENTRALIZEDYET}} Over-reliance on technical measures brings an opportunity for latent, informal power structures that have their own risks -- including centralization. {{STRUCTURELESS}}

In practice, this means that decentralizing a function requires considerable work, is inherently political, and involves a large degree of uncertainty about the outcome. If one considers decentralization as a larger social goal (in the spirit of how the term is used in other, non-computing contexts), merely rearranging technical functions may lead to frustration. "A distributed network does not automatically yield an egalitarian, equitable or just social, economic, political landscape." {{PERSPECTIVE}}


## Decentralization Strategies {#techniques}

Despite the inherent issues in achieving decentralization through solely technical means, a few technical strategies are sometimes promoted as addressing other forms of centralization. This section examines some, along with their limitations.


### Federation {#federation}

Protocol designers often attempt to address centralization through federation: designing a function in a way that uses independent instances who maintain connectivity and interoperability to provide a single, cohesive service. Federation promises to allow users to choose the instance they associate with and accommodates substitution of one instance for another, lowering switching costs.

However, federation alone is insufficient to prevent or mitigate centralization of a function, because non-technical factors can create pressure to use a central solution.

For example, the e-mail suite of protocols needs to route messages to a user even when that user changes network locations or becomes disconnected for a long period. To facilitate this, SMTP {{?RFC5321}} defines a specific role for routing users' messages, the Message Transfer Agent (MTA). By allowing anyone to deploy an MTA and defining rules for interconnecting them, the protocol avoids the use of a single, central server. Users can (and often do) choose to delegate that role to someone else, or can run their own MTA.

Despite this design, e-mail exhibits a degree of centralization. Part of the reason is a side effect of spam controls; many now consider running a personal MTA to be impractical because of the likelihood of a small MTA being classified as a spam source. Because large MTA operators are widely known and have greater impact if their operation is affected, they are less likely to be classified as such -- creating pressure towards centralization.

XMPP {{?RFC6120}} is a chat protocol that demonstrates another issue with federation: the voluntary nature of technical standards. Like e-mail, XMPP is federated to facilitate rendezvous of users from different systems - if they allow it.

While some XMPP deployments do support truly federated messaging (i.e., a person using service A can interoperably chat with someone using service B), many of the largest do not. Because federation is voluntary, some operators captured their users into a single service, denying them the benefits of global interoperability.

The examples above illustrate that, while federation can create the conditions necessary for a function to be decentralized, it does not guarantee that outcome.


### Distributed Consensus {#distributed}

Increasingly, distributed consensus technologies (such as the blockchain) are touted as a solution to centralization. A complete survey of this rapidly changing area is beyond the scope of this document, but we can generalize about its properties.

These techniques attempt to avoid centralization by distributing functions to members of a sometimes large pool of protocol participants. They typically guarantee proper performance of a function using cryptographic techniques (often, an append-only transaction ledger). A particular task's assignment to a node for handling usually cannot be predicted or controlled.

Sybil attacks (where a party or coordinated parties cheaply create enough protocol participants to affect how consensus is judged) are a major concern for these protocols. They encourage diversity in the pool of participants using indirect techniques, such as proof-of-work (where each participant has to show a significant consumption of resources) or proof-of-stake (where each participant has some other incentive to execute correctly).

Even when distributed consensus is used for all technical functions of a service, some coordination is still necessary -- whether that is through governance of the function itself, creation of shared implementations, or documentation of shared wire protocols. That suggests a path for centralization, just of an indirect nature. For example, the Ethereum "merge" demonstrated that the blockchain could address environmental concerns, but only through coordinated community effort and governance. {{ETHEREUM}}

Furthermore, a protocol or an application can use distributed consensus for some functions, but still be centralized elsewhere -- either because those functions cannot be decentralized (most commonly, rendezvous and global naming; see {{necessary}}) or because the designer has chosen not to because of the associated costs and lost opportunities.

These potential shortcomings do not rule out the use of distributed consensus technologies in every instance, but they do merit caution against uncritically relying upon these technologies to avoid or mitigate centralization.


### Operational Governance {#multi}

Sometimes technologists attempt to mitigate centralization by incorporating a governance mechanism into a protocol's operation. Often, this is through the establishment of a multi-stakeholder body: an institution that includes representatives of the different kinds of parties that are affected by the system's operation ("stakeholders") in an attempt to make well-reasoned, legitimate, and authoritative decisions.

The most widely studied example of this technique is the governance of the DNS name space, which as a “single source of truth” exhibits centralization. The associated risk is managed through administration by [the Internet Corporation for Assigned Names and Numbers (ICANN)](https://www.icann.org/resources/pages/governance/governance-en), a global multi-stakeholder body with representation from end users, governments, operators, and others.

Another example is the governance of the Web's trust model, implemented by Web browsers as relying parties and Certificate Authorities as trust anchors. To promote the operational and security requirements necessary to provide the desired properties, the [CA/Browser Forum](https://cabforum.org) was established as an oversight body that involves both parties as stakeholders.

These examples are notable in that the governance mechanism is not specified in the protocol documents directly; rather, they are layered on operationally, but in a manner that takes advantage of protocol design features that enable the imposition of governance.

Governance in this manner is best suited to very limited functions, like the examples above. Even then, setup and ongoing operation of a governance mechanism is not trivial, and their legitimacy may be difficult to establish and maintain (see, e.g., {{MULTISTAKEHOLDER}}); by their nature, they are vulnerable to capture by the interests that are being governed.


# What Can Internet Standards Do? {#considerations}

Given the limits of decentralization techniques like federation and distributed consensus, the voluntary nature of standards compliance, and the powerful forces that can drive centralization, it is reasonable to ask what standards efforts like those at the IETF can do to accommodate helpful centralization while avoiding the associated harms -- while acknowledging that the distinction itself is a judgment call, and inherently political.

The subsections below suggest a few concrete, meaningful steps that standards bodies can take.


## Bolster Legitimacy {#legitimate}

While technical standards have only limited ability to control centralization of the Internet, legal standards (whether regulation, legislation, or case law) show more promise. However, regulating the Internet is risky without a firm grounding in the effects on the architecture, informed by a technical viewpoint.

That viewpoint can and should be provided by the Internet standards community. To effectively do so, its institutions must be seen as legitimate by the relevant parties -- for example, by competition regulators. If the IETF is perceived as representing or being controlled by "big tech" concerns, its ability to guide decisions that affect the Internet will be diminished considerably.

The IETF already has features that arguably provide considerable legitimacy; for example, open participation and representation by individuals rather than companies both enhance input legitimacy; a well-defined process with multiple layers of appeals and transparency contributes to throughput legitimacy, and a long history of successful Internet standards provides perhaps the strongest source of legitimacy for the IETF -- its output.

However, it is also widely recognized the considerable costs (not just financial) involved in successfully participating in the IETF have a tendency to favour larger companies over smaller concerns. Additionally, the specialised and highly technical nature of the work creates barriers to entry for non-technical stakeholders. These factors have the potential to reduce the legitimacy of the IETF's decisions, at least in some eyes.

Efforts to address these shortcomings are ongoing; see, for example, {{?RFC8890}}. Overall, bolstering the legitimacy of the organization should be seen as a continuous effort.

When engaging in external efforts, the IETF community (especially, its leadership) should keep firmly in mind that it is most authoritative when focused on technical and architectural impact. Straying from these topics will likely result in a loss of legitimacy that would likely be difficult to recover from.


## Focus Discussion of Centralization {#target}

Centralization and decentralization are increasingly being raised in technical standards discussions. Any claims needs to be critically evaluated; as discussed in {{centralization}}, not all centralization is automatically harmful, and per {{decentralization}}, decentralization techniques do not automatically address all centralization harms -- and they may bring their own risks.

Claims of centralization can be proxies for power struggles between actors with competing interests. A protocol that is deployed by a large, centralized service does not necessarily cause that centralization, but a competitor might use a claim of centralization to deny them the benefit of standardization.

Therefore, approaches like requiring a "Centralization Considerations" section in drafts, gatekeeping publication on a centralization review, or committing significant resources to searching for centralization in protocols are unlikely to improve the Internet.

Refusing to standardize a protocol because it does not actively prevent all forms of centralization ignores the very limited power that standards efforts have to do so. Almost all existing Internet protocols -- including IP, TCP, HTTP, and DNS -- fail to do so. While the imprimatur of an Internet Standard is not without value, merely withholding it cannot prevent these sources of centralization.

When claims are made that a given proposal is "centralized" or "decentralized", the context of those statements should be examined for presuppositions, assumptions, and omissions. One framework for critical interrogations is offered by {{BACCHI}}, which can be adapted for centralization-related discussions:

1. What is the nature of the (de)centralization that is represented as being problematic?
2. What deep-seated presuppositions or assumptions (conceptual logics) underlie this representation of the "problem"?
3. How has this representation of the problem come about?
4. What is left unproblematic in this problem representation? Where are the silences? Can the "problem" be conceptualized differently?
5. What effects are produced by this representation of the “problem”?
6. How and where has this representation of the “problem” been produced, disseminated, and defended? How has it been and/or how can it be disrupted and replaced?

Discussions should focus on whether claimed centralization is harmful or, if helpful, whether it is justified. Centralization is concerning when it is not broadly held to be necessary, when it has no checks, balances, or other mechanisms of accountability, when it selects "favorites" which are difficult (or impossible) to displace, and when it threatens the architectural features that make the Internet successful.

{{SCHNEIDER}} implores that proposals to decentralize be "really, really clear about what particular features of a system a given design seeks to decentralize" and promotes borrowing remedies from more traditional governance systems, such as separation of powers and accountability.

When centralization is found, standards efforts should consider its relationship with architectural goals as they consider how and if it should be mitigated (if possible). In particular, attention should be paid to how effective standards (as a form of architectural control) is in achieving each goal.

For example, privacy is often more effectively ensured by ex ante technical constraints, as compared to ex post legal regulation. Conversely (as discussed) some centralization may be more effectively addressed through legal regulation. Thus, a standards effort balancing these concerns might bias towards privacy, after informed discussion.


## Target Proprietary Functions {#up}

Functions that are currently only available from proprietary providers are ripe for standardisation efforts. That might include large-scale protocols for existing proprietary functions (e.g., chat) as well as smaller efforts to improve interoperability and portability of specific features that are often used to users into a platform; for example, a format for lists of contacts in a social network.

A common objection to this approach is that adoption is voluntary, not mandatory; there are no "standards police" to mandate their use or enforce correct implementation. For example, specifications like {{ACTIVITYSTREAMS}}) were available for some time without being used in a federated manner by commercial social networking providers.

However, while standards aren't mandatory, legal regulation is, and legal mandates for interoperability are increasingly discussed by policymakers as a remedy for competition issues (see, e.g., {{OECD}}).

As such, appetite for regulation presents an opportunity for new specifications to decentralize these functions, backed by a legal mandate in combination with changing norms and the resulting market forces {{NEW-CHICAGO}}. That opportunity also presents a risk, if the resulting legal regulation is at odds with the Internet architecture.

Successfully creating standards that work in concert with legal regulation presents many potential pitfalls, and will require improved and new capabilities (especially liaison), and considerable effort. If the Internet community does not make that effort, it is likely that regulators will turn to other sources of interoperability specifications -- most likely, with less transparency, more narrow input, limited experience, and without reference to the Internet’s architectural goals.


## Enable Switching {#balance}

To minimize centralization, specifications should have an explicit goal of facilitating users' switching between implementations and deployments of the functions they define or enable.

One necessary condition for switching is the availability of alternatives; breadth and diversity of implementation and deployment are required. For example, if there is only a single implementation of a protocol, applications that use it are vulnerable to the control it has over their operation. Even Open Source projects can be an issue in this regard if there are factors that make forking difficult (for example, the cost of maintaining that fork). {{Section 2.1 of ?RFC5218}} explores some factors in protocol design that encourage diversity of implementation.

The cost of substituting an alternative implementation or deployment by users is another important factor to consider. This includes minimizing the amount of time, resources, expertise, coordination, loss of functionality, and effort required to use a different provider or implementation -- with the implication that the standard needs to be functionally complete and specified precisely enough to allow substitution.

These goals of completeness and diversity are sometimes in tension. If a standard becomes extremely complex, it may discourage implementation diversity because the cost of a complete implementation is too high (consider: Web browsers). On the other hand, if the specification is too simple, it may not enable easy switching, especially if proprietary extensions are necessary to complete it (see {{evolution}}).

One objection to protocols that enable easy switching is that they reduce the incentives for implementation by commercial vendors. While a completely commoditized protocol might not allow implementations to differentiate themselves, they provide opportunities for specialization and improvement elsewhere in the value chain {{ATTRACTIVE-PROFITS}}. Well-timed standards efforts leverage these forces to focus proprietary interests on top of open technology, rather than as a replacement for it.


## Control Delegation of Power {#intermediation}

Some functions might see substantial benefits if they are provided by a third party in communication. Adding a new party to communication can improve:

* _Efficiency_: Many functions on the Internet are more efficient when performed at a higher scale. For example, a content delivery network can offer services at a fraction of the financial and environmental cost that someone serving content themselves would otherwise pay, because of the scale they operate at. Likewise, a two-sided market platform can introduce sizeable efficiencies over pair-wise buyer/seller trading {{CIRCULAR-CONUNDRUM}}.

* _Simplicity_: Completely disintermediating communication can shift the burden of functions onto endpoints. This can cause increased cognitive load for users; for example, compare commercial social networking platforms with self-hosted efforts.

* _Specialization_: Having a function consolidated into a few hands can improve outcomes because of the resulting specialization. For example, services overseen by professional administrators are often seen to have a better security posture and improved availability.

* _Privacy_: For some functions, user privacy can be improved by consolidating their activity to prevent individual behaviors from being discriminated from each other.{{MIX}} Introduction of a third party can also enforce functional boundaries -- for example, to reduce the need for users to trust potentially malicious endpoints, as seen in the so-called “oblivious” protocols (e.g., {{?RFC9230}}) that allow end users to hide their identity from services, while still accessing them.

However, if that new party is able to make their participation "sticky" -- for example, by leveraging their position in the network to require use of an intermediary, by exploiting their access to data, or by making it difficult to switch to another provider of the function -- there is a risk of centralization.

Most often, third parties are added to functions as "intermediaries" or in designated "agent" roles. Designing such functions with thoughtful constraints on these roles can prevent at least the most egregious abuses of such power.

When adding new parties to communication into a protocol, two techniques have proven useful: first, third parties should only be interposed into communication when at least one of the primary parties takes a positive action to do so. Second, these parties should have their ability to observe or control communication limited to what is necessary to perform their intended function.

For example, early deployments of HTTP allowed intermediaries to be interposed by the network without knowledge of the endpoints, and those intermediaries could see and change the full content of traffic by default -- even when they are only intended to perform basic functions such as caching. Because of the introduction of HTTPS and the CONNECT method (see {{Section 9.3.6 of HTTP}}), combined with efforts to encourage its adoption, those intermediaries are now required to be explicitly interposed by one endpoint, and they only have access to basic routing information.

See {{?I-D.thomson-tmi}} for more guidance on protocol intermediation.

The term "intermediary" is also used (often in legal and regulatory contexts) more broadly than it has been in protocol design; for example, an auction Web site intermediates between buyers and sellers is considered an intermediary, even though it is not formally an intermediary in HTTP (see {{Section 3.7 of HTTP}}). Protocol designers can address the centralization associated with this kind of intermediation by standardising the function, rather than restricting the capabilities of the underlying protocols; see {{up}}.


### Enforce Layer Boundaries {#network}

Most Internet protocols and applications depend on other, "lower-layer" functions and their implementations. The features, deployment, and operation of these dependencies can surface centralization into functions and applications built "on top" of them.

For example, application-layer protocols require a network to function, and therefore a degree of power over communication is available to the network provider. They might block access to, slow down, or change the content of a specific service for financial, political, operational, or criminal reasons, creating a disincentive (or even removing the ability) to use a specific provider of a function. By selectively hindering the use of some services but not others, network interventions can be composed to create pressure to use those other services -- intentionally or not.

Techniques like encryption can discourage such centralization by enforcing layer boundaries. When the number of parties who have access to the content of communication is limited, parties at lower layers can be prevented from interfering with and observing it. Although those lower-layer parties might still prevent communication, encryption also makes it more difficult to discriminate a target from other users' traffic.


## Consider Extensibility Carefully {#evolution}

The Internet's ability to evolve is critical, allowing it to meet new requirements and adapt to new conditions without requiring a “flag day” to upgrade implementations. Typically, functions accommodate evolution by defining extension interfaces, which allow optional features to be added or change over time in an interoperable fashion.

However, these interfaces can also be leveraged by a powerful entity if they can change the target for meaningful interoperability by adding proprietary extensions to a standard. This is especially true when the core standard does not itself provide sufficient utility on its own.

For example, the SOAP protocol's {{SOAP}} extreme flexibility and failure to provide significant standalone value allowed vendors to require use of their preferred extensions, favoring those who had more market power.

Therefore, standards efforts should focus on providing concrete utility to the majority of their users as published, rather than being a “framework” where interoperability is not immediately available. Internet functions should not make every aspect of their operation extensible; boundaries between modules should be designed in a way that allows evolution, while still offering meaningful functionality.

Beyond allowing evolution, well-considered interfaces can also aid decentralization efforts. The structural boundaries that emerge between the sub-modules of the function -- as well as those with adjacent functions -- provide touchpoints for interoperability and an opportunity for substitution of providers.

In particular, if the interfaces of a function are well-defined and stable, there is an opportunity to use different providers for that function. When those interfaces are open standards, change control resides with the Internet community instead of remaining in proprietary hands, further enhancing stability and enabling (but not ensuring) decentralization.


# Future Work {#conclude}

This document has argued that while standards bodies have little means of effectively controlling or preventing centralization on the Internet, there are still concrete and useful steps they can take to improve the Internet in this regard.

Those steps might be elaborated upon and extended in future work; doubtless there is more that can be done. New decentralization techniques might be identified and examined; what we learn from relationships with other, more effective regulators in this space can be documented.

Some have suggested creating a how-to guide or checklist for dealing with centralization. Because centralization is so contextual and so varied in how it manifests, this might best be attempted within very limited areas; for example, for a particular type of function, or a function at a particular layer.


# Security Considerations

This document does not have a direct security impact on Internet protocols. That said, failure to consider centralization might cause a myriad of security issues; see {{why}} for a preliminary discussion.


--- back


# Acknowledgements

This document was born out of early discussions with Brian Trammell during our shared time on the Internet Architecture Board.

Special thanks to Geoff Huston and Milton Mueller for their well-considered, thoughtful, and helpful comments.

Thanks also to Jari Arkko, Kristin Berdan, Christian Huitema, Mallory Knodel, Eliot Lear, John Levine, Tommy Pauly, and Martin Thomson for their comments and suggestions.

No large language models were used in the production of this document.

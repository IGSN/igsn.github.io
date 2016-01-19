---
layout: page
title: Organisation and Governance
---

The application and long-term utility of sample­ based data is critically dependent on, availability of information (metadata) about the samples, links to other data sets derived from individual samples, and access to the samples themselves. Major problems for achieving this include incomplete documentation of samples in publications, use of ambiguous sample names, and the lack of web accessible catalogues that allows finding out about existing samples and their archiving location. Using persistent identifiers for physical samples, such as the International Geo Sample Number (IGSN), provides solutions. Read more on [how to use](../syntax) IGSN as an investigator, author, data centre, publisher ...

The IGSN Implementation Organisation (IGSN e.V.) offers a system of unique persistent identifiers for samples. The objective of the IGSN e.V. is to implement and promote standard methods for locating, identifying, and citing physical samples with confidence by operating an international IGSN registration service with a distributed infrastructure for use by and benefit to its members. Each scientific community has different needs how to reference physical sample materials, yet all communities benefit from the ability to identify samples in a globally unique and persistent way.

The IGSN Implementation Organization (IGSN e.V.) provides the organisational and [technical](system) backbone for scientific communities to apply globally unique and resolvable, actionable, and persistent identifiers for physical sample materials. Read more on the organisation and governance of IGSN and its [technical implementation](../system) … 

Use of persistent identifiers in digital data systems allows building linkages between the digital representation of samples (sample profiles) in community governed portals and their related data in the literature and in web­ accessible digital data repositories. This system is open to scientific communities outside of geology. Physical sample materials encompass any materials referenced for scientific purposes, e.g. minerals, rocks, water samples, holotypes, collection specimens, reference materials, and other types of physical sample materials. Read more on IGSN [communities of practice](../communities) …

A core element of the implementation of globally unique and persistent identifiers for physical sample materials is a handle server ([Handle System](https://en.wikipedia.org/wiki/Handle_System)) to resolve IGSN handles to the URL of the respective sample description at the collection/repository. This server is operated by the IGSN Implementation Organisation (IGSN e.V.). Read more on the [technical implementation](../system) of IGSN …

IGSN is **not a database** for samples. Discipline specific databases are operated by the respective scientific communities and IGSN, as persistent identifiers, help to reference samples in discipline specific sample catalogues. Read more on IGSN [system architecture](../system) and IGSN [communities of practice](../communities) …

IGSN e.V. does **not prescribe a naming scheme** for samples. Communities are free to govern their IGSN namespaces according to their needs. Using IGSN ensures that samples can be uniquely identified. Read more on IGSN [naming conventions](../syntax) …

IGSN does **not prescribe a standard metadata scheme**. Metadata schemes in community databases are defined by the respective scientific communities to best serve their needs for sample discovery and reference. Read more on IGSN [metadata](../metadata) …


The application and long-term utility of sample­ based data is critically dependent on

  * availability of information (metadata) about the samples such as geographical location and time of sampling,
  * links to other data sets derived from individual samples that are dispersed in the literature and in digital data repositories, and 
  * access to the samples themselves.

Major problems for achieving this include incomplete documentation of samples in publications, use of ambiguous sample names, and the lack of a central catalogue that allows finding a sample's archiving location.

Using persistent identifiers for physical samples, such as the International GeoSample Number (IGSN), provides solutions. The IGSN Implementation Organisation (IGSN e.V.) offers a system of unique persistent identifiers for samples. Use of persistent identifiers in digital data systems allows building linkages between the digital representation of samples (sample profiles) in community governed portals and their related data in the literature and in web­ accessible digital data repositories.

This system is open to scientific communities outside of geology.



## Aim and scope ##

Each scientific community has different needs how to reference physical sample materials, yet all communities benefit from the ability to identify samples in a globally unique and persistent way. The IGSN Implementation Organization (IGSN e.V.) provides the organisational and technical backbone for scientific communities to apply globally unique and resolvable, actionable, and persistent identifiers for physical sample materials.

Physical sample materials encompass any materials referenced for scientific purposes, e.g. minerals, rocks, water samples, holotypes, collection specimens, reference materials, and other types of physical sample materials.

IGSN e.V. is **not a database** for samples. Discipline specific databases are operated by the respective scientific communities.

IGSN e.V. does **not prescribe a naming scheme** for samples. Communities are free to govern their IGSN namespaces according to their needs.

IGSN e.V. is **not a standard metadata scheme**. Metadata schemes in community databases are defined by the respective scientific communities. 

## Entities and Roles ##

This section describes the entities and roles in the IGSN [organisational structure](../statutes).

   * Allocating Agent: An [Allocating Agent](../agents) ([Statutes §3.1](../statutes)) is a member institution which registers IGSNs in the IGSN registry and resolver service.
   * The IGSN Implementing Organization e.V. operates the IGSN registry and resolver servie on behalf of the IGSN members ([Statutes §2.2.2](../statutes)).
   * The Managing Agent ([Statutes §3.2](../statutes)) is entrusted with the operation of the IGSN Office and with the day-to-day operation of the IGSN registration Agency.


## International ##

A core element of the implementation of globally unique and persistent identifiers for physical sample materials is a handle server ([Handle System](https://en.wikipedia.org/wiki/Handle_System)) to resolve IGSN handles to the URL of the respective sample description at the collection/repository. This server is operated by the IGSN Implementation Organisation (IGSN e.V.). The constitution of the IGSN Implementation Organisation as an incorporated not-for-profit association under German law was chosen to provide a legal framework for the long-term operation of the system.

At this level, the IGSN web service requires only very limited metadata, e.g. IGSN/URL pair, registrant, date of registration, etc.


## Communities ##

Samples and collections are embedded into specific user communities and organisations. The abilities to provide metadata may vary considerably between communities. At the same time each community requires different metadata. At this level of detail, a "one size fits all" approach will not work. Therefore, the registration of samples, and their description in metadata, is delegated to members of the community. These communities are federated in domain specific portals.



![IGSN simplified system architecture](../media/igsn_simple_architecture.png)

*Simplified system architecture of the IGSN registration.*

Clients register samples together with metadata through their Allocating Agents. The Allocating Agents registers the IGSN at the IGSN Registration Agency and keeps a catalogue of all samples registered through by this agent. The catalogues of registered samples are harvested and compiled into metadata portals to make samples searchable and accessible.



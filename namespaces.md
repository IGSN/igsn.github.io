---
layout: page
title: Namespaces
---
IGSN uses a hierarchical namespace governance model to ensure uniqueness of registered IGSN.

Please refer to the [list of registered IGSN namespaces](../registered).

## Namespaces Allocation Procedure ##

The current procedure for namespace allocation was agreed by the IGSN members during the [IGSN telecon on 15 April 2013].

  - IGSN e.V. uses a hierarchical model to govern its namespace.
  - Top-level namespaces are governed and assigned by IGSN e.V.
  - [Allocating Agents](../agents) may apply for the allocation of namespaces by IGSN e.V. and associate an URI with it.
  - The process of allocating a new namespace is initiated by an Allocating Agent requesting the allocation of a namespace by creating a new ticket in the IGSN Issue Tracker. <https://github.com/IGSN/igsn.github.io/issues>
  - The request is reviewed by the IGSN Manager. Conflicting interests are reviewed and mediated by the Executive Board. Cases the Executive Board cannot resolve are referred to the General Assembly to decide.
  - The approved namespace is added to the IGSN Metadata Store <https://doidb.wdc-terra.org/igsn/> and [advertised on the IGSN technical website](../registered).
  - Allocating Agents may extend their allocated namespaces into sub-namespaces by adding characters or numbers. The allocated namespaces and corresponding sub-namespaces are governed by the respective Allocating Agents.
  - IGSN namespaces and IGSN names must conform to the [IGSN syntax guidelines](../syntax).

In the past, the recommended format for IGSN was nine character string, composed of a three-character namespace followed by six alphanumerical characters. In the future we will have longer namespaces and fewer digits for unique identification, because most single investigators do not need all the unique numbers afforded by the 6 digits (see above for number of samples allowed by 3, 4, 5, 6 alphanumeric digits). A proposal for the workflow of the new naming convention is below.

Each allocating agent will have a two digit supernamespace code, e.g. IE for IEDA, and will have complete authority to assign any subnamespace within it. The user may chose a personal namespace that will come after the allocating agent code. e.g. HS becomes IEHS or HSU becomes IEHSU. The allocating agent is responsible for making sure it assigns unique namespaces within its domain, e.g. IE, and can assign any subnamespace under IE immediately. IGSN e.V. does not enforce a set length for the total namespace, though it is suggested that the total namespace (including 2 digit code) is 4-6 digits in length.

If the user wants a namespace that is not a subnamespace of the allocating agent, then the user  can request the namespace from the higher IGSN registry (though the AA), but the name will not be granted right away. The IGSN manager will be notified - if it is simple case, the manager can grant it. If not this request is not a simple case, the decision goes to the executive board, or to the general assembly, if necessary. 

A module that will complete the task of namespace assignment (described above) is planned for development, pending resources.

# IGSN hierarchical namespace governance model #


## Explanation ##


A governance model on the level of IGSN must meet three conditions:

  - Flexibility to accommodate the needs of diverse scientific communities
  - Assure uniqueness of assigned IGSN names
  - Minimal human and technical communication overhead

These requirements are best met by hierarchical namespace governance (see Bechtold, S. (2003), Governance in Namespaces, *Loy. L.A. L. Rev.*, **36(3)**, 1239–1320, <http://dx.doi.org/10.2139/ssrn.413681>)

### Flexibility ###


An example of a hierachical namespace governance model is the model now used by the Handle system itself. In the Handle system, DataCite <http://www.datacite.org> administers a number of sub-namespaces of CrossRef (10.) <http://www.crossref.org/>, which in turn is a namespace of <http://www.handle.net>. IGSN has been assigned to the namespace 10273 of the Handle namespace. CNRI, the operator of handle.net, has delegated the governance of the namespace 10273 to IGSN e.V.


### Uniqueness and Namespace Exhaustion ###


In the context of IGSN namespaces it is required to support both the 9-character syntax of SESAR and alternative naming conventions used by the major core repositories. At the current state of the discussion the standard prefix for a collection is a string of three characters. This rule allows for potentially 17576 (26^3) namespaces. Including numbers would allow 36^3 = 46,656 possible namespaces. NSF GEO reports approximately 15,000 individual researchers that have submitted grant proposals to NSF in the geosciences. This number clearly shows that by allocating three character namespaces to individual researchers would quickly exhaust the namespaces available.

Using the SESAR format of 3+6 characters as an example, the concatenated sample name is a string of six characters (a-z, 0-9, excluding i and o), which allows 1.55 x 10^9 samples per namespace, which should be sufficient for most purposes.

To ensure unique names for long term operation of the system and to accommodate the requests from the core repositories a few points should be considered:

  - Many collections are much smaller than 1,500 million samples. In most cases four characters would be sufficient, even if the name suffixes are only numbers.
  - Using longer collection prefixes as sub-namespaces would multiply the number of collection namespaces by orders of magnitude while still providing a sufficient number of names for small collections of about 10,000 samples.

The hierarchical namespace governance model is similar in structure to the IP address space (IPv4) or the system of motor vehicle licencing in Australia <https://en.wikipedia.org/wiki/Vehicle_registration_plates_of_Australia>.

### Communication Overhead ###

In a hierarchical namespace governance model the Allocating Agent does not need to negotiate the allocation of sub-namespaces with IGSN e.V. but may solely negotiate with its clients. This is analogous to the current practice in assigning DOI names, or handle names. By delegating parts of the namespace governance to Allocating Agents the communication overhead between Allocating Agents and IGSN e.V. will be minimised.

### Mnemonic Names - How much meaning should be in an IGSN? ###

Principal investigators applying to an Allocating Agent for a namespace might prefer mnemonic names. However, it is foreseeable that many mnemonic namespaces will soon be allocated. When this point is reached only non-mnemonic namespaces can be allocated. This situation is similar to "vanity plates" in car licence plates. For example, in Berlin all car licences in the namespace B-MW nnnn have already been allocated, this particular namespace has been exhausted. An Allocating Agent should take care to reserve "valuable" namespaces for their major clients (e.g. ODP, IODP, ICDP, government geological surveys, ...).

### Legacy Namespaces ###

The current number of namespaces already assigned by SESAR is small enough to leave already assigned namespaces (legacy namespaces) in place.

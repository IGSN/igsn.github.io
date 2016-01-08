---
layout: page
title: Glossary
---

## Allocating Agent ##

An [Allocating Agent](../agents) (see also the definition of an Allocating Agent given in the [statutes](../statutes)) is an institution which allocates IGSN names on behalf of the IGSN registration agency of IGSN. An Allocating Agent may delegate technical functions and services to one or more sample repositories or data centres.

Allocating Agents:

  * System for Earth Sample Registration (SESAR) <http://www.geosamples.org>
  * CSRIO Mineral Resources <http://www.csiro.au/en/Research/MRF>
  * MARUM Centre for Marine Environmental Sciences, Univ. Bremen <http://www.marum.de>
  * German Research Centre for Geosciences GFZ, Potsdam <http://www.gfz-potsdam.de/en/section/centre-for-scientific-drilling/>
  * Geoscience Australia
  * Curtin University, De Laeter Centre for Geoschemistry
  
  
## Community ##

An IGSN [Community](../communities) is a scientific community of practice, e.g. petrology, ocean sediments, critical zone, etc. The catalogue of samples registered by a community is made accessible through a community portal. The community also defines the IGSN [Naming Convention](../syntax) and [descriptive metadata](../metadata) for its samples.

Community Portals:

   * System for Earth Science Sample Registration (SESAR) <http://www.geosamples.org>

## IGSN Syntax #

An International GeoSample Number (IGSN), is a unique string created to identify a sample object in an online environment. The [syntax guidelines](../syntax) are summarised on the IGSN wiki pages.

The IGSN is organised by [namespaces](../namespaces) to ensure globally unique allocation of IGSNs to samples. Please refer to the [syntax guidelines](../syntax) for more detail.



## Metadata Profile and Schema ##

Due to the diversity of samples that IGSN tries to accommodate, including historic samples with a very limited set of available metadata. IGSN metadata come in two sets: registration metadata and descriptive metadata. Regsitation metadata are used only to transmit the core metadata elements needed for the registration, resolution, and administration of the IGSN resolver service. Metadata for sample catalogues use descriptive metadata. IGSN e.V. have defined a core descriptive metadata set, but in community databases may define more specific metadata profiles used by the respective scientific communities.

The registration metadata schema can be downloaded from our code repository: (Trac) <http://trac.gfz-potsdam.de/igsn/browser/IGSN/schema> or (SVN) <http://svnext.gfz-potsdam.de/igsn/>. The documentation of the metadata and schema has moved to the IGSN Trac Wiki <http://trac.gfz-potsdam.de/igsn/wiki/WikiStart> 

An IGSN [Community](../communities) can define a more detailed metadata application profile.

## Namespaces ##

In order to ensure the uniqueness of assigned IGSN names, the space of IGSN identifiers is subdivided into namespaces. [Namespaces](../namespaces) are assigned to [Allocating Agents](../agents) by the IGSN Registration Agency. The allocation of IGSNs within a namespace is governed by the allocation agents.


## Registration Agency ##

IGSN names and [registration metadata](../metadata) are sent to the Registration Agency by the [Allocating Agents](../agents). The Registration Agency keeps a record of all registered IGSN names and integrates the IGSN names into the [handle_system](https://en.wikipedia.org/wiki/Handle_System) for global resolution into URLs. Detailed descriptions of the data are kept by the Allocating agents and can be harvested into community portals for sample discovery and re-use.

Individual users should refer to [Allocating Agents](../agents) for registration of their samples.

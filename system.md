---
layout: page
title: System Architecture
---

The resolution of IGSN names to URL is based on the [Handle_System](https://en.wikipedia.org/wiki/Handle_System) where IGSN operates in the handle-namespace <10273>. IGSN names of samples are registered as key-value pairs together with descriptive and administrative metadata by an IGSN client with an Allocating Agent. The Allocating Agent in turn registers the IGSN at the IGSN Registration Service operated by IGSN e.V.

![IGSN simplified system architecture](../media/igsn_simple_architecture.png)

*Simplified system architecture of the IGSN registration.*

The following pages provide more information on the components of the IGSN system architecture:

[Namespaces](../namespaces) - Namespace governance and how to apply for a namespace

[IGSN Syntax](../syntax) - Rules for creating and registering IGSN names

[Registration Service](../registration) - Documentation of the IGSN Registration Service. This Documentation is intended for Allocation Agents only. Users wishing to register IGSNs should contact one of the Allocating Agents. For more information contact [info@igsn.org](mailto:info@igsn.org).

[Registration Metadata](../metadata) - Overview of the metadata required for IGSN registration by the IGSN Registration Service. This Documentation is intended for Allocation Agents only. Users wishing to register IGSNs should contact one of the Allocating Agents. For more information contact info@igsn.org.

[Descriptive Metadata](../metadata) - The IGSN Registration Service does not store descriptive metadata. These are only stored by Allocating Agents and provided for harvesting into community-specific metadata portals.

[Metadata Harvesting](http://doidb.wdc-terra.org/igsnoaip/) - The contents of the IGSN Metadata Store can be harvested by the OAI-PMH protocol.


# Development #

## IGSN API Documentation ##

The IGSN registration service provides a REST API for the registration of IGSN and associated metadata. The API documentation can be found here: <https://doidb.wdc-terra.org/igsn/static/apidoc>

## IGSN OAI-PMH API Documentation ##

IGSN catalogues are disseminated through web services using the Open Archival Initiative Protocol for Metadata Harvesting [(OAI-PMH)](http://www.openarchives.org/pmh/). Catalogues are offered for harvesting in the IGSN Core Metadata schema and in the OAI-PMH default [Dublin Core](http://www.openarchives.org/OAI/2.0/openarchivesprotocol.htm#dublincore). The documentation for IGSN OAI-PMH services can be found here: [IGSN Catalogues](../oai)


## Source Code ##


The source code of the IGSN Metadata Store can be found here: <https://github.com/IGSN/mds>

The source code of the OAI-PMH provider for the syndication of metadata from the MDS to portals and catalogues can be found here: <https://github.com/IGSN/oaip>

The source code for the search component of the MDS can be found here: <https://github.com/IGSN/search>


## Events ##


First IGSN-DataCite-ORCID [Code Sprint 2013](../2013/07/01/IGSN-code-sprint) (Potsdam, 2013-07-01 to 2013-07-02)

IGSN [Metadata Kernel Workshop](../2015/09/15/IGSN-Metadata-Kernel-Working-Meeting) (Los Angeles, 2015-09-15 to 2015-09-16)


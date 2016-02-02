---
layout: page
title: Creating IGSN Catalogues
---
There are many things you would like to know about a sample (i.e. metadata) and there is no "one size fits all" solution to this question. The metadata elements that matter will depend very much on the [community of practice](../communities) that wants to share metadata and sample catalogues. This is why IGSN uses the Open Archival Initiative Protocol for Metadata Harvesting [(OAI-PMH)](https://en.wikipedia.org/wiki/Protocol_for_Metadata_Harvesting) for sharing sample catalogues. IGSN makes use of the fact that OAI-PMH does not prescribe a particular format for the metadata but allows the parallel use of different metadata formats for different purposes.

Each [Allocating Agent](../agents) is required to offer their sample catalogue for harvesting. The metadata come in two prescribed formats: the [IGSN Core Metadata](../metadata) schema and formated in [Dublin Core](http://www.openarchives.org/OAI/2.0/openarchivesprotocol.htm#dublincore), which is the OAI-PMH default metadata format.

This service exposes metadata stored in the IGSN Registry using the Open Archives Initiative Protocol for Metadata Harvesting (OAI-PMH).

# Who can use this service? #

This service is open to everyone and is meant to be accessed by OAI-PMH compliant harvesters or any application that issues OAI-PMH requests. The service base address for the IGSN Registry is <http://doidb.wdc-terra.org/igsnoaip/oai> and the service identifier is available here.

All Allocating Agents are required to provide their sample catalogues through OAI-PMH. The base URLs of these services are:

*   CSIRO
*   Curtin University
*   Geoscience Australia
*   GFZ Potsdam
*   IEDA
*   MARUM

# What is OAI-PMH? #

In brief, OAI-PMH provides a set of services that enables exposure and harvesting of repository metadata. The protocol is comprised of six verbs that specify the service being invoked, they are:

*  Identify - used to retrieve information about the repository.
*  ListIdentifiers - used to retrieve record headers from the repository.
*  ListRecords - used to harvest full records from the repository.
*  ListSets - used to retrieve the set structure of the repository.
*  ListMetadataFormats - lists available metadata formats that the repository can disseminate.
*  GetRecord - used to retrieve an individual record from the repository.

Selective harvesting can be performed by the use of accompanying parameters. Available parameters are:

*  identifier - specifies a specific record identifier.
*  metadataPrefix - specifies the metadata format that the records will be returned in.
*  set - specifies the set that returned records must belong to.
*  from - specifies that records returned must have been created/update/deleted on or after this date.
*  until - specifies that records returned must have been created/update/deleted on or before this date.
*  resumptionToken - a token previously provided by the server to resume a request where it last left off.

The verbs and parameters can be combined to issue requests to the service such as:

*  <http://doidb.wdc-terra.org/igsnoaip/oai?verb=Identify> for a repository identification
*  <http://doidb.wdc-terra.org/igsnoaip/oai?verb=ListIdentifiers&metadataPrefix=oai_dc> to list all registered datasets
*  <http://doidb.wdc-terra.org/igsnoaip/oai?verb=ListRecords&from=2015-01-01T00:00:00Z&metadataPrefix=oai_dc> to list new/updated records since 01 January 2015

For more details on the protocol, its implementation, and uses please visit the [OAI-PMH web site](http://www.openarchives.org/pmh/).

# Available Metadata Formats #

All IGSN Allocating Agents are required to disseminate records in the following formats:

*  IGSN descriptive metadata kernel <https://github.com/IGSN/metadata/wiki/IGSN-Descriptive-Metadata-Version-1.0>
*  Dublin Core (dc)

In addition, [communites of practice](../communities) may define their own, more use case specific, metadata schemas.

## IGSN -> Dublin Core Cross-walk ##

To offer a minimum functionality for OAI-PMH services, metadata must be made available in the OAI Dublin Core format. The Mapping of IGSN Descriptive Metadata elements to Dublin Core elements should be used to serve Dublin Core metadata through the OAI-PMH service for harvesting by generic clients, e.g. [Geonetwork Open Source](http://www.geonetwork-opensource.org/).

dc:element | IGSN Descriptive Element | Notes
---------- | ------------------------ | -----
dc:contributor |  N/A | not used
dc:coverage | samplingLocation |
dc:creator | sampleCollector |
dc:date | samplingTime |
dc:description | comments |
dc:format | materialType |
dc:identifier | IGSN | In URI format
dc:language | N/A | not used
dc:publisher | sampleCurator |
dc:relation | relatedResources | (KIV) - this will be added when the relations between samples are finalized in the CSIRO schema.
dc:rights | N/A | not used
dc:source | N/A | not used
dc:subject | classification |
dc:title | sampleName |
dc:type | sampleType |
---
layout: page
title: Metadata
---

# IGSN Handle Registration Metadata #

Due to the diversity of samples that IGSN tries to accommodate, including historic samples with a very limited set of available metadata. The IGSN metadata scheme is not a standard metadata scheme for sample description, it is used only to transmit core metadata needed for the registration, resolution, and administration of the IGSN resolver service. Metadata schemes in community databases are defined by the respective scientific [communities](../communities).


The URL of the landing page of the collection item (resourceURI) is not part of the IGSN metadata kernel, but is transmitted to the IGSN web service as part of the registration process and stored in the handle system. In this way, mismatches between URI stored in the metadata and URI stored in the handle system can be avoided.


The XML schema can be downloaded from our code repository: (Trac) <http://trac.gfz-potsdam.de/igsn/browser/IGSN/schema> or (SVN) <http://svnext.gfz-potsdam.de/igsn/>.

The documentation of the metadata and schema has moved to the IGSN Trac Wiki <http://trac.gfz-potsdam.de/igsn/wiki/WikiStart

The URL of the landing page of the collection item (resourceURI) is not part of the IGSN metadata kernel, but is transmitted to the IGSN web service as part of the registration process and stored in the handle system. In this way, mismatches between URI stored in the metadata and URI stored in the handle system can be avoided.

The XML schema can be downloaded from our code repository: (Trac) http://trac.gfz-potsdam.de/igsn/browser/IGSN/schema or (SVN) http://svnext.gfz-potsdam.de/igsn/.

Change requests can be submitted as a new ticket: [http://trac.gfz-potsdam.de/igsn/newticket].

# IGSN Registration Metadata Elements #


Version 1.0 of 2012-07-11


Element  | Definition
-------- | ----------
sampleNumber  | The IGSN that identifies the registered object.
registrant  | The allocating agent registering the object.
relatedResourceIdentifier  | The identifiers of other objects (literature, data, samples) related to this object. **This element will become obsolete with the introduction of the IGSN Descriptive Metadata Schema.**
log  | Date and Time relevant to events concerning the registered object and its metadata.


## IGSN Metadata Properties ##

NB: controlled lists of attribute values need to be finalised.


ID  | Element  | A/C  | Occ  | Definition  | Description and instructions
--- | -------- | ---- | ---- | ----------- | ----------------------------
1  | sampleNumber  |  | 1  | The Identifier is a unique string that identifies a resource. At present, the only allowed value is an IGSN handle.  | IGSN (International GeoSample Number) registered by an IGSN member. Format should be: "10273/foo"
1.1  | identifierType  | A  | 1  | The identifier type.  | At present the only allowed value is igsn.
2  | registrant  |   |  1  | allocating agent    |
2.1  | registrantName  | C  |  1  | The name of the allocating agent.  | 
2.2  | nameIdentifier  |  C  |  0-n  | Identifier of the allocating agent.  | Uniquely identifies the allocating agent according to various schemes
2.2.1  | nameIdentifierScheme  |  A  |  1  | The name or URL of the name identifier scheme.  | Examples: ORCID, ISNI, VIAF, others (see table 2.2.1).
3  | relatedResourceIdentifier  |   | 0-n  | Identifiers of related resources.  |
3.1  | relatedIdentifierType  |  A  |  1  | The type of related identifier.  |  controlled list: DOI, Handle, IGSN, LSID, URL, URN (see table 3.1)
3.2  | relationType  |  A  |  1  | Description of the relationship of the resource being registered (A) and the related resource (B).  |  see table 3.2.
4  | log  |   |  1-n  |  Log of events relevant to the object.  |
4.1  | logElement  |  C  | 1-n  |  Event relevant to the object. |
4.1.1  | event  |  A  |  1-n  |  Controlled list: |  see table 4.1.1.
4.1.2  | timeStamp  |  A  |  1-n  |    |  YYYY or YYYY‐MM‐DD or any other format described in [W3CDTF](http://www.w3.org/TR/NOTE-datetime).
4.1.3  | comment  |  A  |  0-n  |   | Optional free-text comment on the log entry.


A = Attribute, C = Child


## IGSN Element Attribute Values ##

### 1.1 identifierType ###

Attribute value | Definition
--------------- | ----------
igsn  | [see suntax guidelines](../syntax)

At present, the only allowed value is an IGSN handle.


### 2.2.1 nameIdentifierScheme ###

Attribute value  |  Definition
--------------- | ----------
orcid  | <http://en.wikipedia.org/wiki/ORCID>
isni   | <http://en.wikipedia.org/wiki/ISNI>
researcherID  | <http://en.wikipedia.org/wiki/ResearcherID>
viaf | <http://en.wikipedia.org/wiki/Virtual_International_Authority_File]]>

### 3.1 relatedIdentifierType ###

Attribute value |  Definition
--------------- | ----------
doi  | <http://en.wikipedia.org/wiki/Digital_object_identifier>
handle  | <http://en.wikipedia.org/wiki/Handle_System>
igsn  | [see syntax guidelines](../syntax)
lsid  | <http://en.wikipedia.org/wiki/Lsid>
url  | <http://en.wikipedia.org/wiki/Url>
urn  | <http://en.wikipedia.org/wiki/Uniform_Resource_Name>


### 3.2 relationType ###

This element will become deprecated with the introduction of the IGSN Descriptive Metadata Schema.

Description of the relationship of the resource being registered (A) and the related resource (B).

Attribute value |  Definition
--------------- | ----------
isCitedBy  | Indicates that B includes A in a citation
isPartOf  | Indicates this object A is a portion of another object B. (e.g. B is a sub-sample of A)
hasPart  | Indicates this object A includes the object part B. (e.g. sample A has sub-sample B)
isReferencedBy  | Indicates object B is used as a source of information for this object A.
references  | Indicates object A uses object B as a source of information.
isDocumentedBy  | Indicates object B is documentation about/explaining this object A.
documents  | Indicates this object A is documentation about/explaining object B.
isCompiledBy  | Indicates object B is used to compile or create this object A. (e.g. A is compiled by collection B)
compiles  | Indicates object B is the result of a compile or creation event using this object A. (e.g. collection A includes B)
isVariantFormOf  | Indicates this object A is a variant or different form of object B, e.g. processed form or different packaging.
isOriginalFormOf | Indicates this object A is the original form of object B.



### 4.1.1 event ###


Attribute value |  Definition | ISO 19135 equivalent
--------------- | ----------- | --------------------
submitted  | Date of the initial registration.  | notValid
registered  | The object is registered.  | valid
updated  | Date of the last metadata update.  | superseded
deprecated  | The entry is no longer relevant, e.g. due to duplicate registration.  | retired
destroyed  | The object is destroyed and no longer exists.  | (no equivalent)


# IGSN Core Descriptive Metadata #

To facilitate the discovery of samples through centralised catalogues, IGSN e.V., together with the NSF funded iSamples initiative, hosted a workshop in Los Angeles, California, on 14/15 September 2015 to draft a metadata kernel for descripitve and discovery metadata. The IGSN kernel metadata schema can be found at <http://schema.igsn.org>

# IGSN -> Dublin Core Cross-walk #

The Mapping of IGSN Descriptive Metadata elements to Dublin Core elements should be used to serve Dublin Core metadata through the OAI-PMH service for harvesting by generic clients, e.g. [Geonetwork Open Source](http://www.geonetwork-opensource.org/).

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


---
layout: page
title: Metadata
---

Due to the diversity of samples that IGSN tries to accommodate, including historic samples with a very limited set of available metadata. The IGSN registration metadata scheme is not a standard metadata scheme for sample description, it is used only to transmit core metadata needed for the registration, resolution, and administration of the IGSN resolver service. Metadata schemes in community databases are defined by the respective scientific [communities](../communities).

Change requests can be submitted to our issue tracker: <https://github.com/IGSN/metadata/issues>.

# IGSN Descriptive Metadata #

To facilitate the discovery of samples through centralised catalogues, IGSN e.V., together with the NSF funded iSamples initiative, hosted a workshop in Los Angeles, California, on 14/15 September 2015 to draft a metadata kernel for descriptive and discovery metadata. The idea behind this IGSN descriptive metadata kernel is to provide a minimum set of elements to describe a geological sample. The schema only contains elements that do not change over time, in analogy to being a "birth certificate" of a sample. Allocating Agents will provide richer and more specific metadata in schemas defined by [communities of practice](../communities)


*   IGSN description metadata Schema for production: <http://schema.igsn.org/description>

*   IGSN description metadata schema on GitHub: <https://github.com/IGSN/metadata/tree/master/description>

*   Documentation on GitHub: <https://github.com/IGSN/metadata/wiki/IGSN-Descriptive-Metadata-Version-1.0>


# IGSN Handle Registration Metadata #

The IGSN registration metadata scheme is used only to transmit core metadata needed for the registration, resolution, and administration of the IGSN resolver service. The URL of the landing page of the collection item (resourceURI) is not part of the IGSN metadata kernel, but is transmitted to the IGSN web service as part of the registration process and stored in the handle system. This separation helps us to avoid mismatches between URI stored in the metadata and URI stored in the handle system.

*   IGSN registration metadata Schema for production: <http://schema.igsn.org/registration>

*   IGSN registration metadata schema on GitHub: <https://github.com/IGSN/metadata/tree/master/registration>.

*   Documentation on GitHub <https://github.com/IGSN/metadata/wiki/IGSN-Registration-Metadata-Version-1.0>




# IGSN -> Dublin Core Cross-walk #

The Mapping of IGSN Descriptive Metadata elements to Dublin Core elements should be used to serve Dublin Core metadata through the Allocating Agents' [OAI-PMH](../oai) services for harvesting by generic clients, e.g. [Geonetwork Open Source](http://www.geonetwork-opensource.org/). More detail can be found in the [documentation of IGSN OAI-PMH services](../oai).

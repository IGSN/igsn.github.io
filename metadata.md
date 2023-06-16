---
layout: page
title: Metadata
---

## The content on this page is no longer current and will be replaced soon. ##

There are many things you would like to know about a sample (i.e. [metadata](../metadata)) and there is no "one size fits all" solution to this question. The metadata elements that matter will depend very much on the [community of practice](../communities) that wants to share metadata and sample catalogues.

To be able to accommodate the great variety of geoscience samples, the IGSN system uses two separate sets of metadata:

*   IGSN descriptive metadata is a metadata kernel to catalogue samples according to collector, material type, location of origin of the sample, etc.

*   IGSN registration metadata is a set of metadata elements relating only to the registration and administration of the IGSN.

# IGSN Descriptive Metadata #

To facilitate the discovery of samples through centralised catalogues, IGSN e.V., together with the NSF funded iSamples initiative, hosted a [workshop in Los Angeles](../2015/09/15/IGSN-Metadata-Kernel-Working-Meeting), California, on 15/16 September 2015 to draft a metadata kernel for descriptive and discovery metadata. The idea behind this IGSN descriptive metadata kernel is to provide a minimum set of elements to describe a geological sample. The schema only contains elements that do not change over time, in analogy to being a "birth certificate" of a sample. Allocating Agents will provide richer and more specific metadata in schemas defined by [communities of practice](../communities)


*   IGSN descriptive metadata Schema for production: <http://schema.igsn.org/description>

*   IGSN descriptive metadata schema on GitHub: <https://github.com/IGSN/metadata/tree/master/description>

*   Documentation on GitHub: <https://github.com/IGSN/metadata/wiki/IGSN-Descriptive-Metadata-Version-1.0>


# IGSN Handle Registration Metadata #

The IGSN registration metadata scheme is used only to transmit core metadata needed for the registration, resolution, and administration of the IGSN resolver service. The URL of the landing page of the collection item (resourceURI) is not part of the IGSN metadata kernel, but is transmitted to the IGSN web service as part of the registration process and stored in the handle system. This separation helps us to avoid mismatches between URI stored in the metadata and URI stored in the handle system.

*   IGSN registration metadata Schema for production: <http://schema.igsn.org/registration>

*   IGSN registration metadata schema on GitHub: <https://github.com/IGSN/metadata/tree/master/registration>.

*   Documentation on GitHub <https://github.com/IGSN/metadata/wiki/IGSN-Registration-Metadata-Version-1.0>




# IGSN -> Dublin Core Cross-walk #

All OAI-PMH harvesters know how to process Dublin Core metadata. The Mapping of IGSN Descriptive Metadata elements to Dublin Core elements provides a cross-walk to serve Dublin Core metadata for harvesting if IGSN catalogues by generic clients, e.g. [Geonetwork Open Source](http://www.geonetwork-opensource.org/). More detail can be found in the [documentation of IGSN OAI-PMH services](../oai).

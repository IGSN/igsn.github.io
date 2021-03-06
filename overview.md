---
layout: page
title: Overview
---

The IGSN is a persistent unique identifier for physical samples and specimens that eliminates the problems associated with the ambiguous naming of samples. The IGSN registration service helps discover, access, and share samples, ensure preservation of and access to sample data, aid identification of samples in the literature, and advance the exchange of digital sample data among interoperable data systems, thus maximizing the utility of samples for research, education, and society. 

Get a quick introduction to how IGSN works and follow the links for more information.

## How to create and register an IGSN ##

IGSN is designed to "work offline". This means, the standard workflow is to define an IGSN and register it through an [Allocating Agent](../agents)

As an individual researcher, your IGSNs for samples will be registered on your behalf by an [Allocating Agent](../agents). Your [Allocating Agent](../agents) will advise you on [how to create an IGSN](../syntax) and how to register it.
  
## IGSN Syntax and metadata ##

The members of IGSN e.V. have put together a set of [guidelines on the IGSN syntax](../syntax) and how to use IGSN. Your [Allocating Agent](../agents) will advise you on how IGSNs are used in the respective Allocating Agent's system. 

IGSN [communities of practice](../communities) can design descriptive [metadata](../metadata) to suit their use cases. 

## How to resolve an IGSN ##

An IGSN can be resolved through the internet by using a Handle.net or DOI resolver.

     Example (IGSN):        BGRB5054RX05201
	
The address of the IGSN resolver is http://hdl.handle.net/10273

By using the URL <http://hdl.handle.net/10273/BGRB5054RX05201>, you will be automatically redirected to the web page describing this sample.

## How to use IGSN in the literature ##

To tag an IGSN, please use the syntax

    IGSN: <IGSN> 

In a journal article or manuscript a sample identified by IGSN SSH000SUA may look like this (tagged IGSN):

[IGSN: SSH000SUA](http://hdl.handle.net/10273/SSH000SUA)

Tagging IGSNs in manuscripts in this way allows publishers to automatically link samples identified by IGSN to their respective descriptive pages on the web. See also <http://www.geosamples.org/news/tag> for more information about journals using IGSN.

## Set up a service for IGSN registration ##

To be able to register IGSN, you have to [become a member](../membership) of the IGSN Implementation Organization IGSN e.V. This [role](../organisation) in IGSN is called an "[Allocating Agent](../agents)".

As an Allocating Agent you will be authorised to register IGSN in the [namespace](../namespaces) assigned to you. [Check](../namespaces) which namespaces have been assigned already and [apply for your namespace](../namespaces).

You may build your own software or reuse [open source components](../system) developed for IGSN e.V.

## Create Catalogues and Community Portals ##

There are many things you would like to know about a sample (i.e. [metadata](../metadata)) and there is no "one size fits all" solution to this question. The metadata elements that matter will depend very much on the [community of practice](../communities) that wants to share metadata and sample catalogues. This is why IGSN uses the Open Archival Initiative Protocol for Metadata Harvesting [(OAI-PMH)](https://en.wikipedia.org/wiki/Protocol_for_Metadata_Harvesting) for sharing sample catalogues. These catalogues can be harvested and compiled into new catalogues and [community portals](../communities).

Find out more in the documentation of [IGSN OAI-PMH services](../oai)

## Governance of the IGSN ##

The INGS services are operated by the International Geo Sample Number Implementation Organization (IGSN e.V.). The IGSN e.V. is an international non-profit organization that aims to implement and promote standard methods for locating, identifying, and citing physical samples collected from our natural environment, by operating an international registration service for the International Geo Sample Number (IGSN) with a distributed, sustainable infrastructure for use by and benefit to its members.

Membership in the IGSN e.V. is open to all organizations that wish to allocate IGSNs and use the Registration Agency of the IGSN e.V. in their capacity as Allocating Agents. Affiliate Membership with an advisory function is offered to organizations, who do not wish to use the IGSN eV Registration Agency as an allocating agent, but who have an interest in promoting and supporting the purposes of the IGSN e.V.

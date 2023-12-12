---
layout: page
title: Syntax Guidelines
---

The following is a summary of the syntax guidelines for the IGSN ID:

  - **The IGSN ID must be unique and is case insensitive**.
  - In consideration of human readability the **IGSN should be as concise as possible**. IGSN IDs will be displayed on-line and in print and will be re-typed by human users.
  - Organisations assigning IGSN IDs may choose to adopt a consistent, logical system that can be easily documented and readily understood by employees of your organization. This helps to ensure the uniqueness of assigned IGSN IDs and makes it easier for the task of assigning IGSNs to be passed from one employee to the next. You might therefore **consider including existing internal identifiers** already in use within your organization.
  - Suffix nodes may be used to reflect hierarchical information or levels of granularity.  **However, in trying to keep IGSN IDs as short as possible, careful consideration should be taken before adopting a naming scheme that makes use of extending already existing IGSN IDs**.
  - **In general, an IGSN ID should not be considered "derivable"**. For example, sample repository structures may change over time. Repository information encoded in the IGSN ID may become obsolete and possibly meaningless. 

Please refer to the [DataCite Guidelines for IGSN IDs](https://support.datacite.org/docs/igsn-id-registration-guide) for further detail on the technical implementation.

# Recommended Practice #

Unlike many other persistent identifiers, an IGSN ID is used not only used by machines but also needs to be handled by humans. The labelling of sample containers prescribes a limit to the number of characters that fit on a label. Also, IGSN IDs in lists and tables will often need editing by humans. Long character strings increase the risk of mistypings. To reduce the risk of mistypings, the IGSN ID is case insensitive and we recommend to avoid characters that can easily be confused, such as ‘1’ and ‘I’, or  ‘0’ and ‘O’.

Since IGSN IDs are intended to be combined into a URI, in order to retain maximum compatibility with [URI production rules](http://tools.ietf.org/html/rfc3986) it is suggested to limit the characters that can be used in the Code to the so-called 'unreserved' + 'reserved' set, but not allow any other or percent-encoded characters which may exist on the keyboard or other character sets (e.g. no accented characters or non-latin alphabets, no space, CR, LF characters). 

Characters a-z and A-Z in the IGSN ID string are case insensitive (e.g. ABC is identical to AbC). It is recommended to use upper case characters in all cases. If an IGSN ID were registered as ABC, then abc would resolve it and a later attempt to register AbC would be rejected with an error message stating that the IGSN ID already exists.

# Resolving IGSN #

Although some IGSN IDs may be generated according to an algorithm, it is preferable to look them up through a resolver system (see examples below), as there is no guarantee that a generated IGSN ID has been registered with DataCite or that it will resolve.

## Standard IGSN Resolver ##

The standard way to resolve IGSN IDs is through https://doi.org/

    Example (IGSN):        BGRB5054RX05201
	Resulting IGSN URI:    <https://doi.org/10.60510/BGRB5054RX05201>
	
## Legacy IGSN IDs ##

Legacy IGSN IDs registered before 31 December 2022 following the legacy <IGSN prefix>/<igsn> pattern will continue to resolve.

	Example (IGSN):        	BGRB5054RX05201
	Resulting IGSN URI:    <https://igsn.org/10273/BGRB5054RX05201>

# IGSN Examples #

## Example from SESAR ##

A sample from the Susquehanna Shale Hills Critical Zone Observatory, registered through SESAR on behalf of the Department of Geosciences, Pennsylvania State University
	
    Example (IGSN ID):      SSH000SUA

Applying the above rule, the resulting resulting URI is <https://doi.org/10.58052/SSH000SUA>
	
## Example from Geoscience Australia ##

A sample from the collection of Geoscience Australia.

    Example (IGSN ID):        AU1101

Resulting IGSN URI:  <https://doi.org/10.60516/AU1101>

## Example from MARUM ##

Example from the International Scientific Continental Drilling Program (ICDP), registered by MARUM on behalf of ICDP:

    Example (IGSN ID):        MBCR5034RC57001
	
Resulting IGSN URI:  <https://doi.org/10.58095/MBCR5034RC57001>

Example from the core repository of the German Federal Geological Survey (BGR), registered by MARUM on behalf of BGR:

    Example (IGSN ID):        BGRB5054RX05201

Resulting IGSN URI:  <https://doi.org/10.60510/BGRB5054RX05201>
	
The sample [BGRB5054RX05201](https://doi.org/10.60510/BGRB5054RX05201) was derived from [ICDP5054ESYI201](https://doi.org/10.60510/ICDP5054ESYI201).

## Examples from GFZ Potsdam ##

Example from the International Scientific Continental Drilling Program (ICDP), registered by GFZ Potsdam on behalf of ICDP:

	Example (IGSN ID):        ICDP5054ESYI201

Resulting IGSN URI:  <https://doi.org/10.60510/ICDP5054ESYI201>

Example of assigning an IGSN to a drill hole (sampling feature):

    Example (IGSN ID):        ICDP5054EEW1001

Resulting IGSN URI:  <https://doi.org/10.60510/ICDP5054EEW1001>

## Example from CSIRO ##

Example from the collection of CSIRO at the Australian Resources Research Centre in Kensington, Western Australia:

    Example (IGSN ID):        CSRWA275
	
Resulting IGSN URI:  <https://doi.org/10.58108/CSRWA275>

The above example is part of a sub-collection with its own IGSN:

    Example (IGSN ID):        CSRWASC00001
	
Resulting IGSN URI:   <https://doi.org/10.58108/CSRWASC00001>
	
	
	
# Using IGSNs in Manuscripts #

The IGSN Organisation, Allocating Agents and academic publishers ask authors to tag IGSN IDs in their manuscripts. This will enable publishers to link the IGSN ID to the respective samples sample when the paper is published online. To tag an IGSN ID, please use the syntax

    IGSN:<IGSN ID> 

In a journal article or manuscript a sample identified by IGSN ID SSH000SUA may look like this (tagged IGSN):

[IGSN:SSH000SUA](http://doi.org/10.58052/SSH000SUA)

Tagging IGSNs in manuscripts in this way allows publishers to automatically link samples identified by IGSN to their respective descriptive pages on the web. 

Since May 2017 IGSN IDs can be included in the asset tabs of all Copernicus earth science journals. The use of IGSN IDs is also endorsed by the [Coalition for Publishing Data in the Earth and Space Sciences](http://www.copdess.org/).

An example of a publication using live IGSN IDs can be found here:

  * Dere, A. L., T. S. White, R. H. April, B. Reynolds, T. E. Miller, E. P. Knapp, L. D. McKay, and S. L. Brantley (2013), Climate dependence of feldspar weathering in shale soils along a latitudinal gradient, *Geochimica et Cosmochimica Acta*, **122**, 101–126, <http://dx.doi.org/10.1016/j.gca.2013.08.001>.

  
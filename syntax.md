---
layout: page
title: Syntax Guidelines
---



The following is a summary of the syntax guidelines for the IGSN:

  - **The IGSN must be unique and is case insensitive**.
  - In consideration of human readability the **IGSN should be as concise as possible**. IGSNs will be displayed online and in print and will be re-typed by end users.
  - **In general, an IGSN should not be considered "derivable"**. Although some IGSNs may be generated according to an algorithm, it is preferable to look them up in IGSN, as there is no guarantee that a generated IGSN has been registered with IGSN or that it will resolve.
  - Organisations assigning IGSNs may choose to adopt a consistent, logical system that can be easily documented and readily understood by employees of your organization. This helps to ensure the uniqueness of assigned IGSNs and makes it easier for the task of assigning IGSNs to be passed from one employee to the next. You might therefore **consider to include existing internal identifiers** already in use within your organization.
  - Suffix nodes may be used to reflect hierarchical information or levels of granularity. For instance, the first node might be a multiple-letter code for a drill core, while successive nodes encode sub-samples taken from the drill core. IGSN suffixes may be extensible, and the suffix nodes may be used for this purpose. For instance, in the future, further sub-samples taken from already subsampled materials might be assigned IGSNs. **In trying to keep IGSNs as short as possible, careful consideration should be taken before adopting a naming scheme that makes use of extending already existing IGSN names**.


# Recommended Practice #

Unlike many other persistent identifiers, an IGSN is used not only used by machines but also needs to be handled by humans. The labeling of sample containers prescribes a limit to the number of characters that fit on a label. Also, IGSNs in lists and tables will often need editing by humans. Long character strings increase the risk of mistypings. To reduce the risk of mistypings, the IGSN is case insensitive and we recommend to avoid characters that can easily be confused, such as ‘1’ and ‘I’, or  ‘0’ and ‘O’.

Since IGSNs are intended to be combined into a URI, in order to retain maximum compatibility with [URI production rules](http://tools.ietf.org/html/rfc3986) it is suggested to limit the characters that can be used in the Code to the so-called 'unreserved' + 'reserved' set, but not allow any other or percent-encoded characters which may exist on the keyboard or other character sets (e.g. no accented characters or non-latin alphabets, no space, CR, LF characters). Using [ABNF notation](http://tools.ietf.org/html/rfc5234) the syntax proposed syntax for an IGSN is: 

    <IGSN>               = <Namespace><Code>
    <Namespace>          = UPPER                        ; namespace adminstrated by the allocating agent
    <Code>               = CHAR                         ; 
    UPPER                = %x41-5A                       (A-Z)
    DIGIT                = %x30-39                       (0-9)
    CHAR = UPPER and DIGIT
    unreserved           = UPPER / DIGIT / "-" / "." 
    reserved             = ":" / "/" / "?" / "#" / "[" / "]" / "@" / "!" / "$" / "&" / "'" / "(" / ")" / "*" / "+" / "," / ";" / "=" / "_" / "~"


The [Allocating Agent](../agents) ensures that the element \<Code\> is unique within their [namespaces](../namespaces).

Characters a-z and A-Z in the IGSN string are case insensitive (e.g. ABC is identical to AbC). It is recommended to use upper case characters in all cases. If an IGSN were registered as ABC, then abc would resolve it and a later attempt to register AbC would be rejected with an error message stating that the IGSN was already in existence. Comparison of two IGSNs (to decide if they match or not) should be done by first converting all characters 'a' - 'z' in IGSN strings to upper case, followed by octet-by-octet comparison of the entire IGSN string.

Characters that may be confused with digits should be avoided (I = %x49, O = %x4F, i = %x69, o = %x6F)

# Examples #

The resolvable handle URI of an IGSN is made up of three components: a resolving service (<http://dx.doi.org> or <http://hdl.handle.net>), the IGSN Handle prefix 10273, and the IGSN, separated by a forward slash. It is concatenated by the following rule:

    <resolver>/<prefix>/<igsn>
	
where \<resolver\>/\<prefix\> is <http://hdl.handle.net/10273> and  \<igsn\> is the value (IGSN) assigned by an [Allocating Agent](../agents). As an Example, we take a sample from the Susquehanna Shale Hills Critical Zone Observatory, registered through SESAR on behalf of the Department of Geosciences, Pennsylvania State University.

## Example from IEDA ##
	
    Example (IGSN):      SSH000SUA

Applying the above rule, the resulting resulting URI is <http://hdl.handle.net/10273/SSH000SUA> (or using the DOI resolving service <http://dx.doi.org/10273/SSH000SUA>)
	
## Example from Geoscience Australia ##

    Example (IGSN):        AU1101

Resulting handle URI:  <http://hdl.handle.net/10273/AU1101>

## Example from MARUM ##

Example from the International Scientific Continental Drilling Program (ICDP), registered by MARUM on behalf of ICDP:

    Example (IGSN):        MBCR5034RC57001
	
Resulting handle URI:  <http://hdl.handle.net/10273/MBCR5034RC57001>

## Examples from GFZ Potsdam ##

Example from the International Scientific Continental Drilling Program (ICDP), registered by GFZ Potsdam on behalf of ICDP:

	Example (IGSN):        ICDP5054ESYI201

Resulting handle URI:  <http://hdl.handle.net/10273/ICDP5054ESYI201>
	
Example from the core repository of the German Federal Geological Survey (BGR), registered by GFZ Potsdam on behalf of BGR:

    Example (IGSN):        BGRB5054RX05201

Resulting handle URI:  <http://hdl.handle.net/10273/BGRB5054RX05201>
	
The sample [BGRB5054RX05201](http://hdl.handle.net/10273/BGRB5054RX05201) was derived from [ICDP5054ESYI201](http://hdl.handle.net/10273/ICDP5054ESYI201).

Example of assigning an IGSN to a drill hole (sampling feature):

    Example (IGSN):        ICDP5054EEW1001

Resulting handle URI:  <http://hdl.handle.net/10273/ICDP5054EEW1001>

## Example from CSIRO ##

Example from the collection of CSIRO at the Australian Resources Research Centre in Kensington, Western Australia:

    Example (IGSN):        CSRWA275
	
Resulting handle URI:  <http://hdl.handle.net/10273/CSRWA275>

The above example is part of a sub-collection with its own IGSN:

    Example (IGSN):        CSRWASC00001
	
Resulting Handle URI:   <http://hdl.handle.net/10273/CSRWASC00001>
	
	
	
# Using IGSNs in Manuscripts #

IGSN e.V., Allocating Agents and academic publishers ask authors to tag IGSNs in their manuscripts. This will enable publishers to link the IGSN number to the respective samples sample when the paper is published online. To tag an IGSN, please use the syntax

    IGSN: <IGSN> 

In a journal article or manuscript a sample identified by IGSN SSH000SUA may look like this (tagged IGSN):

[IGSN: SSH000SUA](http://hdl.handle.net/10273/SSH000SUA)

Tagging IGSNs in manuscripts in this way allows publishers to automatically link samples identified by IGSN to their respective descriptive pages on the web. See also <http://www.geosamples.org/news/tag> for more information about journals using IGSN.

An example of a publication using live IGSNs can be found here:

  * Dere, A. L., T. S. White, R. H. April, B. Reynolds, T. E. Miller, E. P. Knapp, L. D. McKay, and S. L. Brantley (2013), Climate dependence of feldspar weathering in shale soils along a latitudinal gradient, *Geochimica et Cosmochimica Acta*, **122**, 101–126, <http://dx.doi.org/10.1016/j.gca.2013.08.001>.

  
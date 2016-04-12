---
layout: page
title: IGSN Registration API
---

## IGSN Registry API ##

The IGSN registration service is located at <https://doidb.wdc-terra.org/igsn>

## Architecture ##


This API is intended to be used in programs and you will need a valid login. The account data is the same as for the web interface of <https://doidb.wdc-terra.org/igsn>.
Overview

The API is implemented in REST style. The end point you are going to use is:

    https://doidb.wdc-terra.org/igsn/

At the moment there are two resources:

    /igsn

    /metadata

The URI <https://doidb.wdc-terra.org/igsn/igsn> accepts requests with POST HTTP method.

The URI <https://doidb.wdc-terra.org/igsn/igsn/{igsn}>, where {igsn} is a actually IGSN, accepts requests with GET HTTP method.

The URI <https://doidb.wdc-terra.org/igsn/metadata> accepts requests with POST HTTP method.

The URI <https://doidb.wdc-terra.org/igsn/metadata/{igsn}>, where {igsn} is an actual IGSN, accepts requests with 2 HTTP methods: GET and DELETE

In addition HEAD is allowed, whenever GET is.

## Characters ##

An International GeoSample Number (IGSN), is a unique string created to identify a sample object in an online environment.

Using [ABNF notation](http://tools.ietf.org/html/rfc5234) the syntax proposed syntax for an IGSN is:

     <IGSN> = <Namespace><Code>
     <Namespace> = mUPPER (an m character code denoting the namespace)
     <Code> = nCHAR (a n character code) 
     UPPER                        = %x41-5A                       (A-Z)
     DIGIT                        = %x30-39                       (0-9)
     CHAR                         = UPPER / DIGIT / "-" / "." 
     reserved                     = ":" / "/" / "?" / "#" / "[" / "]" / "@" / "!" / "$" / "&" / "'" / "(" / ")" / "*" / "+" / "," / ";" / "=" / "_" / "~"

The [Allocating Agent](../agents) ensures that the n-character code is unique within their [namespaces](../namespaces). See also IGSN [namespace](../namespaces) for more information on namespace governance.

Characters a-z and A-Z in the IGSN string are case insensitive (e.g. ABC is identical to AbC). It is recommended to use upper case characters in all cases.

Characters that may be confused with digits should be avoided (I = %x49, O = %x4F, i = %x69, o = %x6F)

The resolvable handle URI of an IGSN is made up of two components, a handle prefix 10273 and the IGSN as suffix, separated by a forward slash.

See also [IGSN syntax guideline](../syntax)


## Security and Accounts ##


All the traffic goes via HTTPS. All requests to this system are password protected and require HTTP Basic authentication header.

Accounts have some constraints associated:

  *     you will be allowed to mint IGSNs only with prefix assigned to you
  *     you will be allowed to mint IGSNs only with URLs in host domains assigned to you
  *     the number of IGSNs available for registration can be limited.

## Handle System ##



The Handle System - the technical infrastructure for IGSNs - is a worldwide network system, that caches answers to requests. The consequence of this manifests is its inherent latency. For example, IGSNs have TTL (time to live) defaulted to 24 hours, so your changes will be visible to the resolution infrastructure only when the TTL expires. Also, if you create a IGSN and then immediately try to update its URL, you might get the error message HANDLE NOT EXISTS. This is because it takes some time for the system to register a handle for a IGSN.

## Metadata ##


Metadata about your samples must conform to the standards published by IGSN e.V. at Metadata Schema Repository. You will find there an example XML document. Please remember that all your documents must specify correct schema location :warning: <http://doidb.wdc-terra.org/igsn/schemas/igsn.org/schema/0.3/igsn.xsd> in the root element. Also make sure IGSN specified in your document matches IGSN of the dataset.

## Testing ##


Each API call can have optional query parametertestMode. If set to "true" or "1" the request will not change the database nor will the IGSN handle will be registered or updated, e.g. POST igsn/igsn?testMode=true.

Also please note that there is special test prefix 20.500.11812 available to all datacentres. Please use it for all your testing IGSNs. Your real prefix should not be used for test IGSNs. Note that IGSNs with test prefix will behave like any other IGSN, e.g. they can be normally resolved. They will not be exposed by upcoming services like search and OAI, though. Periodically we purge all 20.500.11812 datasets from the system.


## Code examples ##


Download the files delete_metadata.py, get_igsn.py, get_metadata.py, post_igsn.py, post_metadata.py, test.url, test.xml in one directory and call them from the command line

    python post_igsn.py USER PASSWORD test.url
    python get_igsn.py USER PASSWORD IGSN-HANDLE
    python post_metadata.py USER PASSWORD test.xml
    python get_metadata.py USER PASSWORD IGSN-HANDLE
    python delete_metadata.py USER PASSWORD IGSN-HANDLE 

## API reference ##

{{:igsn:system_architecture:igsn-webservice_flow.jpg?1024| Data flow during IGSN registration}}

Data flow diagram of the IGSN registration process


## IGSN API ##

### GET ###


URI: <https://doidb.wdc-terra.org/igsn/igsn/{igsn}> where {igsn} is a specific IGSN.

This request returns an URL associated with a given IGSN.

     Request headers
     none
     Request body
     empty
     Response headers
     none
     Response body

If response status is 200: URL representing a dataset, otherwise short explanation for non-200 status

#### Response statuses ####

    200 OK - operation successful

    204 No Content - IGSN is known to MDS, but is not resolvable (might be due to handle's latency)

    401 Unauthorized - no login

    403 login problem or dataset belongs to another party

    404 Not Found - IGSN does not exist in our database

    410 Gone - the requested dataset was marked inactive (using DELETE method)

    500 Internal Server Error - server internal error, try later and if problem persists please contact us

### POST ##


URI: <https://doidb.wdc-terra.org/igsn/igsn>

POST will mint new IGSN if specified IGSN doesn't exist. This method will attempt to update URL if you specify existing IGSN. Standard domains and quota restrictions check will be performed. A Datacentre's QuotaUsed will be increased by 1. A new record in Datasets will be created.
Request headers

Content-Type:text/plain;charset=UTF-8
Request body

igsn={igsn}
url={url}

where {igsn} and {url} have to be replaced by your IGSN and URL, UFT-8 encoded.
Response body

short explanation of status code e.g. CREATED, HANDLE_ALREADY_EXISTS etc

#### Response statuses ####

    201 Created - operation successful

    400 Bad Request - request body must be exactly two lines: IGSN and URL; wrong domain, wrong prefix

    401 Unauthorized - no login

    403 Forbidden - login problem, quota exceeded

    500 Internal Server Error - server internal error, try later and if problem persists please contact us


## Metadata API ##


### GET ###


URI: <https://doidb.wdc-terra.org/igsn/metadata/{igsn}> where {igsn} is a specific IGSN.

This request returns the most recent version of metadata associated with a given IGSN.
Request headers
Accept:application/xml
Request body
empty
Response headers
Content-Type:application/xml
Response body

If response status is 200: XML representing a dataset, otherwise short explanation for non-200 status

#### Response statuses ####

    200 OK - operation successful

    401 Unauthorized - no login

    403 Forbidden - login problem or dataset belongs to another party

    404 Not Found - IGSN does not exist in our database

    410 Gone - the requested dataset was marked inactive (using DELETE method)

    500 Internal Server Error - server internal error, try later and if problem persists please contact us

### POST ###


URI: <https://doidb.wdc-terra.org/igsn/metadata/{IGSN}>

This request stores new version of metadata. The request body must contain valid XML.
Request headers
Content-Type:application/xml;charset=UTF-8
Request body

UFT-8 encoded metadata
Response body

short explanation of status code e.g. CREATED, HANDLE_ALREADY_EXISTS etc
Response headers

Location - URL of the newly stored metadata
Response statuses

    201 Created - operation successful

    400 Bad Request - invalid XML, wrong domain, wrong prefix

    401 Unauthorized - no login

    403 Forbidden - login problem, quota exceeded

    500 Internal Server Error - server internal error, try later and if problem persists please contact us

### DELETE ###


URI: <https://doidb.wdc-terra.org/igsn/metadata/{igsn}> where {igsn} is a specific IGSN.

This request marks a dataset as 'inactive'. To activate it again, POST new metadata or set the isActive-flag in the user interface.
Response body

if response status 200 - XML representing a dataset, otherwise short explanation for non-200 status
Response statuses

    200 OK - operation successful: dataset deactivated

    401 Unauthorized - no login

    403 Forbidden - login problem or dataset belongs to another party

    404 Not Found - IGSN does not exist in our database

    500 Internal Server Error - server internal error, try later and if problem persists please contact us 
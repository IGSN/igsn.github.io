# MEETING ON IGSN

09:00-13:00 MT Wednesday 14 September 2016 
Crowne Plaza, Denver, Colorado US

## Attendees:
Steve Richard (LDEO), Bob Arko (LDEO), Markus Stocker (MARUM), Wim Hugo (SAEON), Jens Klump (CSIRO), Kerstin Lehnert (LDEO), Lesley Wyborn (ANU), John Kunze (CDL), Peng Ji (LDEO)

## Draft Agenda:
- Conventions for namespace assignment
- EZID as service provider for IGSN
- Link core metadata with extended metadata
- Relationship between allocators and central catalog
- Should IGSN become a member of WDS 

Wim Hugo:
Issues of 'digital samples' (images, video, etc. that are analyzed), can be analyzed for different purposes similar to physical samples
Need to use controlled vocabularies  for sample metadata
Categories of samples
Methodologies for collecting samples
RDA Working Group of Anne Thessen
Use of DataCite schema to describe samples, is it sensible?

How should IGSN integrate with DOI?
DataCite did not accept physical samples until 2 years ago,
Currently requires $8,000 membership fee to be part of DataCite

JKunze: DCIP (Data Citation Principles)
Identifiers.org supports >500 ID schemes in life (?) sciences; e.g. PMID
EZID uses DOI and ARK, also supports URNs
"Persistable IDs" -- if they break at one hostname, just replace the hostname ("id shift")
EZID is biggest customer of DataCite, founding member with over 120 members on 3 continents

JKlump: Distinguish brand of IGSN for sample community versus technical issues of resolving IGSN

Kunze: EZID does cross-walks between different metadata schemas
$2,500/year for unlimited logins; To support a metadata profile have to map to Dublin Core and DataCite.
API would work as soon as the profile was set, but adding UI support would require some one-time development $$ (small grant?)
[ additional info from Kunze: 
  What EZID does right now:
enforcement, normalization of identifier syntax
enforcement of metadata requirements
metadata mapping, conversion, normalization
for uniform views, satisfying requirements
fully integrated identifier minting
storage in N2T binder
registration with external authorities, services
Handle System, DataCite, CrossRef
manages identifier visibility
provides landing pages
provides ownership, management tools
full API, UI
change owners; proxy owners
provides access
OAI-PMH, bulk download, metadata search
statistics
link checking

  What N2T.net (Name-to-Thing) resolver does right now, across schemes:
Opaque id generation
Suffix passthrough
Content Negotiation
Inflections (à la ARK)
Visibility in Data Citation Index (for those that T-R deems interesting)
Redirection rules for externally hosted schemes and namespaces
About 2000 schemes from life sciences alone (PMID, GO, GeneID, etc)
Potential backup for doi.org (Crossref, DataCite, MeDRA)
]

AAs under IGSN enterprise account would have a log-in, get a prefix, and ability to determine the identifier template for that AA
IGSN has level beneath allocating agent; 
Customers want ability to reserve an identifier before going public; EZID implements reservations for this.



N2t.net is designed to be transportable for sustainability, EZID looking for mechanisms for backup, community ownership.  Need consortium ownership, and a business model for sustaining (not voluntary)

But IGSN has copied DataCite to cut down on maintenance

We need to ensure that if one group , the whole system does not fail. 

IGSN needs to clearly think this through. The technical lead committee can work on the direction to go. Bring a suggestion to the General Assembly in December for a decision.

EZID can help provide on bibliometrics - eg connection between IGSN and ORCID

IGSN can register digital samples. 

IGSN has overlap with the Bio and Soil community. IGSN have attended TWDG. 

Can we go to social sciences?

It should mean something to a publisher that a sample has an IGSN

What are the consequences of IGSN joining EZID
Cost estimated $US2500 per year (need formal quote)
With IGSNs the metadata record comes along later.
Can register before we agree on the description.
Communities can agree on different detailed schema for specific portals.
EZID has a metadata searching that is based on the profile
Description Kernel could be kept outside of EZID

Kerstin: need to have capability to validate that an IGSN is registered and has metadata conforming to a given profile

When go public with identifier is when EZID validation happens according to rules of the 
Agent profile.
Have to account for samples that don't have geospatial location; need to know where physical object is curated and if it is available for inspection/subsampling.

We need to have consistency across the AA for specific sample types - each AA should not set its own rules.

Allocation agents are not sample type specific.

No deal breakers identified as yet, but may be issues in the details.

If you stop paying bills, can continue to maintain identifiers indefinitely, just can't register new IDs; can move ownership of a pack of identifiers to another organization.

What do we do with things that are already published as Handles. 

If full url is out there already, need to alert, or update new records to point to handles or visa versa. Need to think this through as we may need to maintain the handle server at $50 pa.


EZID can pass through identifiers with extensions (anchors, query strings...)

SAEON still interested in joining IGSN e.V.

Coffee break.
Reconvene at 11:00 am
Discussion of how to proceed. Interest group with RDA. Try to bring together various groups working on physical sample identifications, develop vocabularies for different kinds of samples. 
Broader than PID, have to deal with issues of access to sample. Issues around preservation of physical objects. 
Interest group identify issues that need to be solved, form working groups to solve specific problems. 

YAMZ--tool  reputation based crowdsourced vocabulary tool.  Various groups  are using. 

Citizen Group

Persistence vocabulary

Natural Hazards group - Maria Esteva

Three Classes of vocabularies:
Canonical
Vernacular
Deprecated

See John's SciDataCon Presentation: http://www.slideshare.net/jakkbl/a-vocabulary-for-persistence 

Should IGSN be separate from iSamples?

Need to separate deep metadata concerns with Technical issue around high-level metadata for registration.

Should run a trial with EZID before General Assembly in December?  Compare existing API for IGSN creation with  EZID API http://ezid.cdlib.org/doc/apidoc.html 

How do we do smart searches to determine when a sample has been registered twice.
Issue of 2 digit name spaces by Australia raised. 
Australia should have AUVIC, AUNT, AUSA, AUWA, AUQLD, AUTAS, AUNSW - would eliminate need to request the namespaces from IGSN e.V.

Current process is contrary to original guidelines. All requests should go past the Executive Community first, if there is no agreement it passes to the technical committee and if there is no agreement, then it passes to the broader IGSN community. 

## Action Items
- IGSN e.V. to join WDS as an Associate Member (Kerstin send letter to Mustapha by Friday, MOU)
- Contact Donald Hobern of GBIF (GBIF has code of conduct, endorsed by governments with funding) - Wim offers to make contact
- instantiate quarterly meetings (Lesley W. to call meetings)
- provide existing documentation and links from previous work of Leslie Hsu
- See about getting Lindsay Powers engaged with IGSN 
- Steve Richard to re-engage with ODM2-IGSN-GeoSciML vocabulary harmonization
- Send out notes to the December meeting, including election of new officers as two years are up - need to seek candidates: President, Vice President and Treasurer
- Should we have a vote on EZID at the general assembly.
- Oct 31, deadline for article in special issue on persistent identifiers (Kerstin). IGSN manuscript fragment: https://docs.google.com/document/d/11z4wXKeomOt_Oc0ok-e-3yDzblljkEl-7mkkK_OP-Mc

- send out reminder for applications for membership

- Advice to Australia is to have the states as a subset of the AU name. (Jens, Kerstin draft letter to GA)

- managing office needs to send out call for nominations for officer positions to members
- Offer Associate membership to those members who have not actively participated.

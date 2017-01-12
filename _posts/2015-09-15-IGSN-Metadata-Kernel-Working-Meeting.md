---
layout: post
title: 2015-09-15 IGSN Metadata Kernel Working Meeting
---


Sept. 15-16th, 2015, Playa Room, Four Points by Sheraton Los Angeles Westside, Culver City, CA

Attendees: Jens Klump, Kerstin Lehnert, Rob Guralnick, Bob Arko, Doug Fils, Steve Richard, John Deck, Dirk Fleischer, Kelly Stroker, Lesley Wyborn, John Wieczorek, Adam Mansur, Gary Berg-Cross 

A PDF version of these notes is [available here](../../../../media/2015-09-15-IGSN-Metadata-Kernel-Working-Meeting.pdf)


# Tuesday September 15th, 9:00-17:00 PDT #


* Introduction, community scope
* IGSN system architecture (separation of identifier and description)
* Other PID systems (metadata, governance) 
* IGSN definition of roles, naming authorities, vocabularies
* Requirements for IGSN descriptive metadata
* IGSN metadata guidelines


# Wednesday September 16th, 9:00-15:30 PDT #


* IGSN metadata guidelines (cont.)
* Metadata Kernel versioning
* IGSN allocation guidelines for labs and collections (owner, curator, lab) (does anybody who wants a <5 digit namespace have to be a member = allocating agent?)
* Responsibilities of allocating agents towards IGSN e.V.
* deploy schema.igsn.org : decide who will do it
* IGSN syntax guidelines
   * Use cases
   * Legacy data
   * Guidelines
* Documentation, communication to members


Graphical representation of the CSIRO internal IGSN schema: <https://raw.githubusercontent.com/kitchenprinzessin3880/csiro-igsn-schema/master/igsn-csrio-v1.0.png>

Goolgle doc folder with related documents

# Topics #

* IGSNs are important for reproducibility, getting to metadata, and getting to the physical sample - IGSNs in publications should comply with certain rules.
* There is also the issue of labs who do analytical work for others, are not the owners of the original sample, but want to register and track the sample in their lab. It would be good to get some recommendations of how labs should handle this (the owner vs. the lab registering the IGSNs)
* There are different roles for archives and people in the IGSN metadata profile, we want this to be more standardized in the metadata profile, it is used in different ways now. "Archive" can be an institution, lab, person, so we should discuss the different roles (Official physical sample repository vs. collector). Archive vocabulary standardization is also something that could be discussed.
* Specific - Metadata schema development (open issues) :
   * Samples ownership information
   * Requirements and workflow for transferring samples from one allocating agent to another
   * Location of samples[a][b] - optional or mandatory?
   * IGSN registry schema - eventTypes should be refined- distinguish between events related to registration and metadata ; why are multiple events(log elements) allowed for a sample?
   * Alignment of the proposed metadata model with existing data standards should be documented to ensure correct application of the model across different domains.
   * 

There are also some notes/potential topics under point 2 on Tuesday in this Google Doc.


The Australian system of vehicle registration plates as an example of namespace governance and syntax: <https://en.wikipedia.org/wiki/Vehicle_registration_plates_of_Australia>


Examples from Western Australia: <http://www.transport.wa.gov.au/licensing/plateswa.asp>


# Meeting Notes #
2015-09-15
Kerstin Lehnert (LDEO, IEDA), Jens Klump (CSIRO), Adam Mansur (Smithsonian), Gary Berg Cross (SOCoP), John Wieczorek (Darwin Core), Kelly Stroker (NOAA), Lesley Wyborn (ANU), Rob Guralnick (U Fla, biodiversity), Stephen Richard (AZGS, geology, metadata), John Deck (UC Berkeley, Marine systems, biodiversity, field data collection, ARKs), Doug Fils (Consortium Ocean Leadership, IODP), Dick Fleischer (U Kiel Data Info manager, marine science), Bob Arko (LDEO, R2R, research cruises).


Other activities
CODATA group on physical samples
RDA session next week, EPIC, DataCite


Meeting goal:  agree on basic cross domain profile for documenting samples
Issue-- IGSN syntax
Rules for IGSN use


DataCite has very formal process for metadata model management.
International DOI foundation required definition of metadata Kernel to participate.
DOI is about bibliographic data, so was relatively simple evolution of system saw relaxation of mandatory field requirements, addition of vocabularies.


Register admin metadata, descriptive metadata is for harvesting
Top level registration is URI de-reference to URL for landing page, some admin data, no description of specimen
Description of specimen determined by community of practice. 
Harvest endpoints can offer one or more community profiles. Don’t necessarily have to agree on minimal profile for sample description.


Biodiversity experience:
De facto standard is Darwin Core. there are not PIDs, community doesn't understand what IDs are supposed to represent. Don't have any permanent binding between physical object and ID string.
"Birth Certificate for sample" .


SR: could be optional to comply with metadata profiles to be searchable in a central catalog
DF: leave it to the user communities to establish metadata and vocabularies, system of allocating agents is meant for leaving independence to AAs/communities
RG: think about lightest possible common set of controlled vocabularies.  


There is perception that there are some basic property of samples that are common, e.g. what kind of sample (basis of record).


Existing allocating agents have not followed a common metadata profile.


Metadata paper by British Atmospheric Data Center
A=Archiving (Administrative - what you need to manage the data or object)
B=Browsing (I have discovered the a group of objects based on D metadata: I browse these)
C=Character or Citation (Character =  QA/QC or Citation = How you cite the object)
D=Discovery (=19115 - basic discovery of the object - ie equivalent to a data object)
E=Extra/Extensions (Specific to a domain)


Source Document: 
B.N Lawrence, R Lowry, P Miller, H Snaith, A Woolf, 2009. Information in environmental data grids. Phil. Trans. R. Soc. A (2009), 367, 1003-1014 DOI: 10.1098/rsta.2008.0237  <http://doi.org/10.1098/rsta.2008.0237>


IGSN:  identifier string is ultimately bound to a material object. 
The object may still exist, or not. E.g. may only have a picture of the original object.


Why not use DOI. 
1. cost of membership in DataCite
2. control over content policies, vocabularies for identified resource representation


Without go-to identifier system, everybody who aggregates data makes up their own system.
don’t have a way to consistently describe the objects that are identified
Deep problem-- how to avoid assignment of different identifiers to same object.
Smithsonian-- using Ark: prefix, assigning UUID to objects in EMU catalog.


Grinnell-- bio samples, hierarchic system, e.g. id for group (expedition), and then serial number within that collection. Register group, then can add samples independently within that group. 
Cruises get an identifier, and samples are prefixed with that.
GBC: have existing local identifier schemes, want to make easy to map this into a PID system for permanence, reliability, wider usage. 
Smithsonian --asks people to cite smithsonian internal ID (in sharing agreements)


There are two topics that need discussion:
* syntax and structure of identifier strings
* information model for representation of the identified things


Conversation 1: identifier syntax
KL-- concern is that syntax was designed with specific use cases. Listing of IGSN in data tables, string should have a lot of information encoded, should be relative short. 
move from 3.6 to a more hierarchical system that more efficiently uses the identifier string space.
then allow allocating agents more flexibility in syntax definition.  Now, question is what is policy for allowing allocating agents to define different string syntax.  Concern-- easy recognition of valid IGSN in publications. Elsevier checks syntax for 9-digit numbers. 
practical issue for validation when identifiers are registered-- 
want to fit IGSN on physical sample
want to be able to scrape IDs in publication tables. 


JK--don't need specific syntax to validate identifier--can just try to resolve it.


SMR, JK-- it makes adoption easier if relax rules so people can use their existing internal identifier scheme.
Making a global rule that restricts syntax for some particular application (e.g. listing in a table) could be an impediment to uptake.


Could create "shadow" id--like a short URL, for any registered identifier.  Allocated could use any syntax, but system also creates equivalent compliant shorter version that use in publications. ARK uses this system. 


Concern is to separate concerns of allocating agents from global rules at IGSN top level.


Proposal No 1: Revise syntax guidelines to relax restrictions on ID length at the top level of IGSN 
Proposal:
Form smaller group to formulate proposal for flexible IGSN scheme.  
Goal: Define syntax scheme for IGSN of future.  


Who?: involve iSamples working group on Unique Identifiers, RDA (ref: <https://goo.gl/xyA6c8> )?, feedback from publishers.  


How: Need materials online, method to collect feedback, use existing wiki. Starting point is the [syntax wiki page](../../../../syntax). Summarize considerations from discussion f2f in LA; what needs to be discussed with allocating agent, publishers.  Orient discussion to particular user communities (curators, sample collectors, publishers...). Discussion should indicate reasons why shorter is better, the purpose and logic of consistent 9 character ID strings, and emphasize desire to continue with that ID length, but that if required, longer character ID strings can be allowed. 


Volunteers: Jens Klump, Steve Richard, John Deck, Dirk Fleischer, Kerstin Lehnert


Relevant External Initiatives
COPDESS: Coalition for Publishing Data in the Earth and Space Sciences
 <http://www.copdess.org/> . The Statement and list of Signatories in COPDESS is on <http://www.copdess.org/statement-of-commitment/> 


Project THOR (Technical and Human infrastructure for Open Research): <http://project-thor.eu/>  The Partners in THOR are <http://project-thor.eu/the-thor-partners/>


Registration roles and responsibilities
for current admin metadata see <https://drive.google.com/drive/folders/0B-5zXOYZ_JMIZjdXLXp1SUZzbTQ> slide #5


Discussion about access control information for the sample, for the sample metadata, sample collection location. What level in the metadata scheme is this handled. Private vs. public is currently not in admin metadata.


Sample Metadata[c]
What is it
Where is it now
The registration metadata should be immutable information; stateful information should be maintained separately.


what core metadata must be mandatory?
Top level Sesar model is reasonable:
        remove Distributor
Existing ID registration has relations


focus is geospatial sample from real world.


* IGSN[d]
* MetadataTimeStamp: when was this "birth certificate" last updated (or created) (1...1, not nillable)  timestamp W3C DateTime syntax
* MetadataKernelVersion: (1...1, not nillable) provided automatically by host.
* MetadataCreator[e]:  who created this "birth certificate" (analogous to DataCite publication agent). Intention is that this element identifies the party responsible for the content in this record--who should be contacted to report errors in this content. How the contact is actually implemented is determined by the allocating agent.  (1...1, not nillable) Use DataCite creator element implementation (see DataCite MetadataKernel v3.1, "creator").
[f]   Scheme values could use DataCite’s vocabulary at <http://purl.org/spar/datacite/> eg.
        http://purl.org/spar/datacite/doi
        http://purl.org/spar/datacite/ark
        http://purl.org/spar/datacite/isni
        etc.
        Note: Need to ask DataCite folks to add /igsn to this vocabulary.
see also the IANA register of URI schemes: <http://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml> 
   * SampleName[g]: text string for people to understand what is identified. What would typically be presented in a user interface. (1...1 ). Free text
   * AlternateIdentifier: (schema, value). Scheme scopes the authority or context for the identifier, value is the identifier string. Context might be a publication; ‘FreeText’ is a possible scheme value. Might be another IGSN for the same sample (ideally, one of the IGSN would have to have admin status deprecated). Semantics are ‘owl:SameAs’ (0..N). see comment on metadata creator for identifier scheme specification.
   * RelatedIdentifier: (Scheme, value, relationshipType). link to parent sample, paper, other resource. (0..N) Relations ontolgy
   * Remove RelatedIdentifier from top level metadata
   * Suggestion to use Relations Ontology to describe sample relations, which is more suitable to samples than the Datacite relations (See: <https://github.com/oborel/obo-relations>
   
   [h])
   * <http://trac.gfz-potsdam.de/igsn/wiki>


   * Description: Free text, anything else that might be useful to know about the sample at its "birth"(0...1)
   * SamplingLocation[i]: Where was the sample acquired relative to the Earth (or another celestial body...). Some samples might  be "non-geographic": mineral specimen, synthetic material... Suggest something like ISO19115 gmd:EX_Extent, allow vertical, horizontal geolocation + SRS, or geographic location name. Probably want to exclude the temporal and spatiotemporal extent subtypes in EX_Extent. (1...1, nillable[reason]).  For synthetic samples, sample location might be lab name, but Best practice is to not put in location coordinates for lab. Point locations are most typical way to specify sample location, but EX_Extent does not account well for these, may need different implementation.  Implementation should allow gazetter term and geometry and bounding box and vertical coordinate. Best practice is to provide[j] WKT geometry with SRS, could be point, line, BBox, polygon. (location might need to be time stamped to account for dynamic geodetics)
   * SamplingTime. When was the sample collected. instant or interval. have to determine encoding scheme for interchange, eg.(ISO 19156) (1...1, nillable[reason]). (need specifiction of sample dateTime encoding). YYYY, YYYY-MM, YYYY-MM-DD, YYYY-MM-DDZhh:mm
   * Collector. Who collected the sample. Must be nilable. Ideally want an URI for agent; also need name string. Role: Person who gets credit for picking location, getting funding, selecting and extracting the actual object. (1..N, nilable). ODP chief scientist, field geologist. Synthetic sample--experimentalist is collector. Composite core
   * URI
   * name string
   * OtherRole[k]: Ideally want an URI for agent; also need name string. Role: PI, technician, funding agent (award number, organization?), contributor. Other parties who should receive credit for the sample (0..N).  PI might be both collector and OtherRole@PI
   * URI
   * name string
   * role (vocabulary, ISO 19115)
   * <https://geo-ide.noaa.gov/wiki/index.php?title=ISO_19115_and_19115-2_CodeList_Dictionaries#CI_RoleCode>
   *    * SampleType[l]: describe the basic form of the object that is registered. e.g. polished section; core; pulp; solution, dredge haul in a box, lot, piece of material. Different profiles might have different vocabularies. (1..N, not nillable). Implementation should be a "scoped" name (vocabulary URI, concept/term URI, label for display).
   * Could use ODM2 SpecimenType?   <http://vocabulary.odm2.org/specimentype/>  [m]
   * use multiple vocabularies?
   * MaterialType[n]: categorize the material that composes to the sample, e.g. water, granite, tissue. Idea is to create a high-level cross-domain vocabulary. (1..N, nillable). ‘lot’ type samples (dredge haul, drill core) may have multiple materials included. Material may be categorized under different schemes. Implementation should be a ‘scoped’ name (vocabulary URI, concept/term URI, label for display). <http://vocabulary.odm2.org/medium/> and other vocabularies.
   * particulate
   * rock 
   * sediment 
   * soil
   * biologic material
   * fossilized material 
   * gas
   * ice
   * mineral
   * synthetic?
   * isolated from natural environment?
   * SamplingMethod[o][p]: term to categorize the process through which the sample was acquired as an independent object. (1..1, nilable). 
   * draft IUGS CGI sampling method vocabulary [q]draft: https://docs.google.com/spreadsheets/d/1z3sGgtC7W_lGLTo05zo3HGeWiuutCdrjpXbUi2NkmlE/edit#gid=0 
   * SampleStatus: Term specifying the current curation status of physical object. e.g. curated-public, destroyed, curated-limited.  (1..1, nillable). Might reduce to ‘isDestroyed’ true, false, unknown?[r]
   * accessibility: information to be maintained by the repository, not part of the IGSN kernel
   * existence: information to be maintained by the repository, not part of the IGSN kernel
   * SupplementalMetadata[s][t]: location of a supplemental metadata record (0...n, nillable)


Known Relevant Vocabularies:
IGSN:
 <http://www.geosamples.org/help/vocabularies#object>


CGI:
<http://resource.geosciml.org/vocabulary/cgi/201211/> current versions, available as html, rdf/xml and turtle (ttl)
<http://def.seegrid.csiro.au/sissvoc/cgi201211/collection>
Lithology Categories (rdf), Lithology Categories (html) 
<http://resource.geosciml.org/vocabulary/timescale/isc2014.rdf>




ODM2 (Based on O&M) <http://vocabulary.ODM2.org>
The Observations Data Model (ODM2) group <http://resource.geosciml.org/vocabulary/cgi/201211/simplelithology.rdis> working to develop a community information model to extend interoperability of spatially discrete, feature based earth observations derived from sensors and samples and improve the capture, sharing, and archival of these data. This information model, called ODM2, is being designed from a general perspective, with extensibility for achieving interoperability across multiple disciplines and systems that support publication of earth observations.(<https://github.com/ODM2/ODM2>)


Suggested later by Simon Cox (who could not make the meeting)
om-lite - OWL implementation of O&M 
- <http://def.seegrid.csiro.au/ontology/om/sam-lite> 
- <http://def.seegrid.csiro.au/ontology/om/om-lite> 
in particular the Specimen class <http://def.seegrid.csiro.au/ontology/om/sam-lite#Specimen> 
Note that it has two location properties - samplingLocation and currentLocation 
 ODM2 Schematic 

LInks to ODM2 Vocabularies.
<https://github.com/ODM2/ODM2/blob/master/doc/ODM2Docs/concept_controlledvocabs.md> 


<https://drive.google.com/drive/u/0/#folders/0B5JYwkWgsLhRVmtQamJzZmx5cW8/0B0mUuf2-qdlTd2xGTXBjMjlUUDQ/0B3v0QxIOuR_nQ0k4Zm5BNjhlbDQ>  


Material Types from the Envo ontology
+ environmental material
   * - aerosol
   * - air
   * + anthropogenic environmental material
   * - clay
   * - dust
   * - emulsion
   * + foam
   * - gravel
   * - ice
   * + lava
   * - mineral
   * + mud
   * + oil
   * + organic material
   * + rock
   * + sand
   * - scree
   * + scum
   * + sediment
   * - silt
   * + soil
   * + vapour
   * + water


​GeoNames (from BioSample Attributes)


geo_loc_name
	Geographical origin of the sample; use the appropriate name from this list <http://www.insdc.org/documents/country-qualifier-vocabulary>. Use a colon to separate the country or ocean from more detailed information about the location, eg "Canada: Vancouver" or "Germany: halfway down Zugspitze, Alps"
	

Australian National Data Service (ANDS) Vocabulary Project
<http://ands.org.au/services/controlled-vocabulary.html> 


<https://vocabs.ands.org.au/#!/>
Getting IGSN vocabularies into controlled name spaces.
The IGSN vocabularies could come under the governance of the Commission for the Management and Application of Geoscience Information (CGI: <http://www.cgi-iugs.org/> ) of the International Union of Geological Sciences (IUGS: <http://www.iugs.org/>).


Mark Rattenbury who is currently the Chair of the Geoscience Terminology Working Group (<http://www.cgi-iugs.org/tech_collaboration/geoscience_terminology_working_group.html>) of the CGI-IUGS has written:


The Geoscience Terminology Working Group has the CGI-IUGS mandate to develop and maintain international geoscience vocabularies. We look for pragmatic solutions for multiple uses, not just GeoSciML/ERML, and we certainly adopt existing material where it meets our requirements. We should definitely avoid running competing services. Some of those ODM2 vocabs take a much wider view than our geoscience realm but are useful starting points none the less.


Please pass on an invitation to the IGSN to contact me as Chair of GTWG to discuss how we can coordinate our respective requirements. We are open to new membership if IGSN see GTWG involvement as a way forward.


Mark's email is M.Rattenbury@gns.cri.nz 


Other Standards:
ISO 27730:2012 International standard collection identifier (ISCI)
<https://www.iso.org/obp/ui/#iso:std:iso:27730:ed-1:v1:en>






Discussion of Registering IGSN as trademark




Implementation and governance of IGSN schema
Schema (beta) online by 15 Nov 2015 for discussion at IGSN General Assembly at AGU (13 Dec 2015).
Publish xsd file at schema.igsn.org
Proposal to be developed by technical committee and published through GitHub. One month hearing period on schema proposal.
Subsequent changes to be communicated through tech@igsn.org and proposed through GitHub. 
Version changes need to be approved by the General Assembly.
Where will the schema be hosted? Recommendation by task group.
Definition of roles in IGSN
Who is allowed to change the metadata record?
   * To be defined by the respective Allocating Agents.
Roles:
   * Allocating Agent registering IGSN with with the IGSN registry (analogous to DataCite Registry)
   * Collector of the sample (originator)
   * Custodian of the sample (point of contact)
   * Metadata creator (analogous to DataCite Publication Agent)


Who can assigns an IGSN?
   * To be defined by the respective Allocating Agents.
   * Existing IGSN must be respected to avoid duplicate registrations.
Responsibilities of Allocating Agents towards IGSN
   * Record must validate against an approved version of the IGSN schema.
   * Record must uniquely identify an individual sample.
   * Each assigned identifier must resolve to a valid endpoint.
   * Participate in the annual IGSN General Assembly, in person or remotely 
   * Pay membership dues annually to IGSN
   * Adhere to published IGSN syntax
   * Must register any IGSN’s they have allocated
   * Have a succession plan if they cease to be an IGSN allocating agent
Transfer of samples between Allocating Agents
Currently not possible to transfer samples between AAs. Authority would have to be resolved on the level of individual samples. Needs to resolved by IGSN MDS.

# ACTION ITEMS: #
   1. Register IGSN as trademark
   1. Who: Kerstin Lehnert needs to check with CU and NSF lawyers
   2. By: 26 September 2015

      1. New metadata kernel schema (beta) online for discussion at IGSN General Assembly at AGU (13 Dec 2015).  Note: This is separate from the administrative metadata.
      1. Who: Metadata Task Group
      2. By: 15 November 2015


      1. Remove RelatedIdentifier from top level (administrative) metadata
      1. Who: Metadata Task Group
      2. By: 15 November 2015 when metadata kernel goes into production (conditional)


      1. Revise relation types in <http://trac.gfz-potsdam.de/igsn/wiki> and link to suitable ontology.
      1. Who: Metadata Task Group
      2. By: 15 November 2015 when metadata kernel goes into production (conditional)


      1. Discussion of registering boreholes and other sampling features using IGSN. Sense of group is that this is out of scope in IGSN discussion for now, but is a needed resource.
      1. Who: Metadata Task Group
      2. By: 15 November 2015 when metadata kernel goes into production (conditional)


      1. Create a few examples of how to populate SamplingLocation
      1. Who: Metadata Task Group
      2. By: 15 November 2015 when metadata kernel goes into production (conditional)


      1. Promote ODM2 vocabulary governance (specimen type, medium)  to appropriate long- term sustainable host,  IUGS???, or else ODM may have follow-on project (BigCZ?)
        [SMR note: I'll add these to the GTWG drafts and notify the WG of new items. We'll need to identify a shepherd for them]
      1. Who: Lesley Wyborn
      2. By: 13 December 2015 (IGSN General Assembly at AGU)


      1. Set up mailing list tech@igsn.org  (to be used generally by all three Task Groups)
      1. Who: Bob Arko
      2. By: 25 September 2015


      1. Recommend hosting for new site schema.igsn.org .
      1. Who: Metadata Task Group
      2. By: 25 September 2015


      1. Revise syntax guidelines to relax restrictions on ID length at the top level of IGSN 
<https://docs.google.com/document/d/1uLsUXg4TDglteGYODGZhIIatx0kAbEipw9GEuaYcHlU> 
         1. Who: Identifier Task Group
         2. By: 12 October 2015


         1. Executive Board to review Allocating Agent responsibilities. Should the role of a PA be introduced?
         1. Who: Executive Board
         2. By: 12 October 2015


         1. Check whether Allocating Agents can/should/must be registered in re3data.org
         1. Who: Jens Klump
         2. By: 31 October 2015


         1. Communication to IGSN mailing list on results of this meeting
         1. Who: Jens Klump
         2. By: 25 September





Specific Groups Formed
         1. Identifier Task Group
         1. Membership: Jens Klump, Steve Richard, John Deck, Dirk Fleischer, Kerstin Lehnert
         2. Tasks: Define revised IGSN syntax schema (no longer limited to 9 characters)


         1. Metadata Task Group
         1. Membership: Bob Arko (Leader), Doug Fils, John Deck, Rob Guralnick, Megan Carter, Anu Devaraju, Steve Richard.
         2. Tasks: 
         1. Remove RelatedIdentifier from top level (administrative) metadata (Action 3)
         1. By 15 November 2015 when metadata kernel goes into production (conditional)


         1. Revise relation types in http://trac.gfz-potsdam.de/igsn/wiki and link to suitable ontology (Action 4)
         1. By 15 November 2015 when metadata kernel goes into production (conditional)


         1. Discussion of registering boreholes and other sampling features using IGSN. Sense of group is that this is out of scope in IGSN discussion for now, but is a needed resource (Action 5)
         1. By 15 November 2015 when metadata kernel goes into production (conditional)


         1. Examples on SamplingLocation (Action 6)
         1. By 15 November 2015 when metadata kernel goes into production (conditional)


         1. Recommend hosting for IGSN schema (Action 9)
         1. By: 25 September


         1. Introduce location of extended metadata schemas (community profiles) for a sample? Must have valid xsd. (Action 10)
         1. By: 15 November 2015 when metadata kernel goes into production (conditional)


         1. New metadata kernel schema (beta) online for discussion at IGSN General Assembly at AGU (13 Dec 2015).  Note: This is separate from the administrative metadata (Action 2)
         1. By: 15 November


         1. Documentation Task Group: 
         1. Membership: Jens Klump (Leader), Lesley Wyborn, Megan Carter, John Deck, Dirk Fleischer, Steve Richard
         2. Tasks: 
         1. Clean up existing wiki, add more user-centric information.
         2. Revise syntax guidelines to relax restrictions on ID length at the top level of IGSN (Action 10)
         1. By:
         1. Documentation on related identifier, relationship types, collections. 
         1. By:
         1. Documentation on the kernel v1.0 itself as per DataCite to accompany .xsd file
		 
[a]Does this mean sampling location of the parent sample, or sampling location of the derived material?
[b]I would say parent sample. Only problem arises if a parent sample is private and the parent's metadata cannot be accessed. Again, we need to distinguish between 'published' IGSNs and those used for 'internal' sample management.
[c]Create a metadata table (element name, definition, occurrence and data type) - easy to implement a xsd
[d]This is required element
[e]Specify that this refers to data center/individual scientist registering the samples - not an allocating agent
[f]Datacite: -<xs:element name="creator" maxOccurs="unbounded">, but in our metadata only one creator is allowed.
[g]Can be used to specify the local sample name
[h]The relations are too specific, complex URI - not recommended for a top-level schema - might want to consider simple mereology...we just need basic parthood relations (composition, constitution) to relate samples to sub-samples..
[i]Can assign location to gml:AbstractGeometryType to support both spatial and non-spatial location. But, this might introduce complex data structures. We need something simple and understandable like GeoJSON..
[j]Check Ramona Walls, iPlant geolocation tools
[k]Custodian - useful to include temporal information
[l]make sure sampletype is distinct from sampling method!


sampleType is equivalent to MaterialSample in BCO  (biological collections ontology) or DarwinCore;


Also SampleType is the object of an RDF relationship (e.g. Sample rdf:type SampleType).  


BCO can define sub-classes as needed to define particular sampleTypes.
[m]This vocabulary is mostly process oriented whereas sampleType seems to be more about objects (continuants).  This is somewhat confusing. again, see reccomendation for BCO above.
[n]see ENVO (environment ontology) which has environmental  materials including various kinds of rocks.  They are looking for input on this branch and would be happy to receive requests (just talked to Pier Luigi Buttigieg)--- submit requests on the ENVO github site
[o]This is SpecimenCollection Process in BCO
[p]From Ramona Walls-- she reccomends an application ontology for this -- GCO?
[q]This tabular records should be formalized.
[r]Belongs to real-time database at the level of repositories.
[s]Can this be specified using the relatedIdentifer?
[t]This is not a pointer to a related object but a link to an alternative description of the same object.
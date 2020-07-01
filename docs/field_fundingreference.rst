.. include:: /common/replacements.rst

.. _dci:dci:fundingReference:

Funding Reference (MA, 0-n)
===========

Specification of financial support (funding) by funders. If the described items where assembled in the course of funded projects, this should be stated here.
(obligation: |FundingReferencesObl| occurrence: |FundingReferencesOcc|)

Property fundingReference (M, 0-n)
----------------

Specification of funding by way of a project.

Subpropberty funderName (M, 1)
~~~~~~~~~~~~~~~~

Name of the funding provider.

**Allowed values, other constraints**

Free text.

Subpropberty funderIdentifier (MA, 0-n)
~~~~~~~~~~~~~~~~

Unique identifier of the funding body. As identifiers are more distinct than names, available funder identifiers should be given.

**Allowed values, other constraints**

Free text.

Attribute funderIdentifierType (M, 1)
'''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''

The type of the funder identifier.

**Allowed values, other constraints**

*Examples:*

* ``ISNI`` - |ISNI|
* ``VIAF`` - |VIAF|
* ``Crossref Funder`` - |CrossrefFunder|
* ``ISIL`` - |ISIL|
* ``GRID`` - |GRID|
* ``OrgRef`` - |OrgRef|
* national organisation ID authoritative systems (e.g. PTCRIS_OrgID (Portugal))
* ``Other``

Subproperty awardNumber (M, 0-1)
~~~~~~~~~~~~~~~~

The funder's code of the award (grant), i.e. the project number.

**Allowed values, other constraints**

Free text.

Attribute awardURI (O, 0-1)
'''''''''''''''''''''''''''''''''''''''''''''''''

A funder's landing page URI informing about the award (grant).

**Allowed values, other constraints**

A URL.

Subproperty awardTitle (O, 0-1)
~~~~~~~~~~~~~~~~

The title or name of the award (grant). 

**Allowed values, other constraints**

Free text.

Examples
--------

.. code-block:: xml
   :linenos:

   <fundingReferences>
     <fundingReference>
       <funderName>European Commission</funderName>
       <funderIdentifier funderIdentifierType="Crossref Funder">
          http://doi.org/10.13039/501100000780</funderIdentifier>
       <awardNumber awardURI="https://cordis.europa.eu/project/rcn/212961_en.html">777541</awardNumber>
       <awardTitle>OpenAIRE-Advance</awardTitle>
     </fundingReference>
     <fundingReference>
       <funderName>Academy of Finland</funderName>
       <funderIdentifier funderIdentifierType="ISNI">0000 0004 0647 6886</funderIdentifier>
       <awardNumber>80262</awardNumber>
       <awardTitle>Geophysics of the Seasonal Sea Ice Zone</awardTitle>
     </fundingReference>
   </fundingReferences>

Usage Instruction
-----------------

An authoritative list of projects is exposed by OpenAIRE through 
`OAI-PMH <http://api.openaire.eu/oai_pmh?verb=ListRecords&set=projects&metadataPrefix=oaf>`_ 
and 
`REST <http://api.openaire.eu/search/projects>`_ 
(see `documentation <http://api.openaire.eu>`_), and available for all repository managers. Values include the project name and ID and of course the funder. The project ID equals the Grant Agreement identifier or Award number. Please note that the set of funders integrated in OpenAIRE is continuously expanding.

Context
-------

**Do Not Confuse With**

* :ref:`d:creator` (Use ``creator`` for primary responsibility, i.e authorship)
* :ref:`d:contributor` (Use ``contributor`` in cases of lesser responsibility)
* :ref:`d:publisher` (Use ``publisher`` for organisations e.g. when the nature of responsibility is ambiguous)

**DataCite v4.1 Differentiation**

* fundingReference_ is *mandatory if applicable* in OpenAIRE instead of *optional* in DataCite.
* funderIdentifier_ is *mandatory if applicable* in OpenAIRE instead of *optional* in DataCite.
* funderIdentifier_ can occur |funderIdentifierOcc| times in OpenAIRE instead of 0-1 times in DataCite.
* `@funderIdentifierType`_ allows more types in OpenAIRE than in DataCite.
* awardNumber_ is *mandatory* in OpenAIRE instead of *optional* for DataCite.

**OpenAIRE Data Guidelines v3 Differentiation**

* Following DataCite v3, the OpenAIRE Data Guidelines v3 used ``contributor`` (with ``contributorType`` Funder) to indicate funding information.
* The formerly applied `info:eu-repo/grantAgreement/[Funder]/[FundingProgram]/[ProjectID]/[Jurisdiction]/[ProjectName]/[ProjectAcronym] <http://purl.org/eu-repo/semantics/#info-eu-repo-GrantAgreementIdentifiers>`_ notation is replaced by the detailed DataCite properties.
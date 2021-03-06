.. _dci:rights:

Rights (MA)
===========

``datacite:rights``

Cardinality
~~~~~~~~~~~

*Mandatory*

*Occurrence: 1*

Definition and Usage Instruction
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Any rights information for this resource. The property may be repeated to record complex rights characteristics.

**Usage Instruction**

``Free text``

Provide a rights management statement for the resource or reference a service providing such information. Include embargo information if applicable. Use the complete title of a license  and include version information if applicable. May be used for software licenses. 

Examples:
	Creative Commons Attribution 3.0 Germany License
	
	Apache License, Version 2.02
	
Use terms from the `COAR Access Right Vocabulary`_ (occurrence: 1).

======================================== ========================
conceptURI                               label
======================================== ========================
http://purl.org/coar/access_right/c_abf2 ``open access``
http://purl.org/coar/access_right/c_f1cf ``embargoed access``
http://purl.org/coar/access_right/c_16ec ``restricted access``
http://purl.org/coar/access_right/c_14cb ``metadata only access``
======================================== ========================

.. note::
   Unlike DataCite, OpenAIRE restricts the use of this property to indicate the access right. 
   Mandatory when applicable property in OpenAIRE instead of optional in DataCite.

   OpenAIRE uses this property to explicit declare the access right of the resource via 16.1 rightsURI (MA). This does not exclude also using 16. Rights (MA) property for additional rights statements as defined by DataCite Metadata Schema v4.3. In particular OpenAIRE also recommends including license information if available.

	
**Remarks**

- adapted from `DataCite Metadata Schema`_ v4.3

Attribute rightsURI (MA)
************************

The URI of the license.


.. note::
  Use terms from the `COAR Access Right Vocabulary`_ (occurrence: 1).

  ======================================== ========================
  conceptURI                               label
  ======================================== ========================
  http://purl.org/coar/access_right/c_abf2 ``open access``
  http://purl.org/coar/access_right/c_f1cf ``embargoed access``
  http://purl.org/coar/access_right/c_16ec ``restricted access``
  http://purl.org/coar/access_right/c_14cb ``metadata only access``
  ======================================== ========================

The URI of the license (occurrences: 0-1).

Allowed values, examples, other constraints

Example:


Attribute rightsIdentifierScheme (MA)
************************************

The name of the scheme is a controlled vocabulary.

Controlled list: 
	- SPDX
	- COAR


Attribute schemeURI (R)
***********************

Attribute rightsIdentifier (O)
******************************

A short, standardized version of the license name.

Example: CC-BY-3.0

.. note::
  It’s suggested to use the identifiers from the SPDX licence list (https://spdx.org/licenses/).


Example
~~~~~~~

.. code-block:: xml
   :linenos:
   
   <rightsList>
       <rights rightsURI=”http://purl.org/coar/access_right/c_abf2” rightsIdentifierScheme="COAR">open access</rights>
   </rightsList>


.. code-block:: xml
   :linenos:
   
   <rightsList>
      <rights rightsURI=”http://purl.org/coar/access_right/c_abf2” rightsIdentifierScheme="COAR">open access</rights>
      <rights rightsURI=”http://creativecommons.org/licenses/by/4.0/” rightsIdentifier="CC-BY-4.0" rightsIdentifierScheme="SPDX" schemeURI="https://spdx.org/licenses/">
          Creative Commons Attribution 4.0 International</rights>
   </rightsList>


.. _DataCite Metadata Schema: http://schema.datacite.org/meta/kernel-4.3/
.. _COAR Access Right Vocabulary: http://vocabularies.coar-repositories.org/documentation/access_rights/



.. _dci:datePublication:

Publication Date (M, 1)
====================

``datacite:date``

DCMI Definition: A date associated with an event in the life cycle of the resource. Typically, the date will be associated with the creation or availability of the resource. Recommended best practice for encoding the date value is defined in a profile of `ISO 8601 [W3CDTF] <https://www.iso.org/iso-8601-date-and-time-format.html>`_ and follows the ``YYYY-MM-DD`` format.

*Allowed values, other constraints:*

The date should be formatted according to the W3C encoding rules for dates and times:

* Date completeness:

  * ``YYYY-MM-DD`` (e.g. 1997-07-16), where:

    * ``YYYY`` [four-digit year] is ''mandatory''
    * ``MM`` [two-digit month (01=January, etc.)] is ''optional''
    * ``DD`` [two-digit day of month (01 through 31)] is ''optional''

* Date type:

  * Often repository systems have more then one date fields that serve different purposes. Date of creation, publication, modified, promotion, etc. Preferably in the end-users perspective the most logical and meaningful date will be the date of publication. 
  * If no date of publication is available, use any other date available. It is better to use one date than no date at all.

* Datestamp additions:

  * Additions like “Zulu time” should NOT be part of the metadata.

* Fuzzy dates:

  * For fuzzy dates use a logical year that most represents that period, e.g. ``1650`` instead of ``17th century``.
  * To express more about that temporal period, one can use the ``dc:coverage`` field. A temporal period can be expressed in a standard way when precisely defined (see :ref:`dc:coverage`) or when “fuzzy” or uncertain by free text expressions. A service provider is able to sort dates based on date standards like W3CDTF. Since there is no standard for fuzzy dates for terms like “Renaissance” or “17th Century”, they will simply not appear on date-based query results.

Property date (M, 1)
--------------------

Use the publication date as value.

Attribute dateType (M, 1)
~~~~~~~~~~~~~~~~

The type of date. 

*Controlled value lists:*

.. include:: vocabularies/datetype.rst

Examples
----------------

Date of publication:

.. code-block:: xml
   :linenos:

   <datacite:date dateType="Issued">2000-12-25</datacite:date>
   
Start and end date of embargo:

.. code-block:: xml
   :linenos:

   <datacite:dates>
      <datacite:date dateType="Accepted">2011-12-01</datacite:date>
      <datacite:date dateType="Available">2012-12-01</datacite:date>
   </datacite:dates>

.. _DRIVER Guidelines v2 element date: https://wiki.surfnet.nl/display/DRIVERguidelines/Date
.. _DataCite MetadataKernel: http://schema.datacite.org/meta/kernel-4.3/

Context
-------

**Do Not Confuse With**



**DataCite v4.3 Differentiation**



**OpenAIRE Data Guidelines v2 Differentiation**

====================
Electronic invoicing
====================

EDI, or electronic data interchange, allows to rapidly send information digitally using standard
formats.

This feature enables automating the administration between companies and might also be required by
some governments for fiscal control or to facilitate the administration.

Any business that processes large volumes of documents and forms can benefit from an EDI solution to
increase automation and improve accuracy.

.. seealso::
   - `Odoo and EDI <https://www.odoo.com/blog/odoo-news-5/odoo-and-edi-766#blog_content>`_
   - :ref:`Fiscal localization packages <overview/fiscal-localization-package>`
   - :ref:`List of supported countries <overview/localizations-list>`

Configuration
=============

Go to :menuselection:`Accounting --> Configuration --> Journals --> Customer Invoices -->
Advanced Settings --> Electronic Invoicing` and check the boxes you need.

Once :guilabel:`Electronic Invoicing` is selected,  XML documents are generated, either visible or
embedded in the PDF.

.. note::
   - By default, the :guilabel:`Factur-X` option is checked. It means that an XML file is automatically
     included in the PDF document that is sent.
   - The options available depend on your localization.
   - Odoo supports the Peppol format bis3 that can be used via existing access points. Odoo should
     soon become an access point itself.

.. _reference/orm/changelog:

=========
Changelog
=========

Odoo Online version 15.1
========================

- With `#79622 <https://github.com/odoo/odoo/pull/79622>`_, the :meth:`reversed` works efficiently on recordset.

Odoo Online version 15.2
========================

- Remove :attr:`_sequence` attribute of :class:`BaseModel`:  Let PostgreSQL uses the default sequence of the primary key
  `#82727 <https://github.com/odoo/odoo/pull/82727>`_
- :meth:`~odoo.models._write` of :class:`BaseModel` doesn't raise error anymore for no existing records (`#82727 <https://github.com/odoo/odoo/pull/82727>`_)
- Specific index types on :class:`Field`:  With `#83274 <https://github.com/odoo/odoo/pull/83274>`_ and
  `#83015 <https://github.com/odoo/odoo/pull/83015>`_, developers can now define what type of
  indexes can be used on fields by PostgreSQL. See the :ref:`index property <reference/fields>` of
  `odoo.fields.Field`.
- With `#82896 <https://github.com/odoo/odoo/pull/82896>`_, translated :class:`Field` are not prefetch by default anymore.
- Remove :attr:`column_format` and :attr:`deprecated` attributes of :class:`Field` (`#82727 <https://github.com/odoo/odoo/pull/82727>`_)

Odoo Online version 15.3
========================

- Arguments name change for :meth:`~odoo.models.search`, :meth:`~odoo.models.search_count`
  and :meth:`~odoo.models._search`:  `args` is called `domain` now. (`#83687 <https://github.com/odoo/odoo/pull/83687>`_)
- :meth:`~odoo.models.filtered_domain` now conserve order of the current recordset (`#83687 <https://github.com/odoo/odoo/pull/83687>`_)
- With `#83687 <https://github.com/odoo/odoo/pull/83687>`_, :meth:`~odoo.models.browse` doesn't accept :class:`str` as ids anymore.
- Deprecate :meth:`~odoo.models.fields_get_keys` and :meth:`~odoo.models.get_xml_id` methods of :class:`BaseModel` (`#83687 <https://github.com/odoo/odoo/pull/83687>`_)
- Remove :meth:`~odoo.models._mapped_cache` method of :class:`BaseModel` (`#83687 <https://github.com/odoo/odoo/pull/83687>`_)
- Remove :attr:`limit` attribute of :class:`One2many` and :class:`Many2many`
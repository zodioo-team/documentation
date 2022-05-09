:show-content:

.. _studio/fields:

==================
Fields and widgets
==================

Fields structure the models of a database. If you picture a model as a table or spreadsheet, fields
are the columns where the records (i.e., the rows) data is stored. Fields also define the type of
data that is stored within them. How the data is presented and formatted on the :abbr:`UI (User
Interface)` is defined by their widget.

From a technical point of view, there are 15 field types in Odoo. However, you can choose from 20
fields in Studio, as some field types are available more than once with a different default widget.

.. tip::
   :guilabel:`New Fields` can only be added to the :ref:`general/form` and
   :ref:`multiple-records/list` views. On other views, you can only add :guilabel:`Existing Fields`,
   i.e., fields already on the model.

.. _fields/simple-fields:

Simple fields
=============

Simple fields contain basic values, such as text, numbers, files, etc.

.. note::
   Below, the field’s technical name is presented in brackets. Non-default widgets, when available,
   are given as bullet points.

.. _simple-fields/text:

Text (char)
-----------

The :guilabel:`Text` field is used for short text containing any character. One text line is
displayed when filling out the field.

- :guilabel:`Badge`: displays the value inside a rounded shape, similarly to a tag. The value cannot
  be edited   on the UI, but a default value can be set.
- :guilabel:`Copy to Clipboard`: users can copy the value by clicking a button.
- :guilabel:`Email`: the value becomes a clickable *mailto* link.
- :guilabel:`Image`: displays an image using an URL. The value cannot be edited manually, but a
  default value can be set.

  .. note::
     This works differently than selecting the :ref:`Image <simple-fields/image>` field directly, as
     the image isn’t stored in Odoo when you use a :guilabel:`Text` field with the Image widget. For
     example, it can be useful if you want to save disk space.

- :guilabel:`Phone:` the value becomes a clickable *tel* link.

  .. tip::
     Tick :guilabel:`Enable SMS` to add an option to send an SMS directly from Odoo next to the
     field.

- :guilabel:`URL`: the value becomes a clickable URL.

.. _simple-fields/multiline-text:

Multiline Text (text)
---------------------

The :guilabel:`Multiline Text` field is used for longer text containing any type of character. Two
text lines are displayed on the UI when filling out the field.

- :guilabel:`Copy to Clipboard`: users can copy the value by clicking a button.

.. _simple-fields/integer:

Integer (integer)
-----------------

The :guilabel:`Integer` field is used for all integer numbers (i.e., positive, negative, or zero,
without a decimal).

- :guilabel:`Handle`: displays a drag handle icon to change the position of a record in
  :guilabel:`List` view.
- :guilabel:`Percentage Pie`: displays the value inside a percentage circle, usually for a computed
  value. The value cannot be edited on the UI, but a default value can be set.
- :guilabel:`Progress Bar`: displays the value next to a percentage bar, usually for a computed
  value. The field cannot be edited manually, but a default value can be set.

.. _simple-fields/decimal:

Decimal (float)
---------------

The :guilabel:`Decimal` field is used for all decimal numbers (i.e., positive, negative, or zero,
with a decimal).

.. note::
   Decimal numbers are displayed with two decimals after the decimal point on the UI, but they are
   stored in the database with more precision.

- :guilabel:`Monetary`: it is similar to using the :ref:`Monetary <simple-fields/monetary>` field.
  It is recommended to use the later as it offers more functionalities.
- :guilabel:`Percentage`: displays a percent character (%) after the value.
- :guilabel:`Percentage Pie`: displays the value inside a percentage circle, usually for a computed
  value. The field cannot be edited manually, but a default value can be set.
- :guilabel:`Progress Bar`: displays the value next to a percentage bar, usually for a computed
  value. The field cannot be edited manually, but a default value can be set.
- :guilabel:`Time`: the value must follow the *hh:mm* format, with a maximum of 59 minutes.

.. _simple-fields/monetary:

Monetary (monetary)
-------------------

The :guilabel:`Monetary` field is used for all monetary values.

.. note::
   When you first add a :guilabel:`Monetary` field, you are prompted to add a *Currency* field if
   none exists already on the model. Odoo offers to add the *Currency* field for you. Once it is
   added, add the :guilabel:`Monetary` field again.

.. _simple-fields/html:

Html (html)
-----------

The :guilabel:`Html` field is used to add text that can be edited using the Odoo HTML editor.

- :guilabel:`Multiline Text`: disables the Odoo HTML editor to allow editing raw HTML.

.. _simple-fields/date:

Date (date)
-----------

The :guilabel:`Date` field is used to select a date on a calendar.

- :guilabel:`Remaining days`: the remaining number of days before the selected date is displayed
  (e.g., in 5 days), based on the current date.

.. _simple-fields/date-time:

Date & Time (datetime)
----------------------

The :guilabel:`Date & Time` field is used to select a date on a calendar and a time on a clock. The
user's current time is automatically used if no time is set.

- :guilabel:`Date`: used to record the time without displaying it on the UI.
- :guilabel:`Remaining days`: displays the remaining number of days before the selected date (e.g.,
  in 5 days), based on the current date and time.

.. _simple-fields/checkbox:

Checkbox (boolean)
------------------

The :guilabel:`Checkbox` field is used when a value should only be true or false, indicated by
checking or unchecking a checkbox.

- :guilabel:`Button`: displays a radio button. The widget works without switching to the edit mode.
- :guilabel:`Toggle`: displays a toggle button. The widget works without switching to the edit mode.

.. _simple-fields/selection:

Selection (selection)
---------------------

The :guilabel:`Selection` field is used when users should select a single value from a group of
predefined values.

- :guilabel:`Badge`: displays the value inside a rounded shape, similarly to a tag. The value cannot
  be edited on the UI, but a default value can be set.
- :guilabel:`Badges`: displays all selectable values simultaneously inside rectangular shapes,
  organized horizontally.
- :guilabel:`Priority`: displays star symbols instead of values, which can be used to indicate an
  importance or satisfaction level, for example. This has the same effect as selecting the
  :ref:`Priority <simple-fields/priority>` field, although, for the latter, four priority values are
  already predefined.
- :guilabel:`Radio`: displays all selectable values at the same time as radio buttons.

  .. tip::
     By default, radio buttons are organized vertically. Tick :guilabel:`display horizontally` to
     switch the way they are displayed.

.. _simple-fields/priority:

Priority (selection)
--------------------

The :guilabel:`Priority` field is used to display a three-star rating system, which can be used to
indicate importance or satisfaction level. This field type is a :ref:`Selection
<simple-fields/selection>` field with the :guilabel:`Priority` widget selected by default and four
priority values predefined. Consequently, the :guilabel:`Badge`, :guilabel:`Badges`,
:guilabel:`Radio`, and :guilabel:`Selection` widgets have the same effects as described under
Selection.

.. tip::
   To change the number of available stars by adding or removing values, click :guilabel:`Edit
   Values`. Note that the first value is equal to 0 stars (i.e., when no selection is made), so
   having four values results in a three-star rating system, for example.

.. _simple-fields/file:

File (binary)
-------------

The :guilabel:`File` field is used to upload any type of file, or sign a form (Sign widget).

- :guilabel:`Image`: users can upload an image file, which is then displayed in :ref:`general/form`
  view. This has the same effect as using the :ref:`Image <simple-fields/image>` field.
- :guilabel:`PDF Viewer`: users can upload a PDF file, which can be then browsed from the
  :ref:`general/form` view.
- :guilabel:`Sign`: users can electronically sign the form. This has the same effect as selecting
  the :ref:`Sign <simple-fields/sign>` field.

.. _simple-fields/image:

Image (binary)
--------------

The :guilabel:`Image` field is used to upload an image and display it in :ref:`general/form` view.
This field type is a :ref:`File <simple-fields/file>` field with the :guilabel:`Image` widget
selected by default. Consequently, the :guilabel:`File`, :guilabel:`PDF Viewer`, and
:guilabel:`Sign` widgets have the same effects as described under File.

.. tip::
   To change the display size of uploaded images, select :guilabel:`Small`, :guilabel:`Medium` or
   :guilabel:`Large` under the :guilabel:`Size` option.

.. _simple-fields/sign:

Sign (binary)
-------------

The :guilabel:`Sign` field is used to sign the form electronically. This field type is a :ref:`File
<simple-fields/file>` field with the :guilabel:`Sign` widget selected by default. Consequently, the
:guilabel:`File`, :guilabel:`Image`, and :guilabel:`PDF Viewer` widgets have the same effects as
described under :ref:`File <simple-fields/file>`.

.. tip::
   To give users the :guilabel:`Auto` option when having to draw their signature, select one of the
   available :guilabel:`Auto-complete with` fields (:ref:`Text <simple-fields/text>`, :ref:`Many2One
   <relational-fields/many2one>`, and :ref:`Related Field <relational-fields/related-field>` on the
   model only). The signature is automatically generated using the data from the selected field.

.. _fields/relational-fields:

Relational fields
=================

Relational fields are used to link and display the data from records on another model.

.. note::
   Below, the field’s technical name is presented in brackets. Non-default widgets, when available,
   are given as bullet points.

.. _relational-fields/many2one:

Many2One (many2one)
-------------------

The :guilabel:`Many2One` field is used to link another record (from another model) to the record
being edited. The record’s name from the other model is then displayed on the record being edited.

.. example::
   On the *Sales Order* model, the *Customer* field is a :guilabel:`Many2One` field pointing at the
   *Contact* model. Thanks to this, many sales orders can be linked to the same contact (customer).

.. tip::
   - To prevent users from creating a new record in the linked model, tick :guilabel:`Disable
     creation`.
   - To prevent users from opening records in a pop-up window, tick :guilabel:`Disable opening`.
   - To help users only select the right record, click on :guilabel:`Domain` to create a filter.

- :guilabel:`Badge`: displays the value inside a rounded shape, similarly to a tag. The value cannot
  be edited on the UI, but a default value can be set.
- :guilabel:`Radio`: displays all selectable values at the same time as radio buttons.

.. _relational-fields/one2many:

One2Many (one2many)
-------------------

The :guilabel:`One2Many` field is used to display the existing relations between a record on the
current model and multiple records from another model.

.. example::
   You could add a :guilabel:`One2Many` field on the *Contact* model to look at all the sales orders
   that are linked to a single contact (customer).

.. note::
   To use a :guilabel:`One2Many` field, the two models must have been linked already using a
   :ref:`Many2One <relational-fields/many2one>` field. One2Many relations don’t exist on their own:
   a reverse-search of existing Many2One relations is performed.

.. _relational-fields/lines:

Lines (one2many)
----------------

The :guilabel:`Lines` field is used to create a table with rows and columns (e.g., the lines of
products on a sales order).

.. tip::
   To modify the columns, click on the :guilabel:`Lines` field and then :guilabel:`Edit List View`.
   To edit the form that pops up when a user clicks on :guilabel:`Add a line`, click on
   :guilabel:`Edit Form View` instead.

.. _relational-fields/many2many:

Many2Many (many2many)
---------------------

The :guilabel:`Many2Many` field is used to link multiple records from another model to multiple
records on the current model. Many2Many fields can use :guilabel:`Disable creation`,
:guilabel:`Disable opening`, :guilabel:`Domain`, just like :ref:`Many2One
<relational-fields/many2one>` fields.

.. example::
   On the *Project Task* model, the *Assignees* field is a :guilabel:`Many2Many` field pointing at
   the *Contact* model. Thanks to this, the same user can be assigned to multiple tasks and multiple
   users can be assigned to the same task.

- :guilabel:`Checkboxes`: users can select several values using checkboxes.
- :guilabel:`Tags`: users can select several values appearing in rounded shapes, also known as
  *tags*. This has the same effect as selecting the :ref:`Tags <relational-fields/tags>` field.

.. _relational-fields/tags:

Tags (many2many)
----------------

The :guilabel:`Tags` field is used to display several values from another model appearing in rounded
shapes, also known as *tags*. This field type is a :ref:`Many2Many <relational-fields/many2many>`
field with the :guilabel:`Tags` widget selected by default. Consequently, the :guilabel:`Checkboxes`
and :guilabel:`Many2Many` widgets have the same effects as described under Many2Many.

.. tip::
   To have tags with different background colors, tick :guilabel:`Use colors`.

.. _relational-fields/related-field:

Related Field (related)
-----------------------

A :guilabel:`Related Field` is not a relational field per se; no relationship is created between
models. It uses an existing relationship to fetch and display information from another record.

.. example::
   To display the email address of a customer on the *Sales Order* model, use the :guilabel:`Related
   Field` *partner_id.email* by selecting :guilabel:`Customer` and then :guilabel:`Email`.

.. _fields/properties:

Properties
==========

- :guilabel:`Invisible`: When it isn’t necessary for users to view a field on the UI, tick
  :guilabel:`Invisible`. It helps clear the UI by only showing the essential fields depending on a
  specific situation.

  .. example::
     On the :guilabel:`Form` view of the *Contact* model, the *Title* field only appears when
     *Individual* is selected, as that field wouldn’t be helpful for a *Company* contact.

  .. note::
     The :guilabel:`Invisible` attribute also applies to Studio. To view hidden fields inside
     Studio, click on a view's :guilabel:`View` tab and tick :guilabel:`Show Invisible
     Elements`.

- :guilabel:`Required`: If a field should always be completed by the user before being able to
  proceed, tick :guilabel:`Required`.
- :guilabel:`Read only`: If users shouldn’t be able to modify a field, tick :guilabel:`Read only`.

  .. note::
     You can choose to apply these three properties only for specific records by clicking on
     :guilabel:`Conditional` and creating a filter.

- :guilabel:`Label`: The :guilabel:`Label` is the field’s name on the UI.

  .. note::
     This is not the same name as used in the PostgreSQL database. To view and change the latter,
     enable :ref:`Developer mode <developer-mode>`, and edit the :guilabel:`Technical Name`.

- :guilabel:`Help Tooltip`: To explain the purpose of a field, write a description under
  :guilabel:`Help Tooltip`. It is displayed inside a tooltip box when hovering with your mouse over
  the field’s label.
- :guilabel:`Placeholder`: To provide an example of how a field should be completed, write it under
  :guilabel:`Placeholder`. It is displayed in light gray in lieu of the field’s value.
- :guilabel:`Widget`: To change the default appearance or functionality of a field, select one of
  the available widgets.
- :guilabel:`Default value`: To add a default value to a field when a record is created, use
  :guilabel:`Default value`.
- :guilabel:`Limit visibility to groups`: To limit which users can see the field, select a user
  access group.
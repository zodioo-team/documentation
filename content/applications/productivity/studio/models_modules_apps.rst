:show-content:

.. _studio/models-modules-apps:

=========================
Models, modules, and apps
=========================

Models, also known as *Objects*, determine the logical structure of a database and how data is
stored, organized, and manipulated. In other words, a model is a table of information that can be
linked with other tables. A model usually represents a business concept, such as a *sales order*,
*contact*, or *product*.

Modules and apps contain various elements, such as models, views, data files, web controllers and
static web data. The only difference is semantic: larger, standalone modules are typically called
apps, whereas modules are usually add-ons to said apps.

.. _models-modules-apps/suggested-features:

Suggested features
==================

When you create a new model or app with Studio, you can choose to add up to 14 features to speed
up the creation process. These features bundle fields, default settings, and views that are usually
used together to provide some standard functionality. Most of these features can be added later on,
but adding them from the start makes the model creation process much easier. Furthermore, in some
cases, these features interact together to increase their usefulness. For example, creating a model
with the :ref:`suggested-features/picture` and :ref:`suggested-features/pipeline-stages` features
enabled adds the image in the card layout of the :ref:`multiple-records/kanban` view.

.. _suggested-features/contact-details:

Contact details
---------------

Selecting :guilabel:`Contact details` adds to the :ref:`general/form` view a :ref:`Many2one
<relational-fields/many2one>` field linked to the *Contact* model and two of its :ref:`Related
Fields <relational-fields/related-field>`: *Phone* and *Email*. The *Contact* field is also added to
the :ref:`multiple-records/list` view, and the :ref:`multiple-records/map` view is activated.

.. _suggested-features/user-assignment:

User assignment
---------------

Selecting :guilabel:`User assignment` adds to the :ref:`general/form` view a :ref:`Many2one
<relational-fields/many2one>` field linked to the *Users* model, with the following
:guilabel:`Domain`: ``[Share User]`` ``[is]`` ``[not set (false)]`` to only allow the selection of
*Internal Users*. In addition, the *many2one_avatar_user* widget is used to display the user’s
avatar. The *Responsible* field is also added to the :ref:`multiple-records/list` view.

.. _suggested-features/date-calendar:

Date & Calendar
---------------

Selecting :guilabel:`Date & Calendar` adds to the :ref:`general/form` view a :ref:`Date
<simple-fields/date>` field and activates the :ref:`timeline/calendar` view.

.. _suggested-features/date-range-gantt:

Date range & Gantt
------------------

Selecting :guilabel:`Date range & Gantt` adds to the :ref:`general/form` view two :ref:`Date
<simple-fields/date>` fields next to each other: one to set a start date, the other to set an end
date, using the *daterange* widget, and activates the :ref:`timeline/gantt` view.

.. _suggested-features/pipeline-stages:

Pipeline stages
---------------

Selecting :guilabel:`Pipeline stages` activates the :ref:`multiple-records/kanban` view, adds
several fields such as :ref:`Priority <simple-fields/priority>` and *Kanban State*, and three
stages: *New*, *In Progress*, and *Done*. The *Pipeline status bar* and the *Kanban State* field are
added to the :ref:`general/form` view. The *Color* field is added to the
:ref:`multiple-records/list` view.

.. note::
   The :guilabel:`Pipeline stages` feature can be added at a later stage.

.. _suggested-features/tags:

Tags
----

Selecting :guilabel:`Tags` adds to the :ref:`general/form` and :ref:`multiple-records/list` views a
:ref:`Tags <relational-fields/tags>` field, creating a *Tag* model with preconfigured access rights
in the process.

.. _suggested-features/picture:

Picture
-------

Selecting :guilabel:`Picture` adds to the top-right of the :ref:`general/form` view an :ref:`Image
<simple-fields/image>` field.

.. note::
   The :guilabel:`Picture` feature can be added at a later stage.

.. _suggested-features/lines:

Lines
-----

Selecting :guilabel:`Lines`: adds to the :ref:`general/form` view a :ref:`Lines
<relational-fields/lines>` field inside a :guilabel:`Tab` component.

.. _suggested-features/notes:

Notes
-----

Selecting :guilabel:`Notes` adds to the :ref:`general/form` view an :ref:`Html <simple-fields/html>`
field using the full width of the form.

.. _suggested-features/monetary-value:

Monetary value
--------------

Selecting :guilabel:`Monetary value` adds to the :ref:`general/form` and
:ref:`multiple-records/list` views a :ref:`Monetary <simple-fields/monetary>` field. The
:ref:`reporting/graph` and :ref:`reporting/pivot` views are also activated.

.. note::
   A *Currency* field is added and hidden from the view.

.. _suggested-features/company:

Company
-------

Selecting :guilabel:`Company` adds to the :ref:`general/form` and :ref:`multiple-records/list` views
a :ref:`Many2one <relational-fields/many2one>` field linked to the *Company* model.

.. note::
   This is only useful if you work in a multi-company environment.

.. _suggested-features/custom-sorting:

Custom Sorting
--------------

Selecting :guilabel:`Custom Sorting` adds to the :ref:`multiple-records/list` view a handle icon to
manually reorder records.

.. _suggested-features/chatter:

Chatter
-------

Selecting :guilabel:`Chatter` adds to the :ref:`general/form` view Chatter functionalities (sending
messages, logging notes, and scheduling activities).

.. note::
   The :guilabel:`Chatter` feature can be added at a later stage.

.. _suggested-features/archiving:

Archiving
---------

Selecting :guilabel:`Archiving` adds to the :ref:`general/form` and :ref:`multiple-records/list`
views the :guilabel:`Archive` action and hides archived records from searches and views by default.

.. _studio/export-import:

Export and import customizations
================================

When you do any customization with Studio, a new module named :guilabel:`Studio customizations` is
added to your database.

To export these customizations, toggle Studio on the main dashboard and, under the
:guilabel:`Customizations` menu on the top-left, click on :guilabel:`Export` to download a *.zip*
file containing all customizations.

To import and install these customizations in another database, connect to the destination database,
toggle Studio, go to the :guilabel:`Customizations` menu and select :guilabel:`Import`, then upload
the exported *.zip* file before clicking on the :guilabel:`Import` button.

.. warning::
   Before importing, make sure the destination database contains the same apps and modules as the
   source database. Studio doesn't add the underlying modules as dependencies of the exported
   module.
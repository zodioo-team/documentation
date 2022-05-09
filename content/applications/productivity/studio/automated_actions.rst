:show-content:

.. _studio/automated-actions:

===============================
Automated actions (automations)
===============================

Automated actions are used to trigger automatic changes based on user actions (e.g., apply a
modification when a field is set to a specific value) or on time conditions (e.g., archive a record
7 days after its last update).

To create an automated action with Studio, the following elements need to be defined: the
:ref:`automated-actions/model`, the :ref:`automated-actions/trigger`, the :ref:`"Apply on"
<automated-actions/apply-on>`, and the :ref:`automated-actions/action`.

.. _automated-actions/model:

Model
=====

Select the model where the automated action should be applied.

.. _automated-actions/trigger:

Trigger
=======

Define when the automated action should be applied. Different triggers are available.

.. _trigger/on-creation:

On Creation
-----------

The action is triggered when a record is created and then saved.

.. _trigger/on-update:

On Update
---------

The action is triggered when a previously saved record is edited and then saved.

- Use :guilabel:`Trigger Fields` to specify which fields - and only those - trigger the action on
  their update.
- To detect when a record changes from one state to another, define a :guilabel:`Before Update
  Domain` filter, which checks if the condition is satisfied before the record is updated. Then set
  an :ref:`automated-actions/apply-on` filter, which checks if the condition is satisfied after the
  record is updated.

  .. example::
     If you want the automated action to happen when an email address is set on a contact, define
     the :guilabel:`Before Update Domain` to: ``email is not set`` and the :guilabel:`Apply on`
     domain to: ``email is set``.

.. _trigger/on-creation-update:

On Creation & Update
--------------------

The action is triggered when a record is created and saved or edited afterward and saved.

.. _trigger/on-deletion:

On Deletion
-----------

The action is triggered when a record is deleted.

.. note::
   This trigger is rarely used, as archiving records is usually preferred to deletion.

.. _trigger/form-modification:

Based on Form Modification
--------------------------

The action is triggered when any change is done to a trigger field’s value on the
:ref:`general/form` view, even before saving the record. This trigger only works on the UI when a
modification is made by a user. If the field is changed through another action and not by the user,
the action won’t run.

.. note::
   This trigger can only be used with the :ref:`action/python-code` action, so development is
   required.

.. _trigger/timed-condition:

Based on Timed Condition
------------------------

The action is triggered when a trigger field’s date or date & time value is reached.

- To trigger the action after the :guilabel:`Trigger Date`, add a number of minutes, hours, days, or
  months under :guilabel:`Delay after trigger date`. To trigger the action before, add a negative
  number instead.

.. note::
   By default, the scheduler checks for trigger dates every 4 hours.

.. _automated-actions/apply-on:

Apply on
========

Define on which records of the model the automated action should be applied. It works the same way
as when you apply filters on a model.

.. _automated-actions/action:

Action
======

Determine what the automated action should do (server action).

.. _action/python-code:

Execute Python Code
-------------------

The action is used to execute Python code. The available variables are described on the
:guilabel:`Python Code` tab, which is also used to write your code, or on the :guilabel:`Help` tab.

- To allow the action to be run through the website, tick :guilabel:`Available on the Website` and
  add a :guilabel:`Website Path`.

.. _action/new-record:

Create a new Record
-------------------

The action is used to create a new record on any model.

.. note::
   Selecting a :guilabel:`Target Model` is only required if you want to target another model than
   the one you are on.

- To link the record that triggered the creation of the new record, select a field under
  :guilabel:`Link Field`. For example, you could create a contact automatically when a lead is
  turned into an opportunity.
- :guilabel:`Data to Write` tab: the tab is used to specify the new record’s values. After selecting
  a :guilabel:`Field`, select its :guilabel:`Evaluation Type`:

  - :guilabel:`Value`: used to directly give the field’s raw value in the :guilabel:`Value` column.
  - :guilabel:`Reference`: used to select the record under the :guilabel:`Record` column and let
    Studio add the internal ID in the :guilabel:`Value` column.

    .. example::
       If an automated action creates a new project, you can assign it to a specific user by setting
       the :guilabel:`Field` to *Responsible User (Project)* , the
       :guilabel:`Evaluation Type` to *Reference* and the *Record* to a specific user.

  - :guilabel:`Python expression`: used to define the newly created record’s value for a field
    dynamically using Python code in the :guilabel:`Value` column.

.. _action/update-record:

Update the Record
-----------------

The action is used to set value(s) for field(s) of any record on the current model.

.. note::
   The process to fill in the :guilabel:`Data to Write` tab is the same as described under
   :ref:`action/new-record`.

.. _action/several-actions:

Execute several actions
-----------------------

The action is used to trigger multiple actions at the same time. To do so, click on :guilabel:`Add a
line` under the :guilabel:`Actions` tab. In the :guilabel:`Child Actions` pop-up, click on
:guilabel:`Create` and configure the action.

.. _action/send-email:

Send Email
----------

The action is used to send an email to a contact linked to a specific record. To do so, select or
create an :guilabel:`Email Template`.

.. _action/add-followers:

Add Followers
-------------

The action is used to subscribe existing contacts to the record.

.. _action/next-activity:

Create Next Activity
--------------------

The action is used to schedule a new activity linked to the record. Use the :guilabel:`Activity` tab
to set it up as usual, but instead of the :guilabel:`Assigned to` field, select an
:guilabel:`Activity User Type`. Select :guilabel:`Specific User` and add the user under
:guilabel:`Responsible` if the activity should be always assigned to the same user. To dynamically
target a user linked to the record, select :guilabel:`Generic User From Record` instead and specify
the :guilabel:`User field name`.

.. _action/send-sms:

Send SMS Text Message
---------------------

The action is used to send an SMS to a contact linked to the record. To do so, select or create an
:guilabel:`SMS Template`.

.. tip::
   If you want sent messages to be logged in the Chatter, tick :guilabel:`Log as Note`.
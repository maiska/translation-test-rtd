========
Glossary
========

admin qube
==========

A type of :ref:`qube <user/reference/glossary:qube>` used for administering Qubes OS.

-  Currently, the only admin qube is :ref:`dom0 <user/reference/glossary:dom0>`.

app qube
========

Any :ref:`qube <user/reference/glossary:qube>` that does not have a root filesystem of its own.
Every app qube is based on a :ref:`template <user/reference/glossary:template>` from which it
borrows the root filesystem.

-  Previously known as: ``AppVM``, ``TemplateBasedVM``.

-  Historical note: This term originally meant “a qube intended for
   running user software applications” (hence the name “app”).

disposable
==========

A type of temporary :ref:`app qube <user/reference/glossary:app qube>` that self-destructs when
its originating window closes. Each disposable is based on a :ref:`disposable template <user/reference/glossary:disposable template>`.

See :doc:`How to Use Dispoables </user/how-to-guides/how-to-use-disposables>`.

-  Previously known as: ``DisposableVM``, ``DispVM``.

disposable template
===================

Any :ref:`app qube <user/reference/glossary:app qube>` on which :ref:`disposables <user/reference/glossary:disposable>` are
based. A disposable template shares its user directories (and,
indirectly, the root filesystem of the regular :ref:`template <user/reference/glossary:template>`
on which it is based) with all :ref:`disposables <user/reference/glossary:disposable>` based on
it.

-  Not to be confused with the concept of a regular
   :ref:`template <user/reference/glossary:template>` that is itself disposable, which does not
   exist in Qubes OS.

-  Disposable templates must be app qubes. They cannot be regular
   :ref:`templates <user/reference/glossary:template>`.

-  Every :ref:`disposable <user/reference/glossary:disposable>` is based on a disposable template,
   which is in turn based on a regular :ref:`template <user/reference/glossary:template>`.

-  Unlike :ref:`disposables <user/reference/glossary:disposable>`, disposable templates have the
   persistence properties of normal :ref:`app qubes <user/reference/glossary:app qube>`.

-  Previously known as: ``DisposableVM Template``, ``DVM Template``,
   ``DVM``.

dom0
====
 :ref:`Domain <user/reference/glossary:domain>` zero. A type of :ref:`admin qube <user/reference/glossary:admin qube>`. Also
known as the **host** domain, dom0 is the initial qube started by the
Xen hypervisor on boot. Dom0 runs the Xen management toolstack and has
special privileges relative to other domains, such as direct access to
most hardware.

-  The term “dom0” is a common noun and should follow the capitalization
   rules of common nouns.

domain
======

In Xen, a synonym for :ref:`VM <user/reference/glossary:vm>`.  See `“domain” on the Xen Wiki <https://wiki.xenproject.org/wiki/Domain>`__.

-  This term has no official meaning in Qubes OS.

domU
====

Unprivileged :ref:`domain <user/reference/glossary:domain>`. Also known as **guest** domains,
domUs are the counterparts to dom0. In Xen, all VMs except dom0 are
domUs. By default, most domUs lack direct hardware access.

-  The term “domU” is a common noun and should follow the capitalization
   rules of common nouns.

-  Sometimes the term :ref:`VM <user/reference/glossary:vm>` is used as a synonym for domU. This
   is technically inaccurate, as :ref:`dom0 <user/reference/glossary:dom0>` is also a VM in Xen.

HVM
===

Hardware-assisted Virtual Machine. Any fully virtualized, or
hardware-assisted, :ref:`VM <user/reference/glossary:vm>` utilizing the virtualization extensions
of the host CPU. Although HVMs are typically slower than paravirtualized
qubes due to the required emulation, HVMs allow the user to create
domains based on any operating system.

See :doc:`Standalones and HVM </user/advanced-topics/standalones-and-hvms>`.

management qube
===============

A :ref:`qube <user/reference/glossary:qube>` used for automated management of a Qubes OS
installation via :doc:`Salt </user/advanced-topics/salt>`.

named disposable
================

A type of :ref:`disposable <user/reference/glossary:disposable>` given a permanent name that
continues to exist even after it is shut down and can be restarted
again. Like a regular :ref:`disposable <user/reference/glossary:disposable>`, a named disposable
has no persistent state: Any changes made are lost when it is shut down.

-  Only one instance of a named disposable can run at a time.

-  Like a regular :ref:`disposable <user/reference/glossary:disposable>`, a named disposable
   always has the same state when it starts, namely that of the
   :ref:`disposable template <user/reference/glossary:disposable template>` on which it is based.

-  Technical note: Named disposables are useful for certain :ref:`service    qubes <user/reference/glossary:service qube>`, where the combination of persistent device
   assignment and ephemeral qube state is desirable.

net qube
========

Internally known as ``netvm``. The property of a :ref:`qube <user/reference/glossary:qube>` that
specifies from which qube, if any, it receives network access. Despite
the name, “net qube” (or ``netvm``) is a *property* of a qube, not a
*type* of qube. For example, it is common for the net qube of an :ref:`app qube <user/reference/glossary:app qube>` to be the :ref:`service qube <user/reference/glossary:service qube>`
``sys-firewall``, which in turn uses ``sys-net`` as its net qube.

-  If a qube does not have a net qube (i.e., its ``netvm`` is set to
   ``None``), then that qube is offline. It is disconnected from all
   networking.

-  The name ``netvm`` derives from “Networking Virtual Machine.” Before
   Qubes 4.0, there was a type of :ref:`service qube <user/reference/glossary:service qube>`
   called a “NetVM.” The name of the ``netvm`` property is a holdover
   from that era.

qube
====

A secure compartment in Qubes OS. Currently, qubes are implemented as
Xen :ref:`VMs <user/reference/glossary:vm>`, but Qubes OS is independent of its underlying
compartmentalization technology. VMs could be replaced with a different
technology, and qubes would still be called “qubes.”

-  **Important:** The term “qube” is a common noun and should follow the
   capitalization rules of common nouns. For example, “I have three
   qubes” is correct,” while “I have three Qubes” is incorrect.

-  Note that starting a sentence with the plural of “qube” (i.e.,
   “Qubes…”) can be ambiguous, since it may not be clear whether the
   referent is a plurality of qubes or :ref:`Qubes OS <user/reference/glossary:qubes os>`.

-  Example usage: “In Qubes OS, you do your banking in your ‘banking’
   qube and your web surfing in your ‘untrusted’ qube. That way, if your
   ‘untrusted’ qube is compromised, your banking activities will remain
   secure.”

-  Historical note: The term “qube” was originally invented as an
   alternative to “VM” intended to make it easier for less technical
   users to understand Qubes OS and learn how to use it.

Qubes OS
========

A security-oriented operating system (OS). The main principle of Qubes
OS is security by compartmentalization (or isolation), in which
activities are compartmentalized (or isolated) in separate :ref:`qubes <user/reference/glossary:qube>`.

-  **Important:** The official name is “Qubes OS” (note the
   capitalization and the space between “Qubes” and “OS”). In casual
   conversation, this is often shortened to “Qubes.” Only in technical
   contexts where spaces are not permitted (e.g., in usernames) may the
   space be omitted, as in ``@QubesOS``.

Qubes Windows Tools (QWT)
=========================

A set of programs and drivers that provide integration of Windows qubes
with the rest of the Qubes OS system.

See `Qubes Windows Tools <https://github.com/Qubes-Community/Contents/blob/master/docs/os/windows/windows-tools.md>`__ and
`Windows <https://github.com/Qubes-Community/Contents/blob/master/docs/os/windows/windows.md>`__.

service qube
============

Any :ref:`app qube <user/reference/glossary:app qube>` the primary purpose of which is to provide
services to other qubes. ``sys-net`` and ``sys-firewall`` are examples
of service qubes.

standalone
==========

Any :ref:`qube <user/reference/glossary:qube>` that has its own root filesystem and does not share
it with another qube. Distinct from both :ref:`templates <user/reference/glossary:template>` and :ref:`app qubes <user/reference/glossary:app qube>`.

See :doc:`Standalones and HVMs </user/advanced-topics/standalones-and-hvms>`.

-  Previously known as: ``StandaloneVM``.

template
========

Any :ref:`qube <user/reference/glossary:qube>` that shares its root filesystem with another qube.
A qube that is borrowing a template’s root filesystem is known as an :ref:`app qube <user/reference/glossary:app qube>` and is said to be “based on” the template.
Templates are intended for installing and updating software
applications, but not for running them.

See :doc:`Templates </user/templates/templates>`.

-  No template is an :ref:`app qube <user/reference/glossary:app qube>`.

-  A template cannot be based on another template.

-  Regular templates cannot function as :ref:`disposable    templates <user/reference/glossary:disposable template>`. (Disposable templates must be
   app qubes.)

-  Previously known as: ``TemplateVM``.

VM
==

An abbreviation for “virtual machine.” A software implementation of a
machine (for example, a computer) that executes programs like a physical
machine.

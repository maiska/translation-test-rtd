==============
Xfce templates
==============

If you would like to use Xfce (more lightweight compared to GNOME
desktop environment) Linux distribution in your qubes, you can install
one of the available Xfce templates for :doc:`Fedora </user/templates/fedora/fedora>`, `CentOS <https://github.com/Qubes-Community/Contents/blob/master/docs/os/centos.md>`__
or `Gentoo <https://github.com/Qubes-Community/Contents/blob/master/docs/os/gentoo.md>`__.

Installation
============

The Fedora Xfce templates can be installed with the following command
(where ``X`` is your desired distro and version number):

::

   [user@dom0 ~]$ sudo qubes-dom0-update qubes-template-X-xfce

If your desired version is not found, it may still be in :doc:`testing </user/downloading-installing-upgrading/testing>`. You may wish to try again with the testing
repository enabled:

::

   [user@dom0 ~]$ sudo qubes-dom0-update --enablerepo=qubes-templates-itl-testing qubes-template-X-xfce

If you would like to install a community distribution, like CentOS or
Gentoo, try the install command by enabling the community repository:

::

   [user@dom0 ~]$ sudo qubes-dom0-update --enablerepo=qubes-templates-community qubes-template-X-xfce

If your desired version is not found, it may still be in :doc:`testing </user/downloading-installing-upgrading/testing>`. You may wish to try again with the testing
repository enabled:

::

   [user@dom0 ~]$ sudo qubes-dom0-update --enablerepo=qubes-templates-community-testing qubes-template-X-xfce

The download may take a while depending on your connection speed.

To reinstall a Xfce template that is already installed in your system,
see :doc:`How to Reinstall a template </user/templates/how-to-reinstall-a-template>`.

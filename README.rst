===========================
``gs.content.email.layout``
===========================
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Layout of HTML-formatted email notifications in GroupServer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:Author: `Michael JasonSmith`_
:Contact: Michael JasonSmith <mpj17@onlinegroups.net>
:Date: 2013-10-10
:Organization: `GroupServer.org`_
:Copyright: This document is licensed under a
  `Creative Commons Attribution-Share Alike 4.0 International License`_
  by `OnlineGroups.Net`_.

Introduction
============

HTML-formatted email notifications are formatted differently to
Web pages, due to the peculiarities of email clients. This
product supplies the page template that provide the layout for
the HTML notifications. The resulting page is then normally
processed by the ``SiteEmail`` or ``GroupEmail`` classes [#base]_
to produce HTML that can be added to a notification [#notify]_.

Resources
=========

- Code repository:
  https://github.com/groupserver/gs.content.email.layout/
- Documentation:
  http://groupserver.readthedocs.org/projects/gscontentemaillayout
- Questions and comments to
  http://groupserver.org/groups/development
- Report bugs at https://redmine.iopen.net/projects/groupserver

.. _GroupServer: http://groupserver.org/
.. _GroupServer.org: http://groupserver.org/
.. _OnlineGroups.Net: https://onlinegroups.net/
.. _Michael JasonSmith: http://groupserver.org/p/mpj17/
.. _Creative Commons Attribution-Share Alike 4.0 International License:
    http://creativecommons.org/licenses/by-sa/4.0/

.. [#base] See <https://github.com/groupserver/gs.content.email.base/>
.. [#notify] See  <https://github.com/groupserver/gs.profile.notify/>

..  LocalWords:  Viewlets CSS groupserver emailFooter emailStyle css http
..  LocalWords:  nz prebody tal

===========================
``gs.content.email.layout``
===========================
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Layout of HTML-formatted email notifications in GroupServer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:Author: `Michael JasonSmith`_
:Contact: Michael JasonSmith <mpj17@onlinegroups.net>
:Date: 2013-09-27
:Organization: `GroupServer.org`_
:Copyright: This document is licensed under a
  `Creative Commons Attribution-Share Alike 3.0 New Zealand License`_
  by `OnlineGroups.Net`_.

Introduction
============

HTML-formatted email notifications are formatted differently to Web pages,
due to the peculiarities of email clients. This product supplies the `page
template`_ that provide the layout for the HTML notifications. The
resulting page is then normally processed by the ``SiteEmail`` or
``GroupEmail`` classes [#base]_ to produce HTML that can be added to a
notification [#notify]_.

Page Template
=============

There is only one page template, which provides a simple full-page
layout. To use it call the following in the ``<html>`` element::

  <html xmlns="http://www.w3.org/1999/xhtml"
    xmlns:tal="http://xml.zope.org/namespaces/tal"
    xmlns:metal="http://xml.zope.org/namespaces/metal"
    metal:use-macro="context/@@groupserver_email_layout/page">

There are three slots defined by the macro.

``metal:fill-slot="title"``: 
  The compulsory title of the page. It is **always** provided by pages that
  use the standard layouts, and **always** contains a ``<title>``
  element. It is *normally* set to the subject of the email message::
  
    <title metal:fill-slot="title">This is the title</title>

``metal:fill-slot="prebody"``: 
  The optional content that appears before the header of the page. Used by
  some pages to emulate the look of an email message by adding false To,
  From and Subject fields.

``metal:fill-slot="body"``:
  The **compulsory** body of the page.

Example
-------

::

  <html xmlns="http://www.w3.org/1999/xhtml"
    xmlns:tal="http://xml.zope.org/namespaces/tal"
    xmlns:metal="http://xml.zope.org/namespaces/metal"
    metal:use-macro="context/@@groupserver_email_layout/page">
    <head>
      <title metal:fill-slot="title">Notification: 
        <span tal:replace="view/siteInfo/name">Site</span></title>
    </head>
    <body>
      <div id="a-page" metal:fill-slot="body">
        <p>I am a notification, honest.</p>
      </div><!--a-page-->
    </body>
  </html>

Viewlets
========

The email layout uses two viewlet managers. The ``groupserver.emailStyle``
manager supplies the CSS that lays out the message [#css]_. The footer is
supplied by the ``groupserver.emailFooter``, which is provided by this
product.

Within the footer there is one viewlet by default:
``gs-content-email-layout-footer``. It links to the Privacy policy,
Acceptable use policy, and the About page for the site.

Resources
=========

- Code repository: https://source.iopen.net/groupserver/gs.content.email.layout/
- Questions and comments to http://groupserver.org/groups/development
- Report bugs at https://redmine.iopen.net/projects/groupserver

.. _GroupServer: http://groupserver.org/
.. _GroupServer.org: http://groupserver.org/
.. _OnlineGroups.Net: https://onlinegroups.net/
.. _Michael JasonSmith: http://groupserver.org/p/mpj17/
.. _Creative Commons Attribution-Share Alike 3.0 New Zealand License:
   http://creativecommons.org/licenses/by-sa/3.0/nz/

.. [#base] See <https://source.iopen.net/groupserver/gs.content.email.base/>
.. [#notify] See  <https://source.iopen.net/groupserver/gs.profile.notify/>
.. [#css] See  <https://source.iopen.net/groupserver/gs.content.email.css/>

..  LocalWords:  Viewlets CSS groupserver emailFooter emailStyle css http
..  LocalWords:  nz prebody tal

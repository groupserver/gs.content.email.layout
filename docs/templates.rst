Page Template
=============

The ``groupserver_email_layout/page`` page template provides a
simple full-page layout for an email notification:

.. code-block:: xml

  <html xmlns="http://www.w3.org/1999/xhtml"
        xmlns:tal="http://xml.zope.org/namespaces/tal"
        xmlns:metal="http://xml.zope.org/namespaces/metal"
        metal:use-macro="context/@@groupserver_email_layout/page">

There are three slots defined by the macro.

``metal:fill-slot="title"``: 
  The compulsory title of the page. It is **always** provided by
  pages that use the standard layouts, and **always** contains a
  ``<title>`` element. It is *normally* set to the subject of the
  email message:
  
.. code-block:: xml

    <title metal:fill-slot="title">This is the title</title>

``metal:fill-slot="prebody"``: 
  The optional content that appears before the header of the
  page. Used by some pages to emulate the look of an email
  message by adding false :mailheader:`To`, :mailheader:`From`
  and :mailheader:`Subject` fields.

``metal:fill-slot="body"``:
  The **compulsory** body of the page.

Example
-------

.. code-block:: xml

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

..  LocalWords:  mailheader

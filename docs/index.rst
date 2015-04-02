:mod:`gs.content.email.layout`
==============================

HTML-formatted email notifications are formatted differently to
Web pages, due to the peculiarities of email clients. This
product supplies the page template that provide the layout for
the HTML notifications. The resulting page is then normally
processed by the :class:`gs.content.email.base.SiteEmail` or
:class:`gs.content.email.base.GroupEmail` classes [#base]_ to
produce an HTML page that can be added to a notification
[#notify]_.

Contents:

.. toctree::
   :maxdepth: 2

   templates
   viewlets
   HISTORY

Resources
=========

- Code repository:
  https://github.com/groupserver/gs.content.email.layout/
- Documentation:
  http://groupserver.readthedocs.org/projects/gscontentemaillayout
- Questions and comments to
  http://groupserver.org/groups/development
- Report bugs at https://redmine.iopen.net/projects/groupserver

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

.. [#base] See ``gs.content.email.base``
           <http://groupserver.readthedocs.org/projects/gscontentemailbase>
.. [#notify] See ``gs.content.email.base``
             <https://github.com/groupserver/gs.profile.notify/>

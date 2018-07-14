================
diazotheme.plone
================


Introduction
============

``diazotheme.plone`` package provides diazo themes based on the `Sunburst Theme`_ 
using the **theming** and **packaging** features available for create Diazo_ theme
using `plone.app.theming`_.

``diazotheme.plone`` package contains the following diazo implementations: 

- ``classic``, a diazo theme based on `plonetheme.classic`_ used until Plone 3 versions.
- ``sunburst``, a diazo theme based on `plonetheme.sunburst`_ to be used with theme base "(unstyled)".
- ``responsive``, a diazo theme to responsify `plonetheme.sunburst`_ through diazo, to be used with theme base `Sunburst Theme`_.

How to create a child theme
---------------------------

Any of the three theme folders can be used to create your own child theme, 
based on `diazoframework.plone`_. You can either wrap the theme up in a package 
or you can create a zip file of the folder and upload that to the theme panel.

There are two ways of creating a child theme.


The package way
^^^^^^^^^^^^^^^

For this example, lets assume we are creating a package called
diazotheme.newtheme and we will copy the 'responsive' theme in this 
package.

1. Created the ``diazotheme.newtheme`` package (for instance through ``paster`` script).

2. Copy ``diazotheme.plone/diazotheme/plone/responsive`` to
   ``diazotheme.newtheme/diazotheme/newtheme/responsive``.

3. Rename ``diazotheme.newtheme/diazotheme/newtheme/responsive``
   to ``diazotheme.newtheme/diazotheme/newtheme/static`` (arbitrary
   name).

4. Add `<plone:static directory="static" name="newtheme" type="theme"/>`
   to ``diazotheme.newtheme/diazotheme/newtheme/configure.zcml``.

5. Change ``diazotheme.newtheme/diazotheme/newtheme/static/manifest.cfg``
   to reflect the changes, so: ::
   
        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png


The zip file way
^^^^^^^^^^^^^^^^

Again, lets assume we use the 'responsive' theme and we want to end up
with the 'newtheme' name.

1. Copy ``diazotheme.plone/diazotheme/plone/responsive`` to your file system.

2. Rename 'responsive' to 'newtheme' (the folder name wil become the
   theme name in the theme panel)

3. Change ``newtheme/manifest.cfg``
   to reflect the changes, so: ::

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png

4. Customize your theme.

5. When you are finished customizing, create a zip archive of the 
   'newtheme' folder.

6. Upload the ``newtheme.zip`` in the plone theme panel.


Screenshots
===========

Diazo Framework Plone Classic Theme
-----------------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.plone/raw/master/docs/screenshot0.png
  :alt: Diazo Framework Plone Classic Theme
  :align: center


Diazo Framework Sunburst Theme
------------------------------

Layout of the site when viewed in a computer resolution:

.. image:: https://github.com/collective/diazotheme.plone/raw/master/docs/screenshot1.png
  :alt: Diazo Framework Sunburst Theme
  :align: center


Diazo Framework Sunburst Responsive Theme
-----------------------------------------

A demo of different views that show the responsive support as a reduced view for Mobile/Tablet devices look like the following:

.. image:: https://github.com/collective/diazotheme.plone/raw/master/docs/screenshot2.png
  :alt: Diazo Framework Sunburst Responsive Theme
  :align: center


Requirements
============

- From the Plone 4.1.x To the Plone 4.3 latest version (https://plone.org/download)
- The ``plone.app.theming`` package (*will be installed as a dependency of this package*)


Features
========

- Provides the diazo rules for *plonetheme.classic* theme.
- Provides the diazo rules for *plonetheme.sunburst* theme.
- Provides the diazo rules for *plonetheme.sunburst* theme with responsive supported.


Installation
============


Buildout
--------

If you are a developer, you might enjoy installing it via buildout.

For install ``diazotheme.plone`` package add it to your ``buildout`` section's 
*eggs* parameter e.g.: ::

   [buildout]
    ...
    eggs =
        ...
        diazotheme.plone


and then running ``bin/buildout``.

Or, you can add it as a dependency on your own product ``setup.py`` file: ::

    install_requires=[
        ...
        'diazotheme.plone',
    ],


Resources
=========

This package is the parent of all Plone diazo themes and 
provides rule that are practical to use in other diazo themes.

The resources of this framework can be reached through 
``/++theme++plone`` and there are placed at 
``diazotheme.plone/diazotheme/plone/`` directory with 
following resources files:

::
      
    _ classic
      Provides the resources from *plonetheme.classic*.
      _ manifest.cfg
      _ rules.xml
      
    _ sunburst
      Provides the resources from *plonetheme.sunburst*.
      _ manifest.cfg
      _ rules.xml
      
    _ responsive
      Provides the resources from *plonetheme.sunburst* theme with responsive supported.
      _ manifest.cfg
      _ rules.xml


Contribute
==========

- Issue Tracker: https://github.com/collective/diazotheme.plone/issues
- Source Code: https://github.com/collective/diazotheme.plone


License
=======

The project is licensed under the GPLv2.


Credits
-------

- Thijs Jonkman (t.jonkman at gmail dot com).


Amazing contributions
---------------------

- Leonardo J. Caballero G. aka macagua (leonardocaballero at gmail dot com).

You can find an updated list of package contributors on https://github.com/collective/diazotheme.plone/contributors

.. _`Sunburst Theme`: https://github.com/plone/plonetheme.sunburst
.. _`plonetheme.classic`: https://github.com/plone/plonetheme.classic
.. _`plonetheme.sunburst`: https://github.com/plone/plonetheme.sunburst
.. _`diazoframework.plone`: https://github.com/TH-code/diazoframework.plone
.. _`diazotheme.plone`: https://github.com/collective/diazotheme.plone
.. _`Diazo`: http://diazo.org
.. _`plone.app.theming`: https://pypi.org/project/plone.app.theming/

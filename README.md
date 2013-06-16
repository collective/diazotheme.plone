Introduction
============
This package contains diazo implementations of
[plonetheme.classic](https://github.com/plone/plonetheme.classic)
and
[plonetheme.sunburst](https://github.com/plone/plonetheme.sunburst),
to be used with theme base "(unstyled)". It also has a theme to 
responsify 
[plonetheme.sunburst](https://github.com/plone/plonetheme.sunburst) 
through diazo, to be used with theme base "Sunburst theme".


Any of the three theme folders can be used to create your own child
theme, based on 
[diazoframework.plone](https://github.com/TH-code/diazoframework.plone).
You can either wrap the theme up in a package or you can create a zip 
file of the folder and upload that to the theme panel.

How to create a child theme
---------------------------
There are two ways of creating a child theme.

### The package way
I'll not go into this too deep. You create a package structure 
(for instance through paster). You copy the theme folder you want 
to use as your theme into your theme. Rename the folder to something
suitable. Create a theme declaration in configure.zcml.

For this example, lets assume we've created a package called
diazotheme.newtheme and we've copied the 'responsive' theme in this 
package.

1. Created the diazotheme.newtheme package.
2. Copy diazotheme.plone/diazotheme/plone/responsive to
   diazotheme.newtheme/diazotheme/newtheme/responsive.
3. Rename diazotheme.newtheme/diazotheme/newtheme/responsive
   to diazotheme.newtheme/diazotheme/newtheme/static (arbitrary 
   name).
4. Add `<plone:static directory="static" name="newtheme" type="theme"/>`
   to diazotheme.newtheme/diazotheme/newtheme/configure.zcml.
5. Change the diazotheme.newtheme/diazotheme/newtheme/static/manifest.cfg
   to reflect the changes, so:

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png

       


### The zipfile way
For the zipfile way, 

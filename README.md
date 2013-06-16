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
For this example, lets assume we are creating a package called
diazotheme.newtheme and we will copy the 'responsive' theme in this 
package.

1. Created the diazotheme.newtheme package (for instance through paster).
2. Copy diazotheme.plone/diazotheme/plone/responsive to
   diazotheme.newtheme/diazotheme/newtheme/responsive.
3. Rename diazotheme.newtheme/diazotheme/newtheme/responsive
   to diazotheme.newtheme/diazotheme/newtheme/static (arbitrary 
   name).
4. Add `<plone:static directory="static" name="newtheme" type="theme"/>`  
   to diazotheme.newtheme/diazotheme/newtheme/configure.zcml.
5. Change diazotheme.newtheme/diazotheme/newtheme/static/manifest.cfg
   to reflect the changes, so:

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png

### The zipfile way
Again, lets assume we use the 'responsive' theme and we want to end up
with the 'newtheme' name.

1. Copy diazotheme.plone/diazotheme/plone/responsive to your file system.
2. Rename 'responsive' to 'newtheme' (the folder name wil become the
   theme name in the theme panel)
3. Change newtheme/manifest.cfg
   to reflect the changes, so:

        [theme]
        title = New theme
        description = Describe the new theme
        rules = /++theme++newtheme/rules.xml
        prefix = /++theme++newtheme
        doctype = <!DOCTYPE html>
        preview = preview.png

4. Customize your theme.
5. When you are finished customizing, create a zip archive of the 'newtheme'
   folder.
6. Upload the newtheme.zip in the plone theme panel.

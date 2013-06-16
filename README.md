Introduction
============
*This package is the base for creating CSS frameworks (e.g. Twitter
Bootstrap, Zurb Foundation, etc.) to be used with Diazo. They are 
useful for creating themes based on CSS frameworks. A Diazo framework 
should provide the framework resources and diazo rules to reuse and 
add to in a Diazo theme.*

How to setup a Diazo Framework
------------------------------
A framework package is set up as follows:
- **diazoframework.name**  
  I tend to use paster to create the package scaffolding. 
  - **diazoframework**
    - **name**
      - **framework**  
        This folder is registered through configure.zcml
        as the framework and will be traversable through 
        /++framework++name.
        - **resources**  
          The resources are the files you get in the framework
          zip you download. In my opinion it is best to change
          as little as possible for future upgrading of 
          the files. All changes you make here you will also 
          have to make in future versions of the framework.
        - **rules**
          CSS frameworks generally work by delivering styles
          and functionality for specific html structures.  
          The rules folder contains diazo rule snippets, that 
          mold the plone html into blocks the framework 
          expects. These rules are often a little more complex
          than the regular put my content div in that theme div
          and remold the html in a generic way.  
          The rules files can be included through XIncludes 
          into a diazotheme.
        - **preview.png**
          I like to provide a generic thumbnail for the theme
          panel.
      - **__init__.py**
      - **configure.zcml**
      - **version.txt**
    - **__init__.py**
  - **docs**
    - **HISTORY.txt**
    - **INSTALL.txt**
    - **LICENSE.GPL**
    - **LICENSE.txt**
  - **MANIFEST.in**
  - **README.md**
  - **setup.py**

.. include:: ../README.rst


==========
Header One
==========

Header Two
==========
.. |ndof| replace:: :abbr:`NDOF (N-Degrees of Freedom)`

This is |ndof| Abbreviation testing: 3D mice or :abbr:`NDOF (N-Degrees of Freedom)` devices are hardware that you can use to navigate a scene

|RST| is a little annoying to type over and over, especially
when writing about |RST| itself, and spelling out the
bicapitalized word |RST| every time isn't really necessary for
|RST| source readability.


Header Three
------------

Sections
========

.. only:: builder_html and (not singlehtml)

   .. container:: tocdescr

      .. ####################
         ### INTRODUCTION ###
         ####################
      .. container:: descr

         .. figure:: /images/tmp-image1.jpg
            :target: introduction.html

         :doc:`/introduction`
            Descrption of simulator features, supported hardware and libraries used.


      .. ####################
         ### INSTALLATION ###
         ####################
      .. container:: descr

         .. figure:: /images/tmp-image3.jpg
            :target: installation.html

         :doc:`/installation`
             Setting up the simlator, dependencies. Installing Blender with AMBF plugin.


      .. #################
         ### TUTORIALS ###
         #################
      .. container:: descr

         .. figure:: /images/tmp-image2.jpg
            :target: tutorials.html

         :doc:`/tutorials`
            Using the simulator, controlling & modeling robots, creating environments, interacting with haptic devices.


      .. #################
         ### REFERENCE ###
         #################
      .. container:: descr

         .. figure:: /images/tmp-image4.jpg
            :target: reference.html

         :doc:`/reference`
            AMBF API


      .. #################
         ### CHANGELOG ###
         #################
      .. container:: descr

         :doc:`/changelog`
             Test


      .. ###########
         ### FAQ ###
         ###########
      .. container:: descr

         :doc:`/faq`
            Frequently Asked Questions


      .. #######################
         ### TROUBLESHOOTING ###
         #######################
      .. container:: descr

         :doc:`/troubleshooting`
            Solving crashes, errors and graphics issues.


      .. ################
         ### GLOSSARY ###
         ################
      .. container:: descr

         :doc:`/glossary`
            A list of terms and definitions used in AMBF.


      .. ####################
         ### CONTRIBUTING ###
         ####################
      .. container:: descr

         :doc:`/contributing`
             Test


      .. ####################
         ### MANUAL INDEX ###
         ####################
      .. container:: descr

         :ref:`Manual Index <genindex>`
            A list of terms linked to the Glossary.



.. only:: latex or epub or singlehtml

   .. toctree::
      :maxdepth: 1

      introduction.rst
      installation.rst
      tutorials.rst
      reference.rst
      changelog.rst
      faq.rst
      troubleshooting.rst
      glossary.rst
      contributing.rst

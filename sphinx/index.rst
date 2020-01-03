.. include:: ../README.rst


==========
Header One
==========

AMBF Documentation.

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
      concepts.rst
      reference.rst
      changelog.rst
      faq.rst
      troubleshooting.rst
      glossary.rst
      contributing.rst

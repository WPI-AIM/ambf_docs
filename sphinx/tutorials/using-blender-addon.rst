Using AMBF Blender Addon
=========================

In this tutorial we will learn how to create and modify robot models in the `.ambf` format using Blender software. We will be using Blender with a dedicated addon which allows to create and modify ambf models. Please refer to the addon :ref:`installation section <install-ambf-addon>` if needed.

Install the package (or add it to your ``requirements.txt`` file):

See :doc:`Input Preference </installation/ambf-blender-addon>` for more information on configuring peripherals.

:menuselection:`File --> Recover --> Last Session`

.. list-table::
   :stub-columns: 1

   * - 3-button Mouse
     - :kbd:`LMB`
     - :kbd:`MMB`
     - :kbd:`RMB`
   * - 2-button Mouse
     - :kbd:`LMB`
     - :kbd:`Alt-LMB`
     - :kbd:`RMB`


.. seealso::

   See :doc:`Input Preference </editors/preferences/input>` for more information on configuring peripherals.

Subtitle goes here
------------------

Abbreviation testing: 3D mice or :abbr:`NDOF (N-Degrees of Freedom)` devices are hardware that you can use to navigate a scene in Blender.
Currently only devices made by 3Dconnexion are supported.
These devices allow you to explore a scene, as well as :ref:`Fly/Walk modes <3dview-fly-walk>`.

.. note::

   You can also change the default keymap and
   default hotkeys from the :doc:`Preferences </editors/preferences/input>`,
   however, this manual assumes you are using the default keymap.

Shortcuts
   Presets for the default :doc:`keymap </editors/preferences/keymap>` for Blender.
   Note that this manual assumes that you use the "Blender" keymap.

   Blender
      This is the default keymap.
      Read more about this keymap :doc:`here </interface/keymap/blender_default>`.
   Blender 2.7x
      This keymap is intended to match the last major series of Blender versions
      and is designed for people upgrading who do not want to learn the updated keymap.

Table of contents options
-------------------------

.. code:: console

    $ pip install sphinx_rtd_theme

In your ``conf.py`` file:

.. code:: python

    import sphinx_rtd_theme

    extensions = [
        ...
        'sphinx_rtd_theme',
    ]

    html_theme = "sphinx_rtd_theme"


.. note::
    Adding this theme as an extension is what enables localization of theme
    strings in your translated output. If these strings are not translated in
    your output, either we lack the localized strings for your locale, or you
    are using an old version of the theme.

Via Git or Download
-------------------

This is a simple picture below:

.. figure:: /images/kuka_base_frame_selected.png
   :scale: 50 %
   :alt: Kuka Robot and frames
   :align: center

   This is the caption of the figure (a simple paragraph).

Symlink or subtree the ``sphinx_rtd_theme/sphinx_rtd_theme`` repository into your documentation at
``docs/_themes/sphinx_rtd_theme`` then add the following two settings to your Sphinx
``conf.py`` file:

.. code:: python

    html_theme = "sphinx_rtd_theme"
    html_theme_path = ["_themes", ]

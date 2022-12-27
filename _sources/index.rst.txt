.. smpl documentation master file, created by
   sphinx-quickstart on Tue Nov 17 13:55:14 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.
=================================
|project| |version| documentation
=================================

SMPL Animations aim to be as web friendly as possible. 

.. jupyter-execute::

    from smpl_animation import animation
    from smpl import plot
    from ipywidgets import widgets
    import numpy as np

    def fta(n = 1.0):
        plot.function(lambda x : np.exp(n*np.log(x)-x),xmin = 0.1,xmax=100,tight=False,init=False)
    
    animation.interactive(fta,widgets.IntSlider(value=0,min=0,max=100),prerender=True)
 

.. jupyter-execute::

    from smpl_animation import animation
    from smpl import plot
    import numpy as np

    for a in np.linspace(0,10,200):
        plot.function(lambda x : a*x**2,xmin=0,xmax=5,init=True,tight=False)
        animation.frame()

    ani = animation.animate(interval=10,blit=True)
    ani.widget_gif()

..
   .. include:: ../../README.md
      :parser: myst_parser.sphinx_

.. toctree::
   :glob:
   :maxdepth: 3  
   :caption: Examples:

   example/*


:mod:`smpl_animation` package
===================
.. autosummary::
   :toctree: _autosummary
   :template: custom-module-template.rst
   :recursive:
   :caption: Modules:

   smpl_animation

.. toctree::
   :glob:
   :maxdepth: 3  
   :caption: Profiling:

   performance/*


.. toctree::
   :glob:
   :hidden:
   :caption: Versions:
   :maxdepth: 3

   RTD <https://smpl_animation.readthedocs.io/en/stable/>
   Stable <https://apn-pucky.github.io/smpl_animation/>
   Dev <https://apn-pucky.github.io/smpl_animation/test/>

.. toctree::
   :glob:
   :hidden:
   :caption: Links:
   :maxdepth: 3

   GitHub <https://github.com/APN-Pucky/smpl_animation>
 


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

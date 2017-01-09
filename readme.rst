Insert this somewhere... 
========================

.. contents::

.. section-numbering::



Principal structure
~~~~~~~~~~~~~~~~~~~

* Problem statement
* Theoretical background
  (detailed description of statistical methods, structure of computational environment etc.)

* Data analysis


PROBLEM STATEMENT
-----------------

* Constructing a decision tree for `Df`-species classification purposes;
* Studying relationships between environmental factors and leaves/... morphometric features;
* Estimating interspecific variability of the set of morhpometric featrues


MATERIALS AND METHODS
---------------------

Initially, source data was represented as an array, consisting of mixed type variables, quantitative and qualitative ones, that describe
the morphological featrues of six `Df`-species and environmental conditions of its collecting places. The array's shape was 589x47 (totally, 589 items were used in the analysis below).
The number of columns, i.e. 33,  accounted the number of item features, including its species, leaves/... morphological parameters etc.

Quantitative features were presented as a set of the following variables: ['L1p1l','L1p2l','W1p1l','W1p2l','L2p3l','L2p4l','W2p3l','W2p4l',
'S2p3l','S2p4l','Lkd','Wkd','OtnWLkd','Dvsh','Dosh','Lp','Dpl','Lns','Wns','Lvs','Wvs']


+----------------------------------------------+--------------------+
| Full description of numerical variables goes | here               |
+----------------------------------------------+--------------------+
| Variable abbreviation                        | Description        |
+----------------------------------------------+--------------------+
| L1p1l                                        | Variable meaning   |
+----------------------------------------------+--------------------+
| etc.                                         |                    |
+----------------------------------------------+--------------------+


A subset of qualitative features consisted of ['Dp','Dvl','Dnl','Dc','Dvns','Dnns','Dvvs','Dnvs','Сp', 'Ef'] variables, their meanings presented in the table below:

+-----------------------------------------------+-------------------+
| Full description of qualitative variables goes| here              |
+----------------------------------------------+--------------------+
| Variable abbreviation                        | Description        |
+----------------------------------------------+--------------------+
| Dp                                           | Variable meaning   |
+----------------------------------------------+--------------------+
| etc.                                         |                    |
+----------------------------------------------+--------------------+

And, finally, a subset of variables representing environmental conditions was following:

+------------------------------------------------------+-------------+
| Table of environmental variables and its descriptions|             |
+------------------------------------------------------+-------------+
| Variable abbreviation                                | Description |
+------------------------------------------------------+-------------+
| IC                                                   | Var. meaning|
+------------------------------------------------------+-------------+
| etc.                                                 |             |
+------------------------------------------------------+-------------+


Computational environment
~~~~~~~~~~~~~~~~~~~~~~~~~

As an environment for perforiming all kinds of statistical computations and data processing activities, we used built-on-top 
of the Python programming language computational ecosystem, that included: a couple of SciPy/NumPy (ref. to. scipy) packages for fast arrays handling in Python,
Scikit-Learn package (ref.to.sklearn) as a mordern machine learning toolset (we used some common data preprocessing features (scaling and qualitative features encoding), 
and implementation of the adaptive CART algorithm for decision tree building), as well Matplotlib (ref.to.matplotlib) and Seaborn (ref.to.seabornifexists) 
packages for results visualizations.


Data preparation
~~~~~~~~~~~~~~~~






REFERENCES
----------



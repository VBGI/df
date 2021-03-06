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
the morphological featrues of six `Df`-species and environmental conditions of its collecting places. The array's shape was 590x46 (totally, 589 items were used in the analysis below).
The number of columns, i.e. 46,  accounted the number of item features, including its species, leaves/... morphological parameters, as well auxiliary
parameters, which are item identifier (ID) etc.

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
| ALT                                                  | Var. meaning|
+------------------------------------------------------+-------------+
| IC etc.                                              |             |
+------------------------------------------------------+-------------+


Computational environment
~~~~~~~~~~~~~~~~~~~~~~~~~

As an environment for perforiming all kinds of statistical computations and data processing activities, we used built on top 
of the Python programming language computational ecosystem, that included: SciPy/NumPy (ref. to. scipy) packages, the couple for fast arrays handling,
Scikit-Learn package (ref.to.sklearn) as a mordern machine learning toolset (we used some common data preprocessing features (scaling and qualitative features encoding), 
and implementation of the adaptive CART algorithm for decision tree building), Pandas (ref.to.pandas project) for performing I/O operations and data cleaning,
as well Matplotlib (ref.to.matplotlib) and Seaborn (ref.to.seabornifexists)  packages for results visualization.


Data preparation
~~~~~~~~~~~~~~~~

Data preparation operations included: 1) data cleaning, 2) quantitative features scaling/shifting, 3) qualitative features encoding.
During automatic data cleaning all rows, that included not-a-number or non-existing values were removed from the dataset. The only one
item with a non-exisiting value was removed during this stage.

Scaling and shifting procedure was applied to all quantitative columns in the dataset. It consisted in removing the mean and scaling 
to unity standard deviation.

To encode qulitative features, we used one-hot encoding transform from the Scikit-Learn package. This, in turn, led to
extending the number of the data table columns related to qualitative features. 

We didn't use any of dimensinality reduction approaches, because they lead to smoothing the feature meanings, that are important 
when dealing with building taxonomic 


Decision tree building
~~~~~~~~~~~~~~~~~~~~~~


We used an optimized version of the CART algorithm implemented in the Scikit-Learn package(ref.to.sklearn) to construct 
a binary decision tree. When all the morphological features were used, we led to a quite simple tree, that exploited
the set of qualitative features only. The algorithm automatically selected a relatively small subset of morphological parameters,
that yeilded to classification tree of the followign form (see fig.1)

.. class:: no-web

   .. image:: https://raw.githubusercontent.com/vbgi/df/master/images_final/dtree_simple.png
       :alt: Decision tree built with help of the CART algo
       :width: 100%
       :align: center  
      
It is common, when constructing a decision tree, to prune it to reduce the number of its sections and size (ref.to.some lit). Moreover, 
decision tree pruning is used to avoid cassifier overfitting problem. Looking on the fig.1 we could yield, that the tree is overfitted and needed to be pruned, but that isn't the case. Due to internal structure of the dataset we obtained a perfect decision tree, that doesn't need any pruning.
It is worth noting, that we couldn't estimate classification accuracy in this case.
More precisely, if we would try to do this, classification accuracy would be 1.0, that means no misclassification cases can occur. 
A subset of qualitative features selected by the CART algorithm distinguishes the source dataset in a consistent way, with no contradictions. If we assume the dataset is representative, we don't need to make any further investigations: we have got a good decision tree,
that can be used to precisely determine `df`-species by their morphological features. 


REFERENCES
----------



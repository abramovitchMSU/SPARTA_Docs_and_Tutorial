SPARTA: Simple Program for Automated reference-based bacterial RNA-seq Transcriptome Analysis
=============================================================================================

SPARTA is a workflow aimed at analyzing single-end Illumina RNA-seq data. The software is
supported on Windows, Mac OS X, and Linux platforms. The workflow combines several tools:
Trimmomatic (read trimming/adapter removal), FastQC (read quality analysis), Bowtie 
(mapping reads to the reference genome), HTSeq (transcript/gene feature abundance counting),
and edgeR (differential gene expression analysis). Within the differential gene expression
analysis step, batch effects can be detected and the user is warned of the potential, unintended
additional variable. The analysis procedure is outlined below.

.. image:: workflowprocedure.jpg
	:align: center
	:alt: Workflow Procedure

How to get and use SPARTA:
--------------------------

**Mac Users** - :doc:`mactut`

**Windows Users** - :doc:`wintut`

**Linux Users** - :doc:`lintut`

Contents:
^^^^^^^^^
.. toctree::
   :hidden:

   faq
   mactut
   wintut
   lintut
   license
   releasenotes
   citationacknowledgements
   wishlist
   
* **Contribute:** If you would like to contribute to the project, the source code for each platform can be found in the `GitHub repository <http://www.github.com/biobenkj>`_.

* **Bugs:** If you found a bug, please have a look at the issues page and add a description (please be explicit and include error message if possible) of the bug/error.
	- `Mac OS X issues <http://www.github.com/biobenkj/SPARTA_Mac/issues>`_
	
	- `Windows issues <http://www.github.com/biobenkj/SPARTA_Windows/issues>`_
	
	- `Linux issues <http://www.github.com/biobenkj/SPARTA_Linux/issues>`_

* :doc:`faq`

* :doc:`license`

* :doc:`releasenotes`

* :doc:`Citation and Acknowledgements <citationacknowledgements>`

* :doc:`Functionality wishlist <wishlist>`

   
.. toctree::
   :maxdepth: 2


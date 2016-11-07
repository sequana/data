The **sequana_db1** database is used in the **quality_control** pipeline available in Sequana.
(see http://sequana.readthedocs.io/en/master/pipeline_quality_control.html).

Since the database is large, it is posted elsewhere on synapse website: 
https://www.synapse.org/#!Synapse:syn6171000/wiki/401433 where the database
creation is also described.

:Memory required: 8Gb
:Number of genomes: 24226


For book-keeping, the following Python code 
uses Sequana (http://sequana.readthedocs.io) to generate the database. 

The creation of the databases takes hours and requires a computer with about 25Gb of memory 
and 15Go of space disk. 

.. code-block:: python

   from sequana import KrakenBuilder
   # name of the directory will be the name of the database and 
   # can be changed later on
   kb = KrakenBuilder("viruses_bacteria_human_fungi") 
   # The list of accession number used in the database is provided in the files section
   # it contains about 24000 ENA accession numbers that will be downloaded to build the DB
   kb.run(["ena_list.txt"])              
   # This removes all FASTA files downloaded and should be called when the Kraken
   # database is built
   kb.clean_db()

The list ena_list.txt contains the ENA accession numbers used during the construction of the database and is available with the synapse page.

In this repository we also provide a file named **annotations.csv** that
contains all GI and ENA number + taxon and description found in the original
FASTA files.

The database contains (as listed in the ENA genome page) the following
categories:

- viruses
- bacteria
- organelles
- plasmids
- viroids
- achaeal viruses
- archaea
- phage 

In addition, a few fungis have been added:

- leishmania
- aspergillus
- pombe
- candida dubliniensis 
- glabrata 
- albicans
- plasmodium vivax
- Cryptococcus neoformans


The **sequana_db1** database is used in the **quality_control** pipeline available in Sequana.

(see http://sequana.readthedocs.io/en/master/pipeline_quality_control.html).

This database is a Kraken database. For book-keeping, the following Python code 
uses Sequana (http://sequana.readthedocs.io) to generate the database. 

The creation of the databases takes hours and requires a computer with about 25Gb of memory 
and 15Go of space disk. 

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

The list ena_list.txt contains the ENA accession numbers used during the construction of the database. 
It contains all viruses, bacteria, organelles, plasmids, viroids, achaeal viruses, archaea and
phage as listed in the ENA genome page. In addition, a few fungis have been added (leishmania, 
aspergillus, pombe, candida dubliniensis / glabrata / albicans, plasmodium vivax, Cryptococcus neoformans).

Due to the large file generated, we posted it on synapse: https://www.synapse.org/#!Synapse:syn6171000/wiki/401433

The list of ENA accession number is posted there as well as in this repository.

This Kraken database is a toy example. It contains 95 viruses mostly related to measles viruses.

It was generated using `sequana v0.1.5 <http://github.com/sequana/sequana>`_ using the list of ENA accession numbers
provided in this directory (toydb.txt) and created as follows::

    from sequana import KrakenBuilder   
    kb = KrakenBuilder("kraken_toy_db") # name of the final DB
    kb.run(["toydb.txt"])               # list of files with accession number as column)
    kb.clean_db()

The final DB is only 32Mb in size (uncompressed), which is convenient for testing. The whole process took about 5 minutes (mostly to download the 8Gb taxonomy database).


A more realistic DB using thousands of FASTA files would take far more time and hte final DB would be quite large.

A 4Gb kraken database called minikraken can easily be downloaded from https://ccb.jhu.edu/software/kraken/. It contains all viruses, bacteria and archaeal FASTA files from Dec. 2014.

This Kraken database is a toy example. It contains 95 viruses mostly related to measles viruses.

It was generated using `sequana v0.1.5 <http://github.com/sequana/sequana>`_ using the list of ENA accession numbers
provided in this directory (toydb.txt) and created as follows::


    from sequana import KrakenBuilder   
    kb = KrakenBuilder("kraken_toy_db")
    kb.run(["toydb.txt"])
    kb.clean_db()

The final DB is only 32Mb in size (uncompressed), which is convenient for testing.

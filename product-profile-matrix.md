Scope
-----

Scope of this profile is to create, updated and delete product information among the supply chain.

Actors
------

* *Publisher* A publishing house or an entitiy within a publishing house. (e.g. CPI)

* *Printer* Somebody who prints products. (e.g. CPI) 

* *POD Supplier* A printer which also sells items in their own name or in the name of the publisher (e.g. BOD, KNV-POD, Amazon POD)

* *Book Distributor* Somebody who stores printed books and delivers them to third parties if requested.

* *Wholeseller* Somebody who resells books (e.g. Libri, KNV)

* *Bookstore* Sobodoy who buys books from Wholeseller and sells them to consumers

* *Consumer* Sombody who buys and consumes/reads products

* *Directories* Service providers who collect all data which are relevant for selling and makes them accessable for other parties.

Identifier
----------

Every product should have a (globally) unique identifier. An identifier could be an ean (e.g. "978-3-16-148410-0") an UUID (e.g. "f05b7719-afd3-4fc9-bb23-3b56293ab92a") or an identifier containing the publishername plus an identifier (e.g. "xyz-publishing-123123")

Matrix
------

Among the supply chain the different players interchange all information necessary for their and the subsequential steps. This section describes typical parts of interchanging parties. Their might be other usecases with a different combination of parts.

The different parts might be sent in sequential requests and are identified and bound together by the unique identifier.


| Process Name  | Sender          | Receiver        | Bookblock      | Cover             | Sale information  | Ebook  | Marketing Images | Marketing Extracts |   
| ------------- | --------------- |:---------------:| --------------:| -----------------:| ------------------ |------------------- | ------------------- | ------------------- |
| Format             |              |                | PDF, PS        | PDF, PS           | Onix, JSON        | Epub, Mobi, ibooks, PDF | JPG | HTML, PDF | 
| Simple printing    | Publisher | Printer            | X | N |   | | | |
| POD                | Publisher | POD Provider       | X | N | X | | | |
| Directory supply   | Publisher | Directory          |   |   | X | ? | X | X |
| Ebook distribution | Publisher | Ebook platformt    |   |   | X | X | X | X |
| Book Distribution  | Publisher  | Book Distributor  |   |   | X |   |   |   |



? = Might be useful sometimes

X = required

N = might have several instances (e.g. several cover files per print job)

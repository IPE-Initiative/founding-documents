Scope
-----

Scope of this profile is to **create**, **update** or **delete** **product information** among the supply chain. Main use cases could be updating a catalog or an inventory.

Limitation of scope
-------------------

Not covered by this profile is ordering or printing a specific copy of a product. This includes also any billing, reporting and accounting of sales. (-> **transaction profile**).

Not covered by this profile is the way of transmission of the data. (-> **transmission profile**)

Not covered by this profile is authentification. (-> **authentification profile**)

Not covered by this profile is the discovery of services. (-> **discovery profile**)

Actors
------

* **Publisher** A publishing house or an entitiy within a publishing house. (e.g. Bertelsmann, Bonnier, [Lulu press](https://www.lulu.com/)).

* **Printer** Somebody who prints products. (e.g. CPI) or services who connect to printers (e.g. [crispy mountain](https://www.crispymtn.com/) or [cloudprinter](http://cloudprinter.com/) ). 

* **POD Supplier** A printer which also sells items in their own name or in the name of the publisher (e.g. [BOD](http://www.bod.de/), KNV-POD, Amazon POD).

* **Book Distributor** Somebody who stores printed books and delivers them to third parties if requested (e.g. KNV, Libri).

* **Wholeseller** Somebody who resells books (e.g. Libri, KNV).

* **Ebook Distributor** Platforms who distribute ebooks and their metadata to other parties. They could do this in the name of the publishing house (distribution model) or in their own name (aggegation model). (e.g. [readbox](http://www.readbox.net), [openpublishing](https://openpublishing.com), [Bookwire](https://www.bookwire.com/))

* **Bookstore** Sobodoy who buys books from Wholeseller and sells them to consumers (e.g. Thalia)

* ***Ebook platform*** Platform which sells electronic products to consumers (e.g. Kindle, Tolino, Apple-iTunes, Google Books, Ciando, ceebo). 

* **Consumer** Sombody who buys and consumes/reads products (e.g. John Doe).

* **Directories** Service providers who collect all data which are relevant for selling and makes them accessable for other parties (e.g. [VLB](https://www.vlb.de) ).

Identifier
----------

Every product should have a (globally) unique identifier. An identifier could be an EAN (e.g. "978-3-16-148410-0") an UUID (e.g. "f05b7719-afd3-4fc9-bb23-3b56293ab92a") or an identifier containing the publishername plus an identifier (e.g. "xyz-publishing-123123")

(**TBD:** Should the identifier be the same when publisher sends same product to two different parties or if party forwards product from one party to the next party? Alternatively we could use two identifiers, one which is created for each communication pair and one global for the product.)

Components
----------

* ***Bookblock*** Bookblock in printable form.

* **Cover** Cover file in a printable format. It could be the printable file for the Hardcover, Jacket, etc.

* **Printing information** All information you need to print the book. e.g. type of paper, size, radius of corner, type of binding, etc.

* **Ebook** Ebook is the electronic asset. Usually an epub (epub3/epub3) or its variants (.mobi, iBooks). 

* **Sale information** Information you need to sell your product. More or less the information which would be displayed on a storefront (e.g. title, subtitle, contributors, categories, keywords, bisac subjects, abstract, prices, sales rights).

* **Order information** Information you need to actually order a book. Like which wholeseller has it in stock.

* **Marketing information*** Might be extracts of titles, reviews, press-articles, summaries, biography of the author.

Matrix
------

Among the supply chain the different players interchange all information necessary for their and the subsequential steps. This section describes typical parts of interchanging parties. Their might be other usecases with a different combination of parts.

The different parts might be sent in sequential requests and are identified and bound together by the unique identifier.


| Process Name  | Sender          | Receiver        | Bookblock      | Cover         | Printing information    | Sale information  | Ebook  | Marketing Images | Marketing Extracts |   Order information |
| ------------- | --------------- |:---------------:| --------------:| -----------------:| ------------------:|-------------------:| -------------------:| -------------------:| -------------------:| -------------------:|
| **Format**           |              |                | **PDF, PS**       | **PDF, PS**          | **JSON, CSV** | **Onix, JSON**        | **Epub, Mobi** | **JPG** | **HTML, PDF** | **JSON, XML** |
| **Simple printing**    | *Publisher* | *Printer*            | X | N | X | (small subset to identify titles)   |  |  |  |  |
| **POD**                | *Publisher* | *POD Provider*       | X | N | X | X |   |    |  |   |
| **Directory supply**   | *Publisher* | *Directory*          |   |   |   | X | ? | X | X | X |
| **Ebook distribution** | *Publisher* | *Ebook platform*     |   |   |   |   | X | X | X | X | 
| **Book Distribution**  | *Publisher*  | *Book Distributor*  |   |   |   | X |   |   |   | X |
| **Bookstore incoming** | *Book Distribution* | *Bookstore*  |   |   |   | X |   |   |   | X |


**?** = Might be useful sometimes

**X** = required

**N** = might have several instances of the component (e.g. several cover files per print job)

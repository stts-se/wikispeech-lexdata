## Lexicon data for Norwegian

Steps taken to generate lexicon resources in this repository.

All lexicon resources here are based on publicly available resources.

NST Norwegian Bokmål pronunciation lexicon downloaded 2017-09-26

http://www.nb.no/sprakbanken/show?serial=oai%3Anb.no%3Asbr-23&lang=nb

 1. Downloaded file: http://www.nb.no/sbfil/leksikalske_databaser/leksikon/no.leksikon.tar.gz

 2. Unpacked file:

    `$ tar xzvf no.leksikon.tar.gz`

 3. Converted `nor030224NST.pron` to `nor030224NST.pron.utf8` using the following command (or similar):
    
    `$ cd 'NSTs norske leksikon/nor030224NST.pron/`

    `$ iconv -f LATIN1 -t UTF-8 nor030224NST.pron > nor030224NST.pron.utf8`

 4. Converted file to Wikispeech format using `go` package `pronlex/cmd/lexio/convert/nbNoNST2WS`:

    `$ go run nbNoNST2WS.go nor030224NST.pron.utf8 nb-no_nst-xsampa.sym nb-no_ws-sampa.sym  >| nor030224NST.pron-ws.utf8`

    (unparsable lines will be printed to stderr and discarded)

 5. Gzipped and uploaded `nor030224NST.pron-ws.utf8.gz` to git: `lexdata/nb-no/nst` 2017-09-26
 
 6. Converted to sql dump and uploaded to git: `nor030224NST.pron-ws.utf8.sql.gz` 2018-02-06

Update 2017-02-17: new line format   
Update 2017-05-29: small update (changed stress placement)   
Update 2017-09-26: removed lines with GARB tags   
Update 2017-11-14: new line format   
Update 2018-02-06: added sql dump for faster imports    
Update 2018-06-18: new sql dumps for new database schema (with comments and tags)    
Update 2018-07-03: new line format   
Update 2020-04-23: sqlite dump renamed with suffix .sqlite.sql.gz     
Update 2020-04-23: new mariadb dump with suffix to .mariadb.sql.gz   


---

Dependency: https://github.com/stts-se/pronlex

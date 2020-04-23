## Lexicon data for Czech

Lexical Corpus downloaded 2017-12-04

http://www.ujc.cas.cz/phword/

 1. Downloaded: file http://www.ujc.cas.cz/phword/czphlexcorp_29-06-16.zip

 2. Unpacked file:

     `unzip czphlexcorp_29-06-16.zip`

 3. Converted `czphlexcorp_29-06-16.csv` to Wikispeech format using `go` package `pronlex/cmd/lexio/convert/csCzPhword2W`

     `$ go run csCzPhword2WS.go czphlexcorp_29-06-16.csv cs-cz_phword.sym cs-cz_ws-sampa.sym > czphlexcorp_29-06-16-ws.utf8`

    (unparsable lines will be printed to stderr and discarded)

 5. Gzipped and uploaded `czphlexcorp_29-06-16-ws.utf8.gz` to git: `lexdata/cs-cs/phword` 2019-10-17
 
 6. Converted to sql dump and uploaded to git: `czphlexcorp_29-06-16-ws.utf8.sql.gz` 2019-10-17


Update 2020-04-23: sqlite dump renamed with suffix .sqlite.sql.gz     
Update 2020-04-23: new mariadb dump with suffix to .mariadb.sql.gz   

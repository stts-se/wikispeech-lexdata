## Lexicon data for Swedish

Steps taken to generate lexicon resources in this repository.

All lexicon resources here are based on publicly available resources.

Braxen Swedish pronunciation lexicon downloaded 2025-04-10

https://github.com/sprakbankental/braxen

 1. Downloaded file: https://github.com/sprakbankental/braxen/blob/main/dict/braxen-sv.tsv

 2. Converted file to Wikispeech format using `go` package `pronlex/cmd/lexio/convert/svSeBraxen2WS`:

    `$ go run svSeBraxen2WS.go braxen-sv.tsv sv-se_braxen-sampa.sym sv-se_ws-sampa.sym > braxen-sv-ws

    (unparsable lines will be printed to stderr and discarded)

 3. Gzipped and uploaded `braxen-sv-ws.gz` to git: `lexdata/sv-se/braxen` 2025-04-11
 
 4. Converted sqlite db to sql dumps and uploaded to git: `braxen-sv-ws.sqlite.sql.gz` + `braxen-sv-ws.mariadb.sql.gz` 2025-04-11


---

Dependency: https://github.com/stts-se/pronlex

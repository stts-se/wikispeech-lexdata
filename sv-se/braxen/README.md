## Lexicon data for Swedish

Steps taken to generate lexicon resources in this repository.

All lexicon resources here are based on publicly available resources.

Braxen Swedish pronunciation lexicon downloaded 2017-09-26

https://github.com/sprakbankental/braxen

 1. Downloaded file: https://github.com/sprakbankental/braxen/blob/main/dict/braxen-sv.tsv

 2. Converted file to Wikispeech format using `go` package `pronlex/cmd/lexio/convert/svSeBraxen2WS`:

    `$ go run svSeBraxen2WS.go braxen-sv.tsv sv-se_braxen-sampa.sym sv-se_ws-sampa.sym > braxen-sv-ws.tsv

    (unparsable lines will be printed to stderr and discarded)

 3. Gzipped and uploaded `braxen-sv-ws.tsv.gz` to git: `lexdata/sv-se/braxen` 2025-MM-DD
 
 4. Converted to sql dump and uploaded to git: `braxen-sv-ws.sql.gz` 2025-MM-DD


---

Dependency: https://github.com/stts-se/pronlex

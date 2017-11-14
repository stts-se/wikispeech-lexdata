## Lexicon data for Swedish

Steps taken to generate lexicon resources in this repository.

All lexicon resources here are based on publicly available resources.

NST Swedish pronunciation lexicon downloaded 2017-09-26

http://www.nb.no/sprakbanken/show?serial=oai%3Anb.no%3Asbr-22&lang=nb

 1. Downloaded file: http://www.nb.no/sbfil/leksikalske_databaser/leksikon/sv.leksikon.tar.gz

 2. Unpacked file:

    `$ tar xzvf sv.leksikon.tar.gz`

 3. Converted `swe030224NST.pron` to `swe030224NST.pron.utf8` using the following command (or similar):
    
    `$ cd 'NST svensk leksikon/swe030224NST.pron`

    `$ iconv -f LATIN1 -t UTF-8 swe030224NST.pron > swe030224NST.pron.utf8`

 4. Converted file to Wikispeech format using `go` package `pronlex/cmd/lexio/convert/svSeNST2WS`:

    `$ go run svSeNST2WS.go swe030224NST.pron.utf8 sv-se_nst-xsampa.sym sv-se_ws-sampa.sym > swe030224NST.pron-ws.utf8`

    (unparsable lines will be printed to stderr and discarded)

 5. Gzipped and uploaded `swe030224NST.pron-ws.utf8.gz` to git: `lexdata/sv-se/nst` 2017-09-26

Update 2016-10-28: added conversion to r-colored vowels to the svSeNST2WS.go script   
Update 2017-02-17: new line format   
Update 2017-05-29: small update (moved one instance of secondary stress)   
Update 2017-09-26: removed some roman numerals ("C" transcribed like "100", "VI" as "6", etc) [in conversion script]   
Update 2017-09-26: removed lines with GARB tags [in conversion script]   
Update 2017-11-14: new line format   

---

Dependency: https://github.com/stts-se/pronle

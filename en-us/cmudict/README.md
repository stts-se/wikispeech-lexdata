## Lexicon data for US English

Steps taken to generate lexicon resources in this repository.

All lexicon resources here are based on publicly available resources.

### CMU dict
US English lexicon downloaded 2016-09-23

http://www.speech.cs.cmu.edu/cgi-bin/cmudict

 1. Downloaded lexicon file `cmudict-0.7b`
 2. Converted `cmudict-0.7b` to `cmudict-0.7b.utf8` using the following command (or similar):
    
    `$ iconv -f LATIN1 -t UTF-8 cmudict-0.7b > cmudict-0.7b.utf8`

 3. Converted file to Wikispeech format (incl syllable boundaries) using `go` package `pronlex/cmd/lexio/convert/CMU2WS`:

    `$ go run CMU2WS.go cmudict-0.7b.utf8 en-us_cmu.sym en-us_ws-sampa.sym enu_cmu_syll.g2p > cmudict-0.7b-ws.utf8`

 4. Uploaded `cmudict-0.7b-ws.utf8` to git: `lexdata/en-us/cmudict/` 2017-05-09

Update 2017-02-17: new line format  
Update 2017-05-09: new mapper file (ws-sampa) and corrected mapping for secondary stress  
Update 2017-05-11: updated filter for stress placement, and added syllable boundaries  

N.B.! The g2p file above is found in the new git repos rb2gp: https://github.com/stts-se/rbg2p/blob/master/server/g2p_files/enu_cmu_syll.g2p


---

Dependency: https://github.com/stts-se/pronlex

# 2019-09-women-in-politics

### Preliminary Remarks

This document describes the pre-processing and exploratory analysis of the data set that is the basis of the article [Die grössten Hürden für Frauen in der Schweizer Politik](https://srf.ch/news/schweiz/wahlen-2019/wahlen-2019-die-groessten-huerden-fuer-frauen-in-der-schweizer-politik) published on srf.ch.

SRF Data attaches importance to the fact that the data pre-processing and analysis can be reproduced and checked. SRF Data believes in the principle of open data, but also open and comprehensible methods. On the other hand, it should be possible for third parties to build on this preparatory work and thus generate further evaluations or applications.  


### R-Script & Data

The preprocessing and analysis of the data was conducted in the [R project for statistical computing](https://www.r-project.org/). The RMarkdown script used to generate this document and all the resulting data can be downloaded [under this link](http://srfdata.github.io/2019-09-women-in-politics/rscript.zip). Through executing `main.Rmd`, the herein described process can be reproduced and this document can be generated. In the course of this, data from the folder `input` will be processed and results will be written to `output`. 

SRF Data uses Timo Grossenbacher's [rddj-template](https://github.com/grssnbchr/rddj-template) as the basis for its R scripts. If you have problems executing this script, it may help to study the instructions from the [rddj-template](https://github.com/grssnbchr/rddj-template). 


### GitHub

The code for the herein described process can also be freely downloaded from [https://github.com/srfdata/2019-09-women-in-politics](https://github.com/srfdata/2019-09-women-in-politics).


### License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons Lizenzvertrag" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Dataset" property="dct:title" rel="dct:type">2019-09-women-in-politics</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/srfdata/2019-09-women-in-politics" property="cc:attributionName" rel="cc:attributionURL">SRF Data</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Namensnennung - Attribution ShareAlike 4.0 International License</a>.


### Other projects

Code and data by [SRF Data](https://srf.ch/data) are available on [https://srfdata.github.io](https://srfdata.github.io).


### Disclaimer

The published information has been carefully compiled, but does not claim to be up-to-date, complete or correct. No liability is assumed for damages arising from the use of this script or the information drawn from it. This also applies to contents of third parties which are accessible via this offer.


### Data description of output files 

#### `candidates_per_gender_per_year.csv`

| Attribute | Type | Description |
|-------|------|-----------------------------------------------------------------------------|
| year | Number | Year of measurement |
| category | Enum | Either "running" or "elected" |
| share | Number | Share of women as decimal |

#### `candidates_per_gender_per_party_and_year.csv`

| Attribute | Type | Description |
|-------|------|-----------------------------------------------------------------------------|
| year | Number | Year of measurement |
| category | Enum | Either "running" or "elected" |
| party | Number | Party in question |
| n | Number | Number of candidates in that canton, party, year and category |
| share | Number | Share of women as decimal |

#### `candidates_detailed.csv`

| Attribute | Type | Description |
|-------|------|-----------------------------------------------------------------------------|
| party | Number | Party in question |
| canton | Number | Canton of measurement |
| year | Number | Year of measurement |
| n | Number | Number of candidates in that canton, party and year |
| share | Number | Share of women as decimal |


### Original source

#### Data for 2019

-> `input/candidates_2019.csv`

Information about the candidates running this year was acquired by [smartvote](https://smartvote.ch). As we cannot distribute any proprietary material from them, we have reduced the columns to those necessary for this analysis: ID, name, gender, district (canton) and party. The export was done via their API on the 6th of September 2019 with 4596 unique candidates.

Partiese were simplified as follows:

- SP = SP + JUSO + JSP
- GPS = GPS + JG + JGBNW + ALG + BastA
- GLP = GLP + JGLP
- BDP = BDP + JBDP
- CVP = CVP + JCVP + CSV
- FDP = FDP + JFS + LDP + JLDP
- SVP = SVP + JSVP


#### Gender Ratios by Party and Canton and Year

-> `input/su-d-17.02.02.05.02.06.xlsx`

[Candidates running](https://www.bfs.admin.ch/bfs/de/home/statistiken/kataloge-datenbanken/tabellen.assetdetail.284079.html) provided by the Federal Statistical Office.

-> `input/je-d-17.02.02.02.01.02.xlsx`

[Candidates elected](https://www.bfs.admin.ch/bfs/de/home/statistiken/kataloge-datenbanken/tabellen.assetdetail.217221.html) provided by the Federal Statistical Office.

# Public datasets

author: Ji Huang

date: 2019-04-09

last modified date: 2020-02-06

---

This is my dataset repository that are publicly available. Most of these are tables that I constantly refer to. If interested, you can used **[readr](https://readr.tidyverse.org/index.html)** package to retrieve it from Github.

To read a table in R directly, *Copy link address* by right clicking the *Download* button. Then `readr::read_tsv(coply_link)` in R.

![Imgur](https://i.imgur.com/PWbrdo9.png)

PS: FTP links are not rendered correctly in Github. Please go to the `md` file to find out.

---

1. **RAPDB_MSU_ID_conversion_20190411.txt.bz2**. For convert rice gene IDs from RAPDB to MSU7 and vice versa. Refer to [my post](https://jhuang.netlify.com/post/rice-rapdb-to-msu7-id-conversion/) on how I got this table.

```r
readr::read_tsv("https://github.com/timedreamer/public_dataset/raw/master/RAPDB_MSU_ID_conversion_20190411.txt.gz")
```

| rapdb        	| msu7           	|
|--------------	|----------------	|
| Os01g0100100 	| LOC_Os01g01010 	|
| Os01g0100200 	| LOC_Os01g01019 	|


2. **rice_annotation_rapdb_msu7_20190412.txt.bz2**. This table includes rice gene annotation from RAPDB and MSU. RAPDB annotation was downloaded from [*Gene annotation information in tab-delimited text format*](https://rapdb.dna.affrc.go.jp/download/irgsp1.html); MSU7 annotation was from [its website](http://rice.plantbiology.msu.edu/pub/data/Eukaryotic_Projects/o_sativa/annotation_dbs/pseudomolecules/version_7.0/all.dir/). I kept some useful columns and renamed the column names. There are **5339** RAPDB genes have more than one transcripts. All columns are from RAPDB except `msu7` and `msu7_annotation`.

```r
readr::read_tsv("https://github.com/timedreamer/public_dataset/raw/master/rice_annotation_rapdb_msu7_20190412.txt.gz")
```

| rapdb        	| transcript      	| description                           	| msu7           	| msu7_annotation                          	| oryzabase_synonym 	| oryzabase_name 	| transcript_evidence                   	| orf_evidence     	| flcDNA_cloneID 	|
|--------------	|-----------------	|---------------------------------------	|----------------	|------------------------------------------	|-------------------	|----------------	|---------------------------------------	|------------------	|----------------	|
| Os01g0100100 	| Os01t0100100-01 	| RabGAP/TBC domain containing protein. 	| LOC_Os01g01010 	| TBC domain containing protein, expressed 	| NA                	| NA             	| AK242339 (DDBJ, antisense transcript) 	| Q655M0 (UniProt) 	| J075199P03     	|
| Os01g0100100 	| Os01t0100100-01 	| RabGAP/TBC domain containing protein. 	| LOC_Os01g01010 	| TBC domain containing protein, expressed 	| NA                	| NA             	| AK242339 (DDBJ, antisense transcript) 	| Q655M0 (UniProt) 	| J075199P03     	|


3. **ptfdb_maizeTF_list_orgainzed_v4.txt.gz**. This is a list of *Transcriptional Factors* from [Plant TFDB](http://planttfdb.cbi.pku.edu.cn/download.php#oid_tfid). The original IDs was v3. I added the v4 IDs.

```r
readr::read_tsv("https://github.com/timedreamer/public_dataset/raw/master/ptfdb_maizeTF_list_orgainzed_v4.txt.gz")
```

| v3id             	| type 	| v4id           	|
|------------------	|------	|----------------	|
| AC149475.2_FG005 	| C2H2 	| Zm00001d048404 	|
| AC149818.2_FG008 	| C2H2 	| Zm00001d048400 	|
| AC149818.2_FG009 	| LBD  	| Zm00001d048401 	|

4. **maize_v3Tov4_function.tsv.gz**. This table has both maize v3 to v4 id mapping and v4 functions. Both came from GRAMENE and I combined them together.

	+ B73v4.gene_function.txt. Contains maize [gene short description] based on Gramene, [ftp link here](ftp://ftp.gramene.org/pub/gramene/archives/PAST_RELEASES/release-58/gff3/zea_mays/gene_function/B73v4.gene_function.txt).

	+ maize.v3TOv4.geneIDhistory.txt. Contains maize gene version 3 to version 4 conversion, [ftp link here](ftp://ftp.gramene.org/pub/gramene/archives/PAST_RELEASES/release-58/gff3/zea_mays/gene_id_mapping_v3_to_v4/maize.v3TOv4.geneIDhistory.txt).

```r
readr::read_tsv("https://github.com/timedreamer/public_dataset/raw/master/maize_v3Tov4_function.tsv.gz")
```

| v3id             	| v4id           	| changes                       	| method                   	| type   	| annotation                    	| source           	|
|------------------	|----------------	|-------------------------------	|--------------------------	|--------	|-------------------------------	|------------------	|
| AC148152.3_FG001 	| Zm00001d007725 	| No_change_in_genomic_sequence 	| Gene_Tree/Direct_mapping 	| 1-to-1 	| Ankyrin repeat family protein 	| [source:homolog] 	|

5. **maizeTF_grassius_v4id_20190904.tsv.gz**. This table has both the v3 id and v4 id for Maize Grassius TF plasmids.

**Plate Address**|**Stock number**|**GenBank accession**|**Gene model**|**Transcript**|**Template**|**type**|**v4id**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
OSU\_P\_1\_A1|pUT4010|KJ727026|GRMZM2G122614|GRMZM2G122614\_T01|Synthetic|ARF|Zm00001d003011
OSU\_P\_1\_B1|pUT4013|KJ727027|GRMZM2G121111|GRMZM2G121111\_T01|Synthetic|MYB\_related|Zm00001d024809


6. **Ath_TF_list.txt**. This is the Arabidopsis TF genes based on [PlantTFDB](http://planttfdb.cbi.pku.edu.cn/download.php). This file was downloaded on 2020-02-06.

```r
readr::read_tsv("https://raw.githubusercontent.com/timedreamer/public_dataset/master/Ath_TF_list.txt")
```

| TF_ID       | Gene_ID   | Family |
|-------------|-----------|--------|
| AT3G25730.1 | AT3G25730 | RAV    |
| AT1G68840.1 | AT1G68840 | RAV    |
| AT1G68840.2 | AT1G68840 | RAV    |


7. **ptfdb-grassius_maizeTF_list_orgainzed_v4.txt**. This is the combined maize TF list from PlantTFDB and Grassius.

```r
readr::read_tsv("https://raw.githubusercontent.com/timedreamer/public_dataset/master/ptfdb-grassius_maizeTF_list_orgainzed_v4.txt")
```

| v3id          | name    | type     | v4id           |
|---------------|---------|----------|----------------|
| GRMZM2G048582 | ZmNLP17 | Nin-like | Zm00001d006293 |
| GRMZM2G130374 | ZmWRKY3 | WRKY     | Zm00001d030969 |
| GRMZM2G398506 | ZmWRKY1 | WRKY     | Zm00001d021947 |

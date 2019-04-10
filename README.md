# Public datasets

author: Ji Huang

date: 2019-04-09

last modified date: 2019-04-09


This is my dataset repository that are publicly available. Most of these are tables that I constantly refer to. If interested, you can used **[readr](https://readr.tidyverse.org/index.html)** package to retrieve it from Github.

To read a table in R directly, *Copy link address* by right clicking the *Download* button. Then `readr::read_tsv(coply_link)` in R.

![Imgur](https://i.imgur.com/PWbrdo9.png)

PS: FTP links are not rendered correctly in Github. Please go to the `md` file to find out.


1. **RAPDB_MSU_ID_conversion_20190403.txt.gz**. For convert rice gene IDs from RAPDB to MSU7 and vice versa. Refer to [my post](https://jhuang.netlify.com/post/rice-rapdb-to-msu7-id-conversion/) on how I got this table.

| RAPDB        	| MSU7           	|
|--------------	|----------------	|
| Os01g0100100 	| LOC_Os01g01010 	|
| Os01g0100200 	| LOC_Os01g01019 	|
| Os01g0100300 	| None           	|


2. **IRGSP-1.0_representative_annotation_2019-03-22_jhuang.tsv.gz**. This table includes rice gene annotation from RAPDB. It can be downloaded from [*Gene annotation information in tab-delimited text format*](https://rapdb.dna.affrc.go.jp/download/irgsp1.html). I kept some useful columns and renamed the column names. There are **5339** genes have more than one transcripts, so there are multiple rows for these genes.


| Transcript_ID   	| Locus_ID     	| Description                                	| Oryzabase_synonym                     	| Oryzabase_name   	| Transcript_evidence 	| ORF_evidence 	| FLcDNA_cloneID 	|
|-----------------	|--------------	|--------------------------------------------	|---------------------------------------	|------------------	|---------------------	|--------------	|----------------	|
| Os01t0100100-01 	| Os01g0100100 	| RabGAP/TBC domain containing protein.      	| AK242339 (DDBJ, antisense transcript) 	| Q655M0 (UniProt) 	| J075199P03          	|              	|                	|
| Os01t0100200-01 	| Os01g0100200 	| Conserved hypothetical protein.            	| AK059894 (DDBJ, Best hit)             	| B8ACR2 (UniProt) 	| 006-208-E01         	|              	|                	|
| Os01t0100300-00 	| Os01g0100300 	| Cytochrome P450 domain containing protein. 	| AK365211 (DDBJ)                       	| B9EYQ3 (UniProt) 	|                     	|              	|                	|

3. **ptfdb_maizeTF_list_orgainzed_v4.txt.gz**. This is a list of *Transcriptional Factors* from [Plant TFDB](http://planttfdb.cbi.pku.edu.cn/download.php#oid_tfid). The original IDs was v3. I added the v4 IDs.

| v3id             	| type 	| v4id           	|
|------------------	|------	|----------------	|
| AC149475.2_FG005 	| C2H2 	| Zm00001d048404 	|
| AC149818.2_FG008 	| C2H2 	| Zm00001d048400 	|
| AC149818.2_FG009 	| LBD  	| Zm00001d048401 	|

4. **maize_v3Tov4_function.tsv.gz**. This table has both maize v3 to v4 id mapping and v4 functions. Both came from GRAMENE and I combined them together.

	+ B73v4.gene_function.txt. Contains maize [gene short description] based on Gramene, [ftp link here](ftp://ftp.gramene.org/pub/gramene/archives/PAST_RELEASES/release-58/gff3/zea_mays/gene_function/B73v4.gene_function.txt).

	+ maize.v3TOv4.geneIDhistory.txt. Contains maize gene version 3 to version 4 conversion, [ftp link here](ftp://ftp.gramene.org/pub/gramene/archives/PAST_RELEASES/release-58/gff3/zea_mays/gene_id_mapping_v3_to_v4/maize.v3TOv4.geneIDhistory.txt).

| v3id             	| v4id           	| changes                       	| method                   	| type   	| annotation                    	| source           	|
|------------------	|----------------	|-------------------------------	|--------------------------	|--------	|-------------------------------	|------------------	|
| AC148152.3_FG001 	| Zm00001d007725 	| No_change_in_genomic_sequence 	| Gene_Tree/Direct_mapping 	| 1-to-1 	| Ankyrin repeat family protein 	| [source:homolog] 	|




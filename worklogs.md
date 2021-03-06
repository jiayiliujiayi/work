#### worklogs  :book:

**general**

- [x] summarize scripts: plot cnv using complexheatmap R3.4 (input "nferCNV.obs.txt" and "dendrongram.txt" (call phylogram::read.dendrogram) from R3.6 in .sif)
  ~~- [ ] or try Infercnv&complexheatmap in singluarity container? %after the container is done~~ notes: better not wrap two functions into one: gotta check the prelim cna & confirm the annotations before plotting  
- [x] add gather scripts (ref: zhaoproject folder)

------
### legacy

#### BRST004  

- [x] QC
- [x] CNV
- [x] variants

- normal
  - immune
    - [x] immclassifier
    - [x] prepare immune counts
    - [x] ~~ask Xuan to run ImmClass~~ used singleR instead because its annotations matches up better with the immune marker levels.  
- cancer phenotypes
  - [x] Pareto  
  - [x] stat test on RTK among cancer clusters  ~~(consensus clustering on jeff's way)~~ _notes: jeff done consensus clustering, the number of "real" clusterrs are as did_
- cancer genotypes
  - [x] pyclone

#### BRST006  

- [x] QC
- [x] CNV
- [x] variants

- normal
  - immune
    - [x] immclassifier
    - [x] prepare immune counts
    - [x] ask Xuan to run ImmClass _notes: done in the /data/pub/BRST***ImmClass_
- cancer phenotypes
  - [x] Pareto
- cancer genotypes 
  - [x] pyclone

#### BRST007  

- [x] QC
- [x] CNV
- [x] variants

- rm doublets? try [scrublet](https://github.com/AllonKleinLab/scrublet) ( ~~how to confirm there are doublets??~~)
- seperate cancer from normal
  - [x] wait for xuan's infercnv regression results to differ cancer from normal _notes: Xuan says ~~it'll be done tmr~~ she did a session on ~3k cells subset, hopefully finished by the end of tmr_ // _notes: finished today, seems better then the "cell type unregressed" version, we're trying another session with epithelial cells (annotated by SingleR) included in the counts, then:_ 
    - [x] discuss with jeff.  _notes: agreed on "the hclust 1 & 3 as cancers"_
  - [x] infercnv sessions: "chr_exclude = NULL" to include ChrX
    - [x] "ref = random macro & fibro" (running@uni:tmux) ~~_notes: forgot to clear caches:(( rerunning it now_~~
    - [x] "ref = fibroblasts" (running@uni: tmux) ~~_notes: forgot to clear caches:(( rerunning it now_~~
      - [x] finish the session
      - [x] ~~update the hm with "chrX" shown~~ wait for Xuan's results then update the hm
    - [x] send jeff: Xuan's data: annotated by 1. dendrogram from the original plot, 2. singler annotations, and 3. cancer+singler annotations
  - [x] try tsne on the high quality cells (running@velo:tmux; hv been running for ~48h; talked abt this with jeff, updated some files and now running in another session in another tmux)
    - [x] send jeff the network.pdf
    - [x] error from the  new tsne module reported
    - [x] plot labeled by SampleIDs or infercnv hclusts. _notes: similar to the umap clusters: macrophages too close to epithelials_
  - [x] locate filtered umap &rarr; not found... 
    - [x] redo umap on the "filtered" ones
  - [x] check PTPRC levels in the annotated "cancer"s &rarr; ~5% of which are PTPRC+
  - [x] check PTPRC levels in the annotated 'normal's &rarr; same distribution as the cancers on the density plot (.../coh062/../0.1checkMarkers)
  - [x] plot cnv using complexheatmap (questioning cancer/normal annots, wait for the other annot from Xuan) 
- cancer genotypes
  - [x] pyclone

- combined analysis
  - [x] check if batch effects in es.ss between 004 and 6
    - [x] yes
  - [x] check QC for BRST004 or BRST006: nGenes, nReads, %mitochondria
    - [x] email jeff the results
  - [x] email jeff: raw counts umap, combat umap, cca umap
    - [x] run a umap on the concatenated raw counts
  - [x] wrap up corrections
    - [x] CCA:  
      - [x] CCA on the h.es.ss, then cluster
      - [x] CCA on counts then h.es.ss then cluster
    - [x] ref to Tran et al 2020 paper to correct _notes: tried, not as good as we thought._  
      - [x] try harmony: _velo:~/legacy/combinexxxx/cancer/harmony_demo_
            - [x] on two datasets: one with a small number of cells and the other large. ~1:5. 
            - [x] on two datasets: datapoints of two groups that are far from each other on the PCA.  
            - [x] on two datasets: one larger, one small, two far.  
    - [x] talked to jeff: 
      - [x] send CCA plots on counts
      - [x] send UMAP plots on counts respectively
    - [x] try harmony
      - [x] walkthrough (functions "cosine_" not installed)
        - [x] ~~submit github issue~~ _no responses yet_
      - [x] jeff trying subsets
      - [x] on all types of cells (immune+cancer?)
        - [x] raw counts as input
        - [x] es.ss as input
  - [x] zinbwave correction on 4 and 6 (jeff's working on zinbwave in betsy)
    - [x] zinbwave corrections
    - [x] compare before and after distribution 
    - [x] if satisfiedly corrected, then umap on the corrected one

#### BRST002

- [x] preprocessing

  - [x] rna
  - [x] premrna
  - [x] cutoffs
    - [x] 1k~10k feature, 10k~100k reads, <30 mito perc: 8.91% high quality cells
    - [x] 1k~10k feature, 2k~10k reads, <30 mito perc: 1.84%
    - [x] 1k~10k feature, 2k~100k reads, <30 mito perc: 10.76% 

- [x] compare cellranger vs kallisto _comment: generally very similar_

- [x] standard pipelines

  - [x] infercnv _comment: very unclear clusters, cannot differenciate cancer/normal cells_

    - [x] reference tried: fibroblasts, fibroblasts+hmec, fibroblasts+macrophages(annotated by singler), gtex breast, NULL 

  - [x] singler annotation _comment: hpca does not match up with blueprint_

  - [x] umap _comments: instead of clustering by cell types, cells are clustering by samples_

    _comment: questioning whether the cells are mostly normal cells_ 

  - [x] ssgsea (zinbwave corrected counts)

- [x] try tirosh copy number calling pipeline to match up with the infercnv 

  - normal
    - [x] immclassifier 

#### BRST011

- [x] standard pipelines
  - [x] infercnv _comment: very good seperation of the cell clusters_
  - [x] mutations 
  - [x] umap _comment: very good seperation of the cells clusters, mainly clustered by singler annotations_
  - [x] singler
- [x] cancer
  - [x] pareto: find the genes enriched near each vertex
- [x] normal
  - [x] immclassifier 

#### BRST013

- [x] standard pipelines

  - [x] infercnv _comment: very good seperation of the cell clusters_

  - [x] mutations

  - [x] umap 

    _comment: very good seperation of the cells clusters, mainly clustered by singler annotations_

    _comment2: epithelial cells are clustered by if they are pleural effusion cells_

    - [x] UMAP:  pleural and non pleural respectively

  - [x] singler

- [x] cancer

  - [x] pareto: find the genes enriched near each vertex

- [x] normal

  - [x] immclassifier 



#### wrapups  

- [x] patient PMH  
  - [x] 007 PMH not available
  - [x] update 007 PMH
- [x] schematic workflow
- [x] cell type table and piecharts ~~(ggplot)~~ notes: used [plotly-piecharts](https://plot.ly/r/pie-charts/) instead
- [x] check the .Key file: schematic@formalin fixation
- [x] address jeff's comments no hurry
  - [x] reform the table
  - [x] replot the pies

#### integrating all the patients

 - [x] email mark and Jeff the normal UMAP, plots, singler and immuclassifier and marker gene levels
     - [x] MACROPHAGES
           - [x] UMAP
             - [x] variable features of integrated counts
             - [x] variable features of raw counts
             - [x] macrophage markers :star: _seperates the cells best​_
             - [x] macrophage polarization 
           - [x] de on umap clusters ()
         - [x] integration
         - [x] umap
         - [x] ssgsea-z c7
         - [x] de - genes - umap
         - [x] de c7 scores -umap
 - [x] piecharts of celltypes: cancer normal types, per patient
 - [ ] update cell metadata
     - [x] original metadata
     - [x] singler annotation (hpca)
     - [x] cancer or not
     - [x] number of variants
     - [x] pattern (late bloomer or other pattern) 
     - [x] DxTime
     - [x] Event at the timpoint of Dx? eg Tx?
     - [ ] BRST013 Dx pending, asked Pat.  
 - [x] patient info
     - [x] imaging progression pending 
    - [x] update events
    - [x] update death time
 - [x] sequencing info
    - [x] update number of cells
 - [x] CCA
   	- [x] integrate 004, 6, 7, 11 and 13
   	- [x] umap the counts before CCA, send to Jeff
   	- [x] check the quality of integration
 - [x] Pareto
    - [x] send  weina specificity, sensitivity and expr _comment: sent the 3 patient cca results_
    - [x] pareto on cca integrated counts 5 patients and send jeff (final)
       - [x] diff exp among 5 archetypes and generalists
       - [x] curate 5 genesets
         - [x] by logFC/logFDR
         - [x] by selection c(0, 1)
     - [x] by variable features
     - [x] shared by variable and logfc
       - [x] ssgsea 
    - [x] heatmap of 5 geneset scores, colored patient IDs 
    - [x] heatmap of genes and cells, both colored by archetypes :star:
    - [x] discuss with jeff about next steps
       - [x] send weina: the result of this session
    - [x] curate 6 genesets from 004, 006 and 007,
       - [x] ssgsea (zinbwave corrected counts)
       - [x] correlate genesets
       - [x] correlate genesets with archetypes
    - [x] curate more genesets from 4, 6, 7, 11 and 13 _totally 24, split BRST013 by if pleural or not._
      	- [x] ssgsea (zinbwave corrected counts)
       - [x] curate shared archetypes by 3 selection methods (cca.counts, raw.counts(lcpm), )
         	- [x] ssgsea
         	- [x] archetype assignment:star:
      	- [x] correlate genesets by patient _comment: correlations are pretty consistent throughout patients_
      	- [x] cluster the genesets by patient _comment: clusters are pretty consistent throughout patients_
    - [x] curate 6 genesets from 5 patients
       - [x] ssgsea (zinbwave corrected count)
       - [x] correlate archetypes
    - [x] pareto: select the k with the lowest variance
       - [x] curate genesets: select the lowest variance per k
       - [x] gather
       - [x] ssgsea (zinbwave corrected count)
       - [x] correlate archetypes
    - [ ] pareto & group lasso
- [ ] progression patterns
    - [x] archetype (from pareto) vs progression patterns (late or normal)
    - [x] phenotype (from ssgsea scores, geneset curated from pareto on cca'd cancer counts) vs progression patterns
- [x] compare: [AWCA pam50](https://github.com/DEIB-GECO/BC_Intrinsic_subtyping) vs genefu _notes: genefu better_

------
**sscontest**

  - [x] zinbwave do ssgsea for jason zinbwave c2h  
  - [x] ask Xuan abt es.ss after zinbwave
  - [x] test zinbwave@betsy

------
**zhaoproject**

velo:/zhaoproject/jing_filter.....

- [x] draft method

------

chiproject

- [x] wrap_up: splict raw counts by the metadata (sampling in my dropbox) 

------

**misc** 

  - [x] docker on unicron _notes: done with r-base_
      - [x] run docker inside tmux
  - [x] jupyter notebook via docker,  [ref](https://www.dataquest.io/blog/docker-data-science/) (might be helpful)
  - [x] singler in singluarity r on unicron: not working -- rjags has non zero exit status
  - [x] send jeff dir to the pat1 cancer counts
  - [x] send jeff the dropbox link to the figures & tables
  - [x] es.ss de on pareto arcs
  - [x] update 02D_scRNAseq_CNV_subclone@u54
  - [x] ut training
  - [x] take pics of the figures on Xuan's desk

**scripts availability**

- infercnv: @uni: ~/***062inf\*cnv/'infercnv-scripts', call: data.table::fread
- cnv-hm with multiple annots: @velo:~/softlinktodat,jliu/***062/6.0/.ipynb
- call dendro: ref--cnv-hm

------

**error reports**

- [x] betsy tsne errors _notes: more efficient module, e.g., 21,000 genes x 11,000 cells usually took > 48h to finish.  After the update it takes 56min :))_
- [x] immclassifier error

### meeting

- ~~2020.1.15~~  
  - ~~007 pmh not available~~
- ~~2020-01-21~~
  - ~~wrap up clustering~~
  - ~~besty-tsne kinda slow?~~
- 2020-01-29
  - ~~CCA on counts (emailed), respective UMAP~~
  - ~~007 cnv reg by small sis~~
  - ~~try harmony~~
- 2020-02-05
  - ~~WES copy number~~
  - ~~pyclone results~~
  - ~~WES higher vs lower coverage compare~~

### IBP Mac crash logs

1. 2020-01-12 18:20, chrome crashed then the OS didn't respond
2. 2020-01-17 13:06, chrome crashed, tried restarting chrome but stucked at the pwd priviledging step. Then the OS didn't respond.  
3. 2020-01-24 18:35, Message didn't respond; pluged in the iPhone then Photos popped out. Then the OS didn't respond.  



###misc

- [x] immclassifier scores --> notice xuan:red_circle:
- [x] email aritro: group lasso
- [x] test diff exp
  - [x] counts _error pending, have sent jeff the email_
  - [x] ssgsea
- [x] update timekiller: 
  - [x] cor.mtest: output a matrix of p values from the cor.test
  - [x] write.gmt
- [ ] new server 129.106.31.84



Non-lab


# worklogs  :book:

**general**

- [x] summarize scripts: plot cnv using complexheatmap R3.4 (input "inferCNV.obs.txt" and "dendrongram.txt" (call phylogram::read.dendrogram) from R3.6 in .sif)
  ~~- [ ] or try Infercnv&complexheatmap in singluarity container? %after the container is done~~ notes: better not wrap two functions into one: gotta check the prelim cna & confirm the annotations before plotting  
- [x] add gather scripts (ref: zhaoproject folder)

------
**Legacy**  

- **BRST004**  
  ……  
  
  - normal
    - immune
      - [x] prepare immune counts
      - [x] ~~ask small sister to run ImmClass~~ used singleR instead because its annotations matches up better with the immune marker levels.  
  - cancer phenotypes
    - [x] Pareto  
    - [ ] stat test on RTK among cancer clusters  ~~(consensus clustering on jeff's way)~~ _notes: jeff done consensus clustering, the number of "real" clusterrs are as did_
  - cancer genotypes
    - [x] pyclone
      - [x] trying another 150x session ~4k mutations
      - [x] try higher vaf, lower others
      - [x] wrap up​
      - [x] split the svm _notes: jeff said he will solve it_
      - [x] rerun pyclone (svm sample id issue solved) and wrap up, both 50x and 150x
      - [ ] :red_circle:wrap up after svm sample id issue solved
  - misc
    - [x] ask jeff about the cancer Umap clustering scripts
      - [ ] :red_circle:run the scripts and check the clusters
    - [x] send jeff the input, scripts and output of pyclone.  
  
- **BRST006**  
  ……  
  
  - normal
    - immune
      - [x] prepare immune counts
      - [x] ask small sister to run ImmClass _notes: done in the /data/pub/BRST***ImmClass_
  - cancer phenotypes
    - [x] Pareto
      - [x] on es.ss
      - [ ] :red_circle:on counts (Seurat)
  - cancer genotypes 
    - [x] pyclone
      - [x] try another 150x session ~1k mutations
      - [x] ~~rap up​~~
      - [x] higher vaf, lower others​ _notes: results similar to 1k mutations_
      - [x] check allelfrequency
      - [x] rerun pyclone (svm sample id issue solved) 
        - [x] rerun 150x using unfiltered mutations call
        - [ ] wrap up, both 50x and 150x
  
- **BRST007**  
  ……  
  
  - rm doublets?:red_circle: try [scrublet](https://github.com/AllonKleinLab/scrublet) ( how to confirm there are doublets?? )
  - seperate cancer from normal
    - [x] wait for xuan's infercnv regression results to differ cancer from normal _notes: small sister says ~~it'll be done tmr~~ she did a session on ~3k cells subset, hopefully finished by the end of tmr_ // _notes: finished today, seems better then the "cell type unregressed" version, we're trying another session with epithelial cells (annotated by SingleR) included in the counts, then:_ 
      - [x] discuss with jeff.  _notes: agreed on "the hclust 1 & 3 as cancers"_
    - [x] infercnv sessions: "chr_exclude = NULL" to include ChrX
      - [x] "ref = random macro & fibro" (running@uni:tmux) ~~_notes: forgot to clear caches:(( rerunning it now_~~
      - [x] "ref = fibroblasts" (running@uni: tmux) ~~_notes: forgot to clear caches:(( rerunning it now_~~
        - [x] finish the session
        - [x] ~~update the hm with "chrX" shown~~ wait for small sister's results then update the hm
      - [x] send jeff: small sister's data: annotated by 1. dendrogram from the original plot, 2. singler annotations, and 3. cancer+singler annotations
    - [x] try tsne on the high quality cells (running@velo:tmux; hv been running for ~48h; talked abt this with jeff, updated some files and now running in another session in another tmux)
      - [x] send jeff the network.pdf
      - [x] error from the  new tsne module reported
      - [x] plot labeled by SampleIDs or infercnv hclusts. _notes: similar to the umap clusters: macrophages too close to epithelials_
    - [x] locate filtered umap &rarr; not found... 
      - [x] redo umap on the "filtered" ones
    - [x] check PTPRC levels in the annotated "cancer"s &rarr; ~5% of which are PTPRC+
    - [x] check PTPRC levels in the annotated 'normal's &rarr; same distribution as the cancers on the density plot (.../coh062/../0.1checkMarkers)
    - [x] plot cnv using complexheatmap (questioning cancer/normal annots, wait for the other annot from small sister) 
  - cancer phenotypes
    - [ ] cluster based
      - [x] counts --> pca --> umap _notes: cluster by samples_
      - [x] scores ==> betsy seurat umap (disp, vst) **running**
      - [x] zinbwave scores ==> betsy seurat umap (disp, vst) 
        - [x] do zinbwave
        - [ ] :red_circle:run umap
    - [ ] 
  - cancer genotypes
    - [x] pyclone
    - [ ] :red_circle: rerun pyclone​ (svm sample id issue solved), 150x _running_
    - [ ] :red_circle: wrap up​ 
  - misc
    - [ ] :red_circle: ask jeff about the cutoffs he used when presenting zinbwave norm es.ss.  
  
- **BRST002**
  
  - qc
    - [x] compare kallisto vs cellranger
    - [x] filter cells
    - [ ] filtered_umap
    - [ ] filtered SingleR annotation
    
  - [ ] split normal from cancer (infercnv) _running_
  
  - snormal
  - cancer phenotype
  - cancer genotype
  
- combined analysis
  
  - [x] check if batch effects in es.ss between 004 and 6
    
    - [x] yes
  - [x] check QC for BRST004 or BRST006: nGenes, nReads, %mitochondria
    
    - [x] email jeff the results
  - [x] email jeff: raw counts umap, combat umap, cca umap
    
    - [x] run a umap on the concatenated raw counts
  - [ ] :red_circle: wrap up corrections
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
      
    - [ ] try harmony
          - [ ] walkthrough (functions "cosine_" not installed)
            - [x] submit github issue
          - [ ] jeff trying subsets
          - [x] on all types of cells (immune+cancer?)
            - [x] raw counts as input
            - [x] es.ss as input
          
        - [x] try directy running UMAP/seurat umap/or PCA
        
          - [x] on combined ssgsea
        
            before: check
        
            - [x]  if batch effects in 004 _notes: no batch effect_
        - [x] cluster vs samples of 006 _no batch effect_
      
      - [x] try seurat umap _notes: similar to umap package_
      
      - [x] ~~​try PCA~~
      
      - [x] try on zinbwave corrected​
      
    - [x] try 6 ways of clustering (pic taken)
    
      - [x] harmony on combined cancer counts
      - [x] 5.3 counts CCA, seuratumap, all celltypes
      - [x] 5.4 counts CCA, seuratumap, all celltypes 007 included _notes: too many 007, might squeeze the cells from other pats_
          - [x] try subset 007 then run CCA
      - [ ] 5.5 pathway CCA, seuratumap, cancer+immune
      - [ ] 4 pareto
      - [ ] 8 
    
  - [x] zinbwave correction on 4 and 6 (jeff's working on zinbwave in betsy)
    - [x] zinbwave corrections
    - [x] compare before and after distribution 
    - [x] if satisfiedly corrected, then umap on the corrected one
  
- wrapups  
  - [x] patient PMH  
    - [x] 007 PMH not available
    - [x] update 007 PMH
  - [x] schematic workflow
  - [x] cell type table and piecharts ~~(ggplot)~~ notes: used [plotly-piecharts](https://plot.ly/r/pie-charts/) instead
  - [x] check the .Key file: schematic@formalin fixation
  - [ ] :red_circle: address jeff's comments no hurry
    - [ ] reform the table
    - [ ] replot the pies

------
**sscontest**

  - [x] zinbwave do ssgsea for jason zinbwave c2h  
  - [x] ask small sister abt es.ss after zinbwave
  - [x] test zinbwave@betsy

------
**zhaoproject**

velo:/zhaoproject/jing_filter.....

- [x] draft method

**zhaopdxproject**

- [x] check email
- [x] generate tables
- [x] prelim analysis

------

chiproject

- [x] wrap_up: splict raw counts by the metadata (sampling in my dropbox) 

------

**misc**  

  - [ ] docker on unicron _notes: done with r-base_
      - [ ] run docker inside tmux
  - [ ] jupyter notebook via docker,  [ref](https://www.dataquest.io/blog/docker-data-science/) (might be helpful)
  - [x] singler in singluarity r on unicron: not working -- rjags has non zero exit status
  - [x] send jeff dir to the pat1 cancer counts
  - [x] send jeff the dropbox link to the figures & tables
  - [x] es.ss de on pareto arcs
  - [x] update 02D_scRNAseq_CNV_subclone@u54
  - [x] ut training
  - [x] take pics of the figures on small sister's desk and send to her wechat
  - [x] bioinfo weekly meeting presentation @10 Feb
  - [ ] NIH Commons ID
  - [x] update betsy ssgsea commands
  - [x] update R container in .genomicoderc

**scripts availability**

- infercnv: @uni: ~/***062inf\*cnv/'infercnv-scripts', call: data.table::fread
- cnv-hm with multiple annots: @velo:~/softlinktodat,jliu/***062/6.0/.ipynb
- call dendro: ref--cnv-hm

------

**error reports**

- [x] betsy tsne errors _notes: more efficient module, e.g., 21,000 genes x 11,000 cells usually took > 48h to finish.  After the update it takes 56min :))_

#### meeting

- ~~2020.1.15~~  
  - ~~007 pmh not available~~
- ~~2020-01-21~~
  - ~~wrap up clustering~~
  - ~~besty-tsne kinda slow?~~
- 2020-01-29
  - ~~CCA on counts (emailed), respective UMAP~~
  - ~~007 cnv reg by small sis~~
  - ~~try harmony~~
- 2020-02-04
  - ~~WES copy number~~
  - ~~pyclone results~~
  - ~~WES higher vs lower coverage compare~~
- 2020-02-11
  - ~~harmony on 004 & 6 es.ss~~
  - ~~umap pkg vs seurat: variable features --> PCA --> UMAP~~
  - ~~PCA?~~
  - ~~007pyclone~~
- 2020-02-18
  - ~~wrapped up umap & seurat umap results on es.ss~~
  - ~~betsy umap on es.ss not working~~
  - ~~pyclone results on 004 and 006~~
- 2020-02-24
  - ~~pyclone higher vaf results~~
  - ~~harmony on counts (variable features ==> pea ==> tsne) not as good as #5 approach~~
  - ~~trying seurat disp umap on 007cancer h/c2, raw scores done,~~ zinbwaved scores pending
  - ~~X issuse in read.delim, show variable features from betsy pipeline~~
- 2020-03-03
  - pyclone new results, 2 pats, 2 depths
  - 002 results

##### IBP Mac crash logs

1. 2020-01-12 18:20, chrome crashed then the OS didn't respond
2. 2020-01-17 13:06, chrome crashed, tried restarting chrome but stucked at the pwd priviledging step. Then the OS didn't respond.  
3. 2020-01-24 18:35, Message didn't respond; pluged in the iPhone then Photos popped out. Then the OS didn't respond.  





Non-lab

- [x] kaming methods & scripts
  - [x] reproduce
  - [x] manuscripts
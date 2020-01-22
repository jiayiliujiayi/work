# worklogs  :book:

**general**

- [x] summarize scripts: plot cnv using complexheatmap R3.4 (input "nferCNV.obs.txt" and "dendrongram.txt" (call phylogram::read.dendrogram) from R3.6 in .sif)
  ~~- [ ] or try Infercnv&complexheatmap in singluarity container? %after the container is done~~ notes: better not wrap two functions into one: gotta check the prelim cna & confirm the annotations before plotting  
- [x] add gather scripts (ref: zhaoproject folder)

------
**Legacy**  

- BRST004  
  ……  
  - normal
    - immune
      - [x] prepare immune counts
      - [ ] ask small sister to run ImmClass
  - cancer phenotypes
    - [x] Pareto  
    - [ ] stat test on RTK among cancer clusters  (consensus clustering on jeff's way)
    - [ ] DNA analysis (WES on the way)
- BRST006  
  ……  
  - normal
    - immune
      - [x] prepare immune counts
      - [ ] ask small sister to run ImmClass
  - cancer phenotypes
    - [x] Pareto  
    - [ ] DNA analysis (WES on the way)
- BRST007  
  ……  
  - rm doublets? try [scrublet](https://github.com/AllonKleinLab/scrublet)
  - seperate cancer from normal
    - [ ] wait for xuan's infercnv regression results to differ cancer from normal _notes: small sister says ~~it'll be done tmr~~ she did a session on ~3k cells subset, hopefully finished by the end of tmr_  
    - [x] do another session of infercnv "chr_exclude = NULL, ref = random macro & fibro" (running@uni:tmux) _notes: forgot to clear caches:(( rerunning it now_
    - [x] do another session of infercnv "chr_exclude = NULL" (running@uni: tmux) _notes: forgot to clear caches:(( rerunning it now_
      - [ ] update the hm with "chrX" shown 
    - [x] try tsne on the high quality cells (running@velo:tmux; hv been running for ~48h; talked abt this with jeff, updated some files and now running in another session in another tmux)
      - [x] send jeff the network.pdf
      - [ ] plot labeled by SampleIDs or infercnv hclusts. 
    - [x] locate filtered umap &rarr; not found... 
    - [x] redo umap on the "filtered" ones
    - [x] check PTPRC levels in the annotated "cancer"s &rarr; ~5% of which are PTPRC+
    - [x] check PTPRC levels in the annotated 'normal's &rarr; same distribution as the cancers on the density plot (.../coh062/../0.1checkMarkers)
    - [x] plot cnv using complexheatmap (questioning cancer/normal annots, wait for the other annot from small sister) 
  - cancer genotypes
    - [ ] DNA analysis (check if WES)
- combined analysis
  - [x] check if batch effects in es.ss between 004 and 6
    - [x] yes
  - [ ] email jeff: raw counts umap, combat umap, cca umap
  - [ ] if yes zinbwave correction on 4 and 6 (jeff's working on zinbwave in betsy)
- wrapups  
  - [x] patient PMH  
    - [x] 007 PMH not available
    - [x] update 007 PMH
  - [x] schematic workflow
  - [x] cell type table and piecharts ~~(ggplot)~~ notes: used [plotly-piecharts](https://plot.ly/r/pie-charts/) instead
  - [X] check the .Key file: schematic@formalin fixation

------
**sscontest**

  - [x] zinbwave do ssgsea for jason zinbwave c2h  
  - [ ] ask small sister abt es.ss after zinbwave

------
**zhaoproject**

velo:/zhaoproject/jing_filter.....

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
  - [ ] es.ss de on pareto arcs

**scripts availability**

- infercnv: @uni: ~/***062inf\*cnv/'infercnv-scripts', call: data.table::fread
- cnv-hm with multiple annots: @velo:~/softlinktodat/***062/6.0/.ipynb
- call dendro: ref--cnv-hm

------

**error reports**

- [ ] betsy tsne errors

#### meeting

- ~~2020.1.15~~  
  - ~~007 pmh not available~~

- ~~2020-01-21~~
  - ~~wrap up clustering~~
  - ~~besty-tsne kinda slow?~~

##### IBP Mac crash logs

1. 2020-01-12 18:20, chrome crashed then the OS didn't respond
2. 2020-01-17 13:06, chrome crashed, tried restarting chrome but stucked at the pwd priviledging step. Then the OS didn't respond.  





Non-lab

- [ ] kaming methods & scripts
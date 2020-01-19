# worklogs  :book:

**general**

- [ ] summarize scripts: plot cnv using complexheatmap R3.4 (input "nferCNV.obs.txt" from R3.6 in .sif), 
  ~~- [ ] or try Infercnv&complexheatmap in singluarity container?~~ % after the container is done.  
- [x] add gather scripts (ref: zhaoproject folder)

------
**Legacy**  

- BRST004  
  ……  
  - [ ] Pareto  
  - [ ] stat test on RTK among cancer clusters  (consensus clustering on jeff's way)
  - [ ] DNA analysis (WES on the way)
- BRST006  
  ……  
  - [ ] Pareto  
  - [ ] DNA analysis (WES on the way)
- BRST007  
  ……  
  - [ ] wait for xuan's infercnv regression results to differ cancer from normal  
  - [ ] try tsne on the high quality cells, labeled by SampleIDs or infercnv hclusts. 
  - [x] check PTPRC levels in the annotated "cancer"s &rarr; ~5% of which are PTPRC+
  - [x] check PTPRC levels in the annotated 'normal's &rarr; same distribution as the cancers on the density plot (.../coh062/../0.1checkMarkers)
  - [ ] plot cnv using complexheatmap  
  - [ ] DNA analysis (check if WES)
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

------
**zhaoproject**

velo:/zhaoproject/jing_filtergenes

------

**misc**  

  - [ ] docker on unicron
  - [ ] jupyter notebook via docker,  [ref](https://www.dataquest.io/blog/docker-data-science/) (might be helpful)
  - [x] singler in singluarity r on unicron: not working -- rjags has non zero exit status
  - [x] send jeff dir to the pat1 cancer counts





#### meeting

~~- 2020.1.15~~  
  ~~- 007 pmh not available~~

##### IBP Mac crash logs

1. 2020-01-12 18:20, chrome crashed then the OS didn't respond
2. 2020-01-17 13:06, chrome crashed, tried restarting chrome but stucked at the pwd priviledging step. Then the OS didn't respond.  
3. 

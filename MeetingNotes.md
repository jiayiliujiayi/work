# 2022
**0501 Mon Meeting w/ Dr. Kreimer**  
- Analyses 
	- real motifs: overlapped WTs motifs: to be finished
	- nonmotifs: overlapped: to be finished; MPRA output.  
- Prediction: continue working on them

**04.26 Tue Meeting w/ Dr. Kreimer**  
- redo analyses:    
	- F(all)=0 vs all, F(all)=1 vs all, between pertX 
	- nGained and nLost comparision 
	- overlapped WTs analyses 
- predictions: ask Justin for the scripts and start working on it!  

**04.22, Fri, Meeting w/ Dr. Li**    
- manuscript:   
	- Fig1: add arrows; remove dashed boxes; DM names
	- Fig2: QQ plot: gray x=y line; try -log10p; type I error as supplementary
	- remove subsubsections
- check: under norm methods, gene variance changed?   
- check: variance vs cell number in denSNE manuscript  

**04.18 Mon Meeting w/ Dr. Li**  
- manuscript
	- finish results (effect of norm method & effect of nFeatures)
	- schematic workflow

**04.12 Tue Meeting w/ Dr. Kreimer**  
- activators/repressors:    
	- reverse the categorizing because log2FC = log2(WT/Pert). 
	- tfbs_func: 1&2 activators, 3&4 repressors
- read papers regarding MPRA and predictions

**04.08, Fri, Meeting w/ Dr. Li**    
- manuscript:   
	- add toy examples for methods part  
	- QQ plot for type I error
	- big picture: Best practices in differential variability analysis of single-cell gene expression data  
- check: under SCT, gene variance changed?   
- check: variance vs cell number in denSNE manuscript  

**04.05 Tue Meeting w/ Dr. Kreimer**  
- activators/repressors: add "filter" (F1-F4) criterias
- for pertX, wilcox test on:
	- positive
	- negative
	- overall
	- (also considering filters)
- add n_gained vs n_lost to slides
- discussion about joining the lab

**04.01, Fri, Meeting w/ Dr. Li**    
- manuscript:   
	- focus on same cell number scenarios  
	- add toy examples for methods part  
	- big picture: evaluation  
- Check: under SCT, gene variance changed?   
- check: variance vs cell number in denSNE manuscript   

**03.29 Tue Meeting w/ Dr. Kreimer**  
- For the perturbed/not perturbed motifs, check if they have 
 overlapped/not overlapped identical motifs  
- what does each F mean?   
- what does Filt mean?   
- gained/lost motifs: activators or repressors?   
- delta $nMotif_{pert - WT}$ --> positive or negative?   

**03.25 Meeting w/ Dr. Li**  
- should keep an eye on Type I Errors  
- Todo  
	- Try different cell number scenario:   
		- condition 1: 100cells/type
		- condition 2: 100-1000cells/type
	- Update manuscripts

**03.24 Meeting w/ Dr. Kreimer**
- Fisher's test for subgroups? 
	- crosstable, chi-square? 
- add raw numbers of motifs
- Wilcox on F=0 motifs
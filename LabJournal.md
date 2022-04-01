#### Lab Journal  :book:

# 2022
**03.31, Thu**     
#scRNA-SeqVariability   
- updated manuscript until the SCT part
#AssessPertX 
- updated 

**03.30, Wed**     
#scRNA-SeqVariability     
- updated manuscript until the SCT part  
#AssessPertX   
- updated the successful/unsuccessful props, perturbed/not perturbed props, and overlapped/not overlapped props  
	- found a mistake: "Perturbed or not" should be the reversed of "contain_Identical.PertX.MotifIDs.in.sequence"  
	- now is fixed  
  
**03.29, Tue**    
#scRNA-SeqVariability   
- finished different cell numbers/type  -- all methods finished
	- methods: 3, 7, 9, 11, 16 
- MWW test finished

**03.28, Mon**    
#AssessPertX 
- continue adding plots showing both motif numbers and statistics
#scRNA-SeqVariability   
- finished different cell numbers/type  
	- methods: 13

**03.27**  
#scRNA-SeqVariability   
- finished different cell numbers/type  
	- methods: 1, 12, 14, 15  
#AssessPertX   
- [slides](https://docs.google.com/presentation/d/18T4jBtUAEKMg5_3sEeDKXSYLtdkPW_xXHf8G7wzn5NU/edit?usp=sharing)  
	- add plots showing both motif numbers and statistics (havent' finished)  
	- substitute Fisher's exact tests with Chi square tests  

**03.26**  
#scRNA-SeqVariability   
- calculating affinities for scenarios of different cell numbers/type: 
	- condition 1: 100 cells/type; condition2: 100-1000 cells/type
	- methods: 1, 3, 7, 9, 11, 12, 13, 14, 15, 16
- manuscript: finished simulation part

**03.22**  
#AssessPertX  
- [flowchart of categorizing](https://drive.google.com/file/d/1zxn8tRwU6WUHjsGodA8C1ODszrlgak7J/view?usp=sharing)

**03.18**  
#scRNA-SeqVariability 
- method1 needs high RAM, set as 400G, with 5 cores
- tried installing glmGamPoi
	- Error: zlib.h not defined when installing XVector #bug 
		- Solution: manually define path of zlib.h to $HOME/miniconda3
			1. in source code of XVector
			2. in ./src/io_utils.c, line 16: include{zlib.h}
			3. change zlib.h to absolute path of zlib.h
			4. re-tar source code and install package from source #debug
	- Error: "cannot find -lz" #bug 

**03.17**  
#scRNA-SeqVariability  
- "connection error" when using mclapply #debug #bug
	- solutions: 
		1. using absolute paths
		2. setwd() before writing out files
		3. alwayse setwd() before sourcing scripts
- revised Rscritps of methods1-14 to avoid duplicating calculations
	- check available files: list.files(..., recursive = T)
	- get not available fils: not.avail = 1:1000 %>% .\[!.  %in% avail.files\]
	- lapply only on not.avail files
- adequate job configs for methods.job (avoid long queues)
	- nCPU <= 10, best <=8
	- mem <=500G, best <= 200G
- method13, 100cell/type, batch303: #bug
	- submit issue to github
	- answer from developer: install package glmGamPoi

**03.16**  
#scRNA-SeqVariability  
- Revised .jobs of method
	- partition=mem --> less queueing
	- more CPUs
	- larger RAM
- waiting for the methodN.job to finish



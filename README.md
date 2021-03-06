#### SUPER-FOCUS 0.28: A tool for agile functional analysis of shotgun metagenomic data
(c) Silva, G. G. Z., Green K., B. E. Dutilh, and R. A. Edwards: 
		SUPER-FOCUS: A tool for agile functional analysis of shotgun metagenomic data. Bioinformatics. 2015 Oct 9. pii: btv584. website: https://edwards.sdsu.edu/SUPERFOCUS


#### DOWNLOAD DATABASE

Program: superfocus__downloadDB.py: Downloads and formats the SUPER_FOCUS database for the available aligners
#### (1) Usage

python superfocus__downloadDB.py aligner

###### Example: 
	python superfocus__downloadDB.py rapsearch blast diamond


You may choose as many aligners as you want among the three, as long as they are installed.

#### (2) Recommendations
- RAPSearch2 and DIAMOND don't work properly using a already formatted database with a newer version of the aligner. Thus, please re-run 'superfocus__downloadDB.py' in the case of any aligner was updated in the 
	  system.


#### (1) SUPER-FOCUS Usage

superfocus.py: SUPER-FOCUS main program

#### Options:

	-h print help
	
	-q FASTA/FASTQ
		query file (FASTA or FASTQ format) or folder with multiple FASTA/FASTQ files when -m 1

	-dir string
		output directory

	-o string
		project name (default 'my_project')
	
	-mi float
		minimum identity (default 60 %)

	-ml int
		minimum alignment (amino acids) (default: 15)

	-focus int
		runs FOCUS; 1 does run; 0 does not run: default 0

	-t int
		number of threads (default 8	)

	-e float
		e-value (default 0.00001)

	-db string
		database (DB_90, DB_95, DB_98, or DB_100; default DB_98)

	-p int
		amino acid input; 0 nucleotides; 1 amino acids (default 0)
		
	-k int
		keep original tabular output. 0 delete it / 1 keep it (default 0)

	-a string
		aligner choice (rapsearch, blast (only fasta files), diamond; default rapsearch)

	-fast int
		runs RAPSearch2 or DIAMOND on fast mode - 0 (False) / 1 (True) (default: 1)	
  
	-n int
		normalizes each query counts based on number of hits; 0 doesn't normalize; 1 normalizes (default: 1)

	-r string
		use only the subsystems in the organisms predicted by "-focus"– ncbi / rast annotation  (default: ncbi)
		
#### Example
	python superfocus.py -q query.fasta -dir myOutputdirectory
	 
#### (2) Output
SUPER-FOCUS output will be add the folder selected in -dir

#### (3) Plotting output
Please read https://github.com/metageni/SUPER-FOCUS/tree/master/plotting_output for plotting your output

#### (4) Recommendations
- The FOCUS reduction is not necessary if not wanted (set -focus 0)
- Run RAPSearch for short sequences. it is less sensitive for long sequences
- How BLAST if you want the result to be the most sensitive as possible
- Only use DIAMOND for large datasets. It is slower than blastx for small datasets

#### (5) Dependencies
- Python >= 2.6.X < 3.Y: http://www.python.org/download
- Jellyfish: http://www.cbcb.umd.edu/software/jellyfish
- Numpy: http://sourceforge.net/projects/numpy/files/NumPy
- SciPy: http://sourceforge.net/projects/scipy

#### One of the below aligners:
- RAPSearch2: http://rapsearch2.sourceforge.net
- DIAMOND: http://ab.inf.uni-tuebingen.de/software/diamond
- BLAST: ftp://ftp.ncbi.nlm.nih.gov/blast/executables/blast+/LATEST

##### COPYRIGHT AND LICENSE

Copyright (C) 2014-2017  Genivaldo Gueiros Z. Silva

This program is free software: you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE.  See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
this program.  If not, see <http://www.gnu.org/licenses/>.

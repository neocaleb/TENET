TENET

Dependency

openmpi

JPype

Usage

./AllinOneRun.sh [expression_file_name] [number_of_threads] [trajectory_file_name] [cell_select_file_name]

Input 

1. expression_file - a csv file with N cells in the rows and M genes in the columns (same format with wishbone pseudotime package [1]).

example

	GENE_1	GENE_2	GENE_3	...	GENE_M

CELL_1	

CELL_2

CELL_3

.
.
.

CELL_N

2. trajectory_file - a text file of pseudotime data with N time points in the same order as the N cells of the expression file.

example

0.098
0.040
0.023
.
.
.
0.565

3. cell_select_file - a text file of cell selection data with N Boolean (1 for select and 0 for non-select) data in the same order as the N cells of the expression file.

example

1
1
0
.
.
.
1

Output

TE_result_matrix.txt - TEij, M genes x M genes matrix representing the causal relationship from GENEi to GENEj.

example

TE	GENE_1	GENE_2	GENE_3	...	GENE_M
GENE_1	0	0.05	0.02	...	0.004
GENE_2	0.01	0	0.04	...	0.12
GENE_3	0.003	0.003	0	...	0.001
.
.
.
GENE_M	0.34	0.012	0.032	...	0

# PepDockDove
Peptide structure prediction with **PepFlow** and do docking by **MEGADOCK**.   
Finally rerank the outputs by **GNN_DOVE**

## Usage
Clone pepflow, MEGADOCK, GNN_DOVE in the same directory and this code.   

### Directory Example
**Workspace**   
|_ GNN_DOVE   
|_ MEGADOCK   
|_ pepflow   
|_ pepdockdove.py   


### Run PepDockDove
''' Python
python3 ./pepdockdove.py -s [peptide_sequence] -r [receptor_path] -m [num_models] -d [num_decoys] -o [output_dir]
'''

You must input the sequence and the receptor path. Other parameters are not necessary. The number of models is 100 by default, and decoy is 1000.
**Pepflow's chunck is set in 10, so you must set the num_models >= 10**

## Output
Predicted models are saved in **/your/path/models** and decoys are saved in **/your/path/decoys**.

### Directory
**PMD_output**
|_ decoys   
    |_ {sequence}_1   
        |_ ligands   
            |_ {sequence}_1.1.pdb   
            |_ ...   
            |_ {sequence}_1.{num_decoys}.pdb   
        |_ {sequence}_1.decoy_1.pdb   
        |_ ...   
        |_ {sequence}_1.decoy_{num_decoys}.pdb   
    |_ ...   
    |_ {sequence}_{num_decoys}   
        |_ ...   
|_ models   
    |_ {sequence}_1.pdb   
    |_ ...   
    |_ {sequence}_{num_models}.pdb   

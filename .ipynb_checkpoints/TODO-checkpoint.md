
# :calendar: Todos 

- [ ] Run baseline models as comparison for the chosen combined_score_thresh
    - [ ] Predicting the mean
    - [ ] Regression
    - [ ] MLP
    - [ ] Random Forest 
    - [ ] SVM
- [x] Compare predicted with observed ic50 values for each model on the test set
- [ ] For the cell-GNN try and monitor multiple architecture
    - [x] `GCNConv` vs `GATConv`
    - [x] implement `global_mean_pool` vs `global_max_pool`
    - [ ] run `global_mean_pool` vs `global_max_pool`
    - [ ] Number of GNN layers (hops)
    - [ ] Choice of `combined_score_thresh` and therefore the number of genes in the graph
- [ ] Find cell-line drug tuples which have been removed in the processing and predict the ic50 values for them. 
    - compare these predictions with the observed ic50s. This means predicting missing drug-response values.    
- [ ] Calculate the average predicted ic50 values for each drug. Choose the top 10 and bottom 10 drugs.
- [ ] Run crossvalidation and choose for example 10 different random seeds. Monitor average performance over set of seeds.
    - [x] Put the random seed in final `.pth` files name
- [x] Check other performance metric [spearmanr](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.spearmanr.html)
- [ ] Implement BayesianOptimization to tune hyperparameters:
    - __hyperparams__:
        - `combined_score_thresh` (this will be visualised after the hypertuning)
        - `learning rate`
        - `dropout`
        - `number of cell GNN layers`
        - `number of drug GNN layers`
        - `type of cell GNN layer`
        
        
        
        
GraphTab
--> GATConv - 2

        
conv_type = {GATConv, GCNConv}
num_conv_layers = {2,3,4}

GATConv - 2 
-> 


        
90% 10%
1 mal
train 80 
val 80
 
train.  val 
___ ___ ___
train val train 

      
train , validation , test 

1st appraoch
------------
10 * 2,5 h * 5 = 5 days
- holdout in inner train-val loop
    - best params train on train U val --> test on test
    - iterate 5-times with different test sets
- plus early stopping 

2nd approach
------------
- holdout in inner train-val loop
    - best params train on train U val --> test on test
- optimize on train U val
- plus early stopping

optimal_params --> over combined_thresh in {850, 900, 950, 990}


- performance per cell-line --> mu, sigma
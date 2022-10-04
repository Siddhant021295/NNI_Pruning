# NNI_Pruning

## How to run the code 

- Create an conda environment using the requirement.txt
- conda activate PRUN
- Run the python3 NNI_Pruning.py

## what happend in the code.

- First the code trains a network with MNIST data.
- Then we save the model pth file for further comparision with the pruned model.
- Then we load the model again and prune it using 2 different pruning methods L1NormPruner and FPGMPruner and 2 different configuration.
- The result are as follows :
  - Orignal Model:
    
    ![Screen Shot 2022-10-04 at 3 46 52 PM](https://user-images.githubusercontent.com/22122136/193911940-b9c9ba69-b530-4175-bf3e-e3f37b337e00.png)
  - Pruning with N1NormPruner:
    
    ![Screen Shot 2022-10-04 at 12 40 06 PM](https://user-images.githubusercontent.com/22122136/193909846-d34a5ffc-4eeb-4995-bf65-21b5eb168bf5.png)
  - Pruning with N1NormPruner:
    
    ![Screen Shot 2022-10-04 at 12 42 35 PM](https://user-images.githubusercontent.com/22122136/193909881-4332871c-614b-4135-9a57-f8bf64da78c4.png)
  - Pruning with FPGMPruner:
    
    ![Screen Shot 2022-10-04 at 12 43 11 PM](https://user-images.githubusercontent.com/22122136/193910002-98a1795b-eb49-4705-9874-932573b8e23f.png)
  - Pruning with FPGMPruner:
    
    ![Screen Shot 2022-10-04 at 12 44 18 PM](https://user-images.githubusercontent.com/22122136/193910047-1037949f-bb2d-402a-a2c9-344b3b5e80c0.png)


- Project Learnings
  - As we can see that the accuracy of the model post pruning is at par or in some cases higher than the accuracy of the original model on the validation dataset.
  - Another important factor to be considered while pruning is the training time for the model. The training time incurred for training of the pruned model in all pruner-configuration combinations is significantly lesser than the training time required for the original model. In the cases where the sparsity ratio is lower i.e. configuration 2, the training time is even lesser than than the training time taken for pruned models with configuration 1 since we obtain a more compact model after pruning.
  - The sparsity ratios defined in the configuration list for each pruning method also have a significant effect on the pruning process. In configuration 1, the sparsity ratio is set to 0.5 which forces the pruning process to narrow down the models layers to 1/2 of their original size significantly reducing training time and model carbon footprint. As shown in the results, the model pruning with a 0.75 ratio does not have a significant decrease in accuracy from the accuracy of the 0.5 sparsity ratio pruned model, but provides a more compact model with faster training time and thus can be considered more optimal.
  - In terms of the pruner methods, both the methods follow a different mathematical approach to deciding the weight blocks that need to be pruned. In our particular example, with the mnist dataset, the approach followed by the FPGM pruner shows to be more effective as it helps achieve an accuracy of more than 99% in the configuration 1 settings.

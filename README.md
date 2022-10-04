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
    
    ![Screen Shot 2022-10-04 at 3 34 26 PM](https://user-images.githubusercontent.com/22122136/193909614-61e058ba-85cf-4fd7-a3f3-864027afb687.png)
  - Pruning with N1NormPruner:
    
    ![Screen Shot 2022-10-04 at 12 40 06 PM](https://user-images.githubusercontent.com/22122136/193909846-d34a5ffc-4eeb-4995-bf65-21b5eb168bf5.png)
  - Pruning with N1NormPruner:
    
    ![Screen Shot 2022-10-04 at 12 42 35 PM](https://user-images.githubusercontent.com/22122136/193909881-4332871c-614b-4135-9a57-f8bf64da78c4.png)
  - Pruning with FPGMPruner:
    
    ![Screen Shot 2022-10-04 at 12 43 11 PM](https://user-images.githubusercontent.com/22122136/193910002-98a1795b-eb49-4705-9874-932573b8e23f.png)
  - Pruning with FPGMPruner:
    
    ![Screen Shot 2022-10-04 at 12 44 18 PM](https://user-images.githubusercontent.com/22122136/193910047-1037949f-bb2d-402a-a2c9-344b3b5e80c0.png)

As we can see the result of the Pruned model is on par with the Original model and at the same time require less computaion

# Model_Prunning
Several basic methods for model compression

- Networks are typically over-parameterized (there is significant redundant weights or neurons)
- Prune them!

step 1: Pretrained Network (large)  
step 2: Evaluate the importance

        - Importance of weight: L1, L2, ....
        - Importance of a neuron:
            The number of times it wasn't zero on a given dataset

step 3: Remove (smaller)

        After prunning, the accuracy will drop (hopefully not too much)
        Don't prune too much at once, or the network won't recover. 

step 4: Fine-tune

step 5: Loop to step2


***Why prunning?***

How about simply train a smaller network?
    
    - It is widely known that smaller network is more diffcult to learn successfully
    - If the network is large enough, it is able to find the global optimal easily. 
    - Lottery Ticket Hypothesis
      - Small network with random init weights is hard to train
      - Small network with random init weights of big network can be trained
      - 大的模型是有多个小模型组成的, 大的模型可以很容易被训练,但他剪裁出的小模型像是乐透中奖一样, 有的可以被训练, 而有的不行
  
    - Rethinking the value of Network Prunning
      - Real random initialization, not original random initialization in "Lottery Ticket Hypothesis"
      - Prunning algorithms could be seen as performing network architecture search

***How to prune?***
- Weight pruning - mask
- Neuron pruning 




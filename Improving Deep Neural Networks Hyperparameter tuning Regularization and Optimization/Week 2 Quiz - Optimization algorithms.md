## Week 2 Quiz - Optimization algorithms

1. Which notation would you use to denote the 3rd layer’s activations when the input is the 7th example from the 8th minibatch?

    - a^\[3]\{8}\(7)
    
    Note: **[i]{j}(k)** superscript means **i-th layer**, **j-th minibatch**, **k-th example**
    
2. Which of these statements about mini-batch gradient descent do you agree with?

    - [ ] You should implement mini-batch gradient descent without an explicit for-loop over different mini-batches, so that the algorithm processes all mini-batches at the same time (vectorization).
    - [ ] Training one epoch (one pass through the training set) using mini-batch gradient descent is faster than training one epoch using batch gradient descent.
    - [x] One iteration of mini-batch gradient descent (computing on a single mini-batch) is faster than one iteration of batch gradient descent.
    
    Note: Vectorization is not for computing several mini-batches in the same time.
    
3. Why is the best mini-batch size usually not 1 and not m, but instead something in-between?

    - If the mini-batch size is 1, you lose the benefits of vectorization across examples in the mini-batch.
    - If the mini-batch size is m, you end up with batch gradient descent, which has to process the whole training set before making progress.
    
4. Suppose your learning algorithm’s cost ***J***, plotted as a function of the number of iterations, looks like [this](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/KIycr3grEeeJIwrF5BVsIg_f1c324824bd9220c7ee985cce1521404_cost.png?expiry=1558828800000&hmac=mYrDGYMnxnoc1NJ-kOLHh-IW-xMyti5UvS7YfREn-a8):

    - [ ] Whether you’re using batch gradient descent or mini-batch gradient descent, something is wrong.
    - [x] If you’re using mini-batch gradient descent, this looks acceptable. But if you’re using batch gradient descent, something is wrong.
    - [ ] If you’re using mini-batch gradient descent, something is wrong. But if you’re using batch gradient descent, this looks acceptable.
    - [ ] Whether you’re using batch gradient descent or mini-batch gradient descent, this looks acceptable.
    
    Note: There will be some oscillations when you're using mini-batch gradient descent since there could be some noisy data example in batches. However batch gradient descent always guarantees a lower ***J*** before reaching the optimal.
    
5. Suppose the temperature in Casablanca over the first three days of January are the same:

    Jan 1st: θ_1 = 10
    
    Jan 2nd: θ_2 * 10
    
    Say you use an exponentially weighted average with β = 0.5 to track the temperature: v_0 = 0, v_t = βv_t−1 + (1 − β)θ_t. If v_2 is the value computed after day 2 without bias correction, and v^corrected_2 is the value you compute with bias correction. What are these values?
    
    - [ ] v_2 = 7.5, v^corrected_2 = 7.5
    - [ ] v_2 = 10, v^corrected_2 = 7.5
    - [ ] v_2 = 10, v^corrected_2 = 10
    - [x] v_2 = 7.5, v^corrected_2 = 10
    
6. Which of these is NOT a good learning rate decay scheme? Here, t is the epoch number.

    - α = e^t * α_0
    
    Note: This will explode the learning rate rather than decay it.
    
7. You use an exponentially weighted average on the London temperature dataset. You use the following to track the temperature: v_t = βv_t−1 + (1 − β)θ_t. The red line below was computed using β = 0.9. What would happen to your red curve as you vary β? (Check the two that apply) [image](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/W0boqHgrEee6mw7xN92yoA_3a1f4052dc56969b5d7da4024a46836d_temp.png?expiry=1558828800000&hmac=Bp4aNItgCdX0WxRC-ARJiOeeASK5a5P0C6S19QzKPbk)

    - Increasing β will shift the red line slightly to the right.
    - Decreasing β will create more oscillation within the red line.
    > The red line corresponds to β=0.9. In lecture we had a green line $$\beta = 0.98) that is slightly shifted to the right. The red line corresponds to β=0.9. In lecture we had a yellow line $$\beta = 0.98 that had a lot of oscillations.
    
8. Consider this [figure](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/fv6gungsEeeJIwrF5BVsIg_6da8c45ffcd4075de23d8e93884937f1_GD.png?expiry=1558828800000&hmac=w4LjB_C7ElqxcO6vGjwx99zr9VRob5HWTDjHARnpEHc):

    These plots were generated with gradient descent; with gradient descent with momentum (β = 0.5) and gradient descent with momentum (β = 0.9). Which curve corresponds to which algorithm?

    (1) is gradient descent. (2) is gradient descent with momentum (small β). (3) is gradient descent with momentum (large β)

9. Suppose batch gradient descent in a deep network is taking excessively long to find a value of the parameters that achieves a small value for the cost function J(W[1],b[1],...,W[L],b[L]). Which of the following techniques could help find parameter values that attain a small value forJ? (Check all that apply)

    - [x] Try using Adam
    - [x] Try better random initialization for the weights
    - [x] Try tuning the learning rate α
    - [x] Try mini-batch gradient descent
    - [ ] Try initializing all the weights to zero

10. Which of the following statements about Adam is False? 

    - [x] Adam should be used with batch gradient computations, not with mini-batches.
    - [ ] The learning rate hyperparameter \alphaα in Adam usually needs to be tuned.
    - [ ] Adam combines the advantages of RMSProp and momentum.
    - [ ] We usually use “default” values for the hyperparameters β_1, β_2, and ε in Adam (β_1=0.9, β_2=0.999, ε=10^−8)
    
    Note: Adam could be used with both.

## Week 1 Quiz - Recurrent Neural Networks


1. Suppose your training examples are sentences (sequences of words). Which of the following refers to the jth word in the ith training example?

  - [x] $x^{(i)<j>}$
  - [ ] $x^{<i>(j)}$
  - [ ] $x^{(j)<i>}$
  - [ ] $x^{<j>(i)}$

  

2. Consider this RNN: This specific type of architecture is appropriate when:

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/WVhjoPCuEee5Rg5IFJ7l8g_a7b6030c6e5a53b431fee7aaabecd9bd_Screen-Shot-2018-01-03-at-5.48.26-PM.png?expiry=1604620800000&hmac=Q2revPaqo8yJyaBvE0QM-xp4KRWp9zixMn67CLFJzfw)

  - [x] $T_x = T_y$
  - [ ] $T_x < T_y$
  - [ ] $T_x > T_y$
  - [ ] $T_x = 1$

  

3. To which of these tasks would you apply a many-to-one RNN architecture? (Check all that apply).

  - [ ] Speech recognition (input an audio clip and output a transcript) 
  - [x] Sentiment classification (input a piece of text and output a 0/1 to denote positive or negative sentiment) 
  - [ ] Image classification (input an image and output a label)
  - [x] Gender recognition from speech (input an audio clip and output a label indicating the speaker’s gender) 

  

4. You are training this RNN language model. At the t-th time step, what is the RNN doing? Choose the best answer.

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/cxeeLPCvEee7YRLKCWJ4hg_bca1b05c70eece156b470abb2d0f0cad_Screen-Shot-2018-01-03-at-5.56.30-PM.png?expiry=1604620800000&hmac=OPS6c4_EH2cC4SXvKu5f4Lf-RpQ2Ug9at2D8FLks0lo)

  - [ ] Estimating $P(y^{<1>},y^{<2>}, \dots, y^{<t-1>})$
  - [ ] Estimating $P(y^{<t>})$
  - [x] Estimating  $P(y^{<t>} | y^{<1>},y^{<2>}, \dots, y^{<t-1>})$
  - [ ] Estimating  $$P(y^{<t>} | y^{<1>},y^{<2>}, \dots, y^{<t>})$$

  

5. You have finished training a language model RNN and are using it to sample random sentences, as follows. What are you doing at each time step t?

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/zOkWE_CvEee5Rg5IFJ7l8g_f36533d67eb6590d5bcb7021d88493eb_Screen-Shot-2018-01-03-at-5.58.53-PM.png?expiry=1604620800000&hmac=GsUgRMwAeQdffYyGh0UqrOl7W-B8YoTJZaq-OBkdrb0)

  - [ ]  (i) Use the probabilities output by the RNN to pick the highest probability word for that time-step as $y^{<t>}$. (ii) Then pass this selected word to the next time-step.
  - [ ] (i) Use the probabilities output by the RNN to randomly sample a chosen word for that time-step as $y^{<t>}$. (ii) Then pass the ground-truth word from the training set to the next time-step.
  - [ ] (i) Use the probabilities output by the RNN to pick the highest probability word for that time-step as $y^{<t>}$. (ii) Then pass this selected word to the next time-step.
  - [x] (i) Use the probabilities output by the RNN to randomly sample a chosen word for that time-step as $y^{<t>}$. (ii) Then pass this selected word to the next time-step.

  

6. You are training an RNN, and find that your weights and activations are all taking on the value of NaN (“Not a Number”). Which of these is the most likely cause of this problem?

  - [ ] Vanishing gradient problem.
  - [x] Exploding gradient problem.
  - [ ] ReLU activation function g(.) used to compute g(z), where z is too large.
  - [ ] Sigmoid activation function g(.) used to compute g(z), where z is too large.

  

7. Suppose you are training a LSTM. You have a 10000 word vocabulary, and are using an LSTM with 100-dimensional activations $a^{<t>}$. What is the dimension of $\Gamma_u$ at each time step?

  - [ ] 1
  - [x] 100
  - [ ] 300
  - [ ] 10000

  

8. Here’re the update equations for the GRU. Alice proposes to simplify the GRU by always removing the $\Gamma_u$. I.e., setting $\Gamma_u = 1$. Betty proposes to simplify the GRU by removing the $\Gamma_r$. I. e., setting $\Gamma_r = 1$ always. Which of these models is more likely to work without vanishing gradient problems even when trained on very long input sequences?

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/y-VsavCwEeeVOQpGYM3DAA_b10afdb5d35702d711338d5b72ce5be7_Screen-Shot-2018-01-03-at-6.05.56-PM.png?expiry=1604620800000&hmac=kKlAahqWR1pqdRzpI3i0HqBXOTyd4CfgVuKMUP3RRBs)

  - [ ]  Alice’s model (removing $\Gamma_u$), because if $\Gamma_r \approx 0$ for a timestep, the gradient can propagate back through that timestep without much decay. 
  - [ ] Alice’s model (removing $\Gamma_u$), because if $\Gamma_r \approx 1$ for a timestep, the gradient can propagate back through that timestep without much decay.
  - [x] Betty’s model (removing $\Gamma_r$), because if $\Gamma_u \approx 0$ for a timestep, the gradient can propagate back through that timestep without much decay. 
  - [ ] Betty’s model (removing $\Gamma_r$), because if $\Gamma_u \approx 1$ for a timestep, the gradient can propagate back through that timestep without much decay. 

  

9. Here are the equations for the GRU and the LSTM: From these, we can see that the Update Gate and Forget Gate in the LSTM play a role similar to _______ and ______ in the GRU. What should go in the the blanks?

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ZJgnEfCxEeeVOQpGYM3DAA_2552c64114ba9a4a065a54e8e4855b39_Screen-Shot-2018-01-03-at-6.10.24-PM.png?expiry=1604620800000&hmac=EgzzTb44jThd0tk10CQLEJ9Ahqp5MtQKnJGNKr1vpWI)

  - [x] $\Gamma_u$ and $1 - \Gamma_u$
  - [ ] $\Gamma_u$ and $\Gamma_r$
  - [ ] $1 - \Gamma_u$a and $\Gamma_u$
  - [ ] $\Gamma_r$ and $\Gamma_u$

  

10. You have a pet dog whose mood is heavily dependent on the current and past few days’ weather. You’ve collected data for the past 365 days on the weather, which you represent as a sequence as $x^{<1>}, \dots, x^{<365>}$. You’ve also collected data on your dog’s mood, which you represent as $y^{<1>}, \dots, y^{<365>}$. You’d like to build a model to map from x→y. Should you use a Unidirectional RNN or Bidirectional RNN for this problem?

  - [ ] Bidirectional RNN, because this allows the prediction of mood on day t to take into account more information.
  - [ ] Bidirectional RNN, because this allows backpropagation to compute more accurate gradients. 
  - [x] Unidirectional RNN, because the value of $y^{<t>}$ depends only on , $x^{<1>}, \dots, x^{<t>}$ but not on  $x^{<t+1>}, \dots, x^{<365>}.$
  - [ ] Unidirectional RNN, because the value of $y^{<t>}$ depends only on $x^{<t>}$, and not other days’ weather.
---
permalink: /projects/
title: "Project Contents"
categories: projects
use_math: true
---
#### 1. [Stock Price Correlation Coefficient Prediction](#stock-price-correlation-coefficient-prediction)
#### 2. [EPL Soccer Match Result Prediction with ML Models from Scratch](#epl-soccer-match-result-prediction-with-ml-models-from-scratch)

---

## Stock Price Correlation Coefficient Prediction

paper : [Stock Price Correlation Coefficient Prediction with ARIMA LSTM Hybrid Model](https://arxiv.org/pdf/1808.01560.pdf)  
codes : [github repository](https://github.com/imhgchoi/ARIMA-LSTM-hybrid-corrcoef-predict)

<center>
<img src="../assets/images/stocks.jpg" alt="drawing" width="800"/>
</center>
  <br>
  
* **Why do we need to compute the correlation coefficients for investment?**  

According to Harry Markowitz's Modern Portfolio Theory, we normally assess the stock portfolio's risk as follows.
 <br>  
<center>
$$
\sigma_p = w^2_i\sigma^2_i + w^2_j\sigma^2_j + 2w_iw_j\sigma_i\sigma_j\rho_{ij}
$$
</center>  

where $w_i$ and $w_j$ be the weights assigned to each asset in the portfolio, $\sigma_i$ and $\sigma_j$ the historical
standard deviation, and $\rho_{ij}$ the correlation coefficient of those two.
 <br>
 <br>  
 
* **How do we predict correlation coefficients?**

Here, various methods have been used to estimate the correlation coefficient value $\rho_{ij}$.  
One of the most simplest and common method used is what so called the **Full Historical Model**. The model assumes that
the correlation coefficient will be identical to the historical value. Thus, the equation,
 <br>  
<center>
$$
\hat{\rho}^{(t)}_{ij} = \rho^{(t-1)}_{ij}
$$
</center>
 <br>  

Several other models for correlation coefficient prediction include...  
the **Constant Correlation Model**
 <br>  
<center>
$$
\hat{\rho}_{ij}^{(t)} = \frac{\displaystyle \sum_{i>j} \rho_{ij}^{(t-1)}} {\displaystyle n(n-1) / 2}
$$
</center>
where $n$ is the number of assets in the portfolio,
 <br>  

the **Single-Index Model**
 <br>  
<center>
$$
\hat{\rho}_{ij}^{(t)} = \frac{\displaystyle \beta_i \beta_j \sigma_m^2} {\displaystyle \sigma_i \sigma_j}
$$
</center>
where $\beta_i$/$\beta_j$ are the beta value for stock item $i$, and $\sigma_m$ is the market's volatility,
 <br>  

the **Multi-Group Model**
 <br>  
<center>
$$
\hat{\rho}_{ij}^{(t)} = \begin{cases}
\frac{\displaystyle \sum_{i \in \alpha}^{n_\alpha} \sum_{j \in \beta ; i \neq j}^{n_\beta} \rho_{ij}^{(t-1)}} {\displaystyle n_\alpha (n_\beta - 1)}, \hspace{2mm} \text{where  $\alpha$ = $\beta$}\\
\frac{\displaystyle \sum_{i \in \alpha}^{n_\alpha} \sum_{j \in \beta ; i \neq j}^{n_\beta} \rho_{ij}^{(t-1)}} {\displaystyle n_\alpha  n_\beta}, \hspace{2mm} \text{where $\alpha$ $\neq$ $\beta$}
\end{cases}
$$
</center>
where $\alpha$ and $\beta$ notation here denotes the industry sector, and $n_\alpha$ and $n_\beta$ is the total number
 of assets in the corresponding industry sector.
 <br>  

You may refer to the paper's section 2, "Various Financial Models for Correlation Prediction" for a more detailed 
elaboration on each model.
 <br>  
 <br>  
 
<center>
<img src="../assets/images/questions.png" alt="drawing" width="300"/>
</center>
  <br>
  
* **Room for Improvements?**  

The above models only consider linearity in their predictions. However, the financial data are innately non-linear,
thus calling for non-linear models for its correlation coefficient predictions. In my project paper, I proposed to
adopt the ARIMA-LSTM hybrid model to capture both linearity and non-linearity in prediction.  
Note that the ARIMA-LSTM model was originally proposed in 2003 by G.P. Zhang, in his paper "[Time series forecasting using a hybrid ARIMA 
and neural network model](https://www.sciencedirect.com/science/article/abs/pii/S0925231201007020)".

The ARIMA sector renders a linear prediction on the stream of correlation coefficients precomputed with a fixed-sized 
sliding window. The order for each time series is selected dynamically based on its AIC values. Then, the residual value
for each time step is computed, which becomes the input for the next LSTM RNN sector.
 
<center>
<img src="../assets/images/lstm.png" alt="drawing" width="450"/>

LSTM Cell Architecture
</center>
  <br> 
 
For prediction, The ARIMA model and the LSTM RNN model each predicts the future (linearity-based) correlation coefficient
and (non-linearity-based) residual value. The two predictions are added to render the final correlation coefficient value.
  <br>
  <br> 
  
* **Experiment Results**

The model was tested against the formerly mentioned financial predictive models. The performance indices indicate that
the ARIMA-LSTM hybrid model outperforms all the other models.

<center>
<img src="../assets/images/arimalstm_test1.png" alt="drawing" width="450"/>
</center>
  <br> 

To test for robustness, I iteratively tested the model on different combinations of 10 stock assets as well.

<center>
<img src="../assets/images/arimalstm_test2.png" alt="drawing" width="450"/>
</center>
  <br> 
  
  
## EPL Soccer Match Result Prediction with ML Models from Scratch

under construction!!
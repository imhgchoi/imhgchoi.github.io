---
permalink: /projects/
title: "Project Lists"
categories: projects
use_math: true
---
#### 1. [Stock Price Correlation Coefficient Prediction](#stock-price-correlation-coefficient-prediction)
#### 2. [EPL Soccer Match Result Prediction with ML Models from Scratch](#epl-soccer-match-result-prediction-with-ml-models-from-scratch)

---

## Stock Price Correlation Coefficient Prediction

* paper : [Stock Price Correlation Coefficient Prediction with ARIMA LSTM Hybrid Model](https://arxiv.org/pdf/1808.01560.pdf)  
* codes : [github repository](https://github.com/imhgchoi/ARIMA-LSTM-hybrid-corrcoef-predict)

According to Harry Markowitz's Modern Portfolio Theory, a correct prediction of the correlation coefficient of 
two assets is crucial for accurately assessing risk, and optimizing the portfolio. For instance, let us assume
a simple portfolio that consists of two different stock assets A and B. Let $w_A$ and $w_B$ be the weights assigned
to each asset in the portfolio, $\sigma_A$ and $\sigma_B$ the historical standard deviation of each asset, and
$\rho_{AB}$ be the correlation coefficient of them. Then, the portfolio's risk is computed as follows :
 <br>  
<center>
$$
\sigma_p = w^2_A\sigma^2_A + w^2_B\sigma^2_B + 2w_Aw_B\sigma_A\sigma_B\rho_{AB}
$$
</center>
 <br>  
 
Here, various methods have been used to estimate the correlation coefficient value $\rho_{AB}$.  
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
 <br>  


Predicting the price correlation of two assets for future time periods is important in portfolio optimization. We apply LSTM recurrent neural networks
(RNN) in predicting the stock price correlation coefficient of two individual
stocks. RNN’s are competent in understanding temporal dependencies. The
use of LSTM cells further enhances its long term predictive properties. To encompass both linearity and nonlinearity in the model, we adopt the ARIMA
model as well. The ARIMA model filters linear tendencies in the data and
passes on the residual value to the LSTM model. The ARIMA-LSTM hybrid
model is tested against other traditional predictive financial models such as
the full historical model, constant correlation model, single-index model and
the multi-group model. In our empirical study, the predictive ability of the
ARIMA-LSTM model turned out superior to all other financial models by a
significant scale. Our work implies that it is worth considering the ARIMALSTM model to forecast correlation coefficient for portfolio optimization.


### EPL Soccer Match Result Prediction with ML Models from Scratch

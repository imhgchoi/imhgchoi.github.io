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

* paper : [Stock Price Correlation Coefficient Prediction with ARIMA LSTM Hybrid Model](https://arxiv.org/pdf/1808.01560.pdf)  
* codes : [github repository](https://github.com/imhgchoi/ARIMA-LSTM-hybrid-corrcoef-predict)

![stock](../assets/images/stocks.jpg =100x20)

**How did we compute the correlation coefficient for our portfolios?**  
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
where $beta_i$/$beta_j$ is the beta value for stock item $i$, and $\sigma_m$ is the market's volatility,
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
 <br><br>  
 
The above variations of correlation coefficient estimating models have shown some success. However, the models only
consider linearity in prediction. The financial data are innately non-linear, thus calling for non linear models in
correlation coefficient prediction. Here, I proposed to adopt the ARIMA-LSTM hybrid model to capture both linearity
and non-linearity in prediction.  
The ARIMA-LSTM model was originally proposed by G.P. Zhang, in his paper "Time series forecasting using a hybrid ARIMA 
and neural network model" in year 2003.

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
significant scale. Our work implies that it is worth considering the ARIMA LSTM model to forecast correlation coefficient for portfolio optimization.


### EPL Soccer Match Result Prediction with ML Models from Scratch

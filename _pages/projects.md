---
permalink: /projects/
title: "Project Lists"
date: 2020-02-20 00:00:00 -0400
categories: projects
---
#### 1. [Stock Price Correlation Coefficient Prediction with ARIMA LSTM Hybrid Model](#1.-stock-price-correlation-coefficient-prediction-with-arima-lstm-hybrid-model)
#### 2. [EPL Soccer Match Result Prediction with ML Models from Scratch](#2.-epl-soccer-match-result-prediction-with-ml-models-from-scratch)

---

### 1. Stock Price Correlation Coefficient Prediction with ARIMA LSTM Hybrid Model

paper link : [https://arxiv.org/pdf/1808.01560.pdf](https://arxiv.org/pdf/1808.01560.pdf)  
code link : [https://github.com/imhgchoi/ARIMA-LSTM-hybrid-corrcoef-predict](https://github.com/imhgchoi/ARIMA-LSTM-hybrid-corrcoef-predict)

According to Harry Markowitz's Modern Portfolio Theory, a correct prediction of the correlation coefficient of 
two assets is crucial for accurately assessing risk, and optimizing the portfolio. For instance, let us assume
a simple portfolio that consists of two different stock assets A and B. Let \\[d\\]

<img src="https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1"> 
  


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


### 2. EPL Soccer Match Result Prediction with ML Models from Scratch

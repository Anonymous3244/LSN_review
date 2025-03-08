# LSN

The repository contains the source code and additional experimental results of our LSN paper.

## 1. Different Parameter of BS Equation for LSN.


<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r02sigma005l10001l21l301l4001.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r02sigma02l10001l21l301l4001.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r005simga02l10001l21l301l4001.png width=200 height=150 />

In the experiment, the parameters of the Black-Scholes equation are set as follows:   $\Omega = (0,20)$, and $T = 1$.  The volatility $\sigma$ and the risk-free interest rate $r$ are selected a subset of parameters that cover both small and large differences  to ensure a representative evaluation. The dataset comprises $50$ internal points and $2000$ boundary points. The neural network architecture is designed with a depth of $9$ layers and a width of $50$ neurons. The Lie symmtery operator is $G_2$. The training iteration is $200,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.

## 2. Additional Experiments on Real-Time Market Dataset.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/market.png width=200 height=150 />

We aimed to extend our analysis to real-time market data, focusing on call options on Nasdaq 100  as underlying assets. The NN model for option pricing relies on two fixed inputs: volatility  and risk-free interest rate. In our experimental setup, we utilized implied volatility sourced from the Optionmetrics dataset. For the risk-free rate, we use the average 1-year Treasury yield over the option period, obtained via web scraping from Yahoo Finance.


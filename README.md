# LSN

The repository contains the source code and additional experimental results of our LSN paper.

## 1. Different Parameter of BS Equation for LSN.


<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r02sigma005l10001l21l301l4001.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r02sigma02l10001l21l301l4001.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r005simga02l10001l21l301l4001.png width=200 height=150 />

In the experiment, the parameters of the Black-Scholes equation are set as follows:   $\Omega = (0,20)$, and $T = 1$.  The volatility $\sigma$ and the risk-free interest rate $r$ are selected a subset of parameters that cover both small and large differences  to ensure a representative evaluation. The dataset comprises $50$ internal points and $2000$ boundary points. The neural network architecture is designed with a depth of $9$ layers and a width of $50$ neurons. The Lie symmtery operator is $G_2$. The training iteration is $200,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.

## 2. Additional Experiments on Real-Time Market Dataset.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/market.png width=200 height=150 />

We aimed to extend our analysis to real-time market data, focusing on call options on Nasdaq 100  as underlying assets. The NN model for option pricing relies on two fixed inputs: volatility  and risk-free interest rate. In our experimental setup, we utilized implied volatility sourced from the Optionmetrics dataset. For the risk-free rate, we use the average 1-year Treasury yield over the option period, obtained via web scraping from Yahoo Finance.

## 3. Different Equation for LSN.
<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/vasicek.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/kdv.png width=200 height=150 />

We acknowledge testing on a single PDE system is limited. We are expanding experiments to include the Vasicek model and other KDV ($u_t=u_{xxx}+uu_x$)　equations. Notably, in the Vasicek model where LPS's regularization coincides with the PINN loss, LPS fails while LSN remains effective.

## 4. FNO vs. LSN vs. FDM.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/slope.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/kdv_fno.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/fdm.png width=200 height=150 />

| Datasize (x,t) | 4k=(40,100) | 5k=(50,100) | 6k=(60,100) | 7k=(70,100) |
|----------------|-------------|-------------|-------------|-------------|
| **Method**     |**TestError**|**TestError**|**TestError**|**TestError**|
| **FDM**        | 8.09e-2     | 5.60e-2     | 3.00e-2     | 2.42e-2     | 
| **LSN**        | 3.91e-4     | 2.17e-4     | 3.11e-4     | 2.13e-4     | 
| **PINN**       | 1.68e-3     | 8.40e-4     | 2.44e-3     | 6.35e-4     | 


| Datasize (x,t) | 4k=(40,100) | 5k=(50,100) | 6k=(60,100) | 7k=(70,100) |
|----------------|-------------|-------------|-------------|-------------|
| **Method**     | **ConError**| **ConError**| **ConError**| **ConError**|
| **FDM**        | 1.81e+3     | 1.80e+3     | 1.78e+3     | 1.77e+3     |
| **LSN**        | 4.83e-3     | 1.20e-3     | 3.71e-3     | 2.46e-3     |
| **PINN**       | 2.15e-1     | 1.28e-1     | 2.11e-1     | 1.60e-1     |

We are currently conducting experiments comparing LSN with neural operator approaches (e.g., FNO) and traditional numerical methods (e.g., FDM). Preliminary results show that LSN performs competitively. Using the second-order finite difference as a reference (refer to the table and figures), we found that LSN does not affect the sample complexity. However, the overall accuracy of LSN is higher than that of PINNs.

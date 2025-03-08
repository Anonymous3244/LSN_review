# LSN

The repository contains the source code and additional experimental results of our LSN paper.

## 1. Different parameter of BS equation for LSN.


<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r02sigma005l10001l21l301l4001.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r02sigma02l10001l21l301l4001.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r005simga02l10001l21l301l4001.png width=200 height=150 />

In the experiment, the parameters of the Black-Scholes equation are set as follows:   $\Omega = (0,20)$, and $T = 1$.  The volatility $\sigma$ and the risk-free interest rate $r$ are selected a subset of parameters that cover both small and large differences  to ensure a representative evaluation. The dataset comprises $50$ internal points and $2000$ boundary points. The neural network architecture is designed with a depth of $9$ layers and a width of $50$ neurons. The Lie symmtery operator is $G_2$. The training iteration is $200,000$, with a learning rate of $lr = 0.001$ and a learning rate decay factor of $\gamma = 0.95$.

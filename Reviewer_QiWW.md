>**Q1:**  Comparative Analysis for LPS 
The comparison with LPS is currently limited to settings where $\sigma=0.5$ and$r=0.1$. A more comprehensive evaluation across a wider range of parameter values would strengthen the analysis. Specifically, could authors provide results for PINN variants, LPS, and LSN across $\sigma=0.05, 0.1, 0.2, 0.5$, $r=0.01, 0.02, 0.05, 0.1, 0.2$ (total 20 experiments for each method)? These values are particularly relevant given that, in real-world scenarios ( $\sigma=0.2$, $r=0.2$).


**A1:** Thanks and address. We agree that a broader range of parameter values would strengthen the analysis. However, conducting 20 experiments for each method, with each experiment running for 200,000 steps, is time-prohibitive within a two-week timeframe. Instead, we have selected a subset of parameters that cover both small and large differences in $\sigma$ and $r$ to ensure a representative evaluation. Specifically, we have conducted experiments for $(r, \sigma)=\{(0.05, 0.2), (0.2, 0.2), (0.2, 0.05)\}$. The results show consistent performance of LSN across these parameters, further validating its robustness. As shown in the following experiments,

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r02sigma005l10001l21l301l4001.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r02sigma02l10001l21l301l4001.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/r005simga02l10001l21l301l4001.png width=200 height=150 />


The experiments demonstrate that LSN with various parameter of BS equation consistently outperform PINN and LPS.


>**Q2:** Moreover, I believe LPS should be trained with various $\lambda_4$ for fair comparison. I suggest using $\lambda_4=1e−3, 1e−4, 1e−5$.

**A2:**  Thanks. To ensure a fair comparison, we have meticulously fine-tuned LPS in Figure 7 of the manuscript. Specifically, we explored a comprehensive range of values for $\lambda_4$, including 10, 1, 1e-1, 1e-2, 1e−3, and 1e−4.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/fig7_r_01_sigma_04_l4_00.png width=200 height=150 />




>**Q5:** Additional Experiments on Different Dataset: Could authors include experiments on European and American option pricing following [1]? This would further demonstrate the applicability of LSN beyond the Black-Scholes equation.  

**A5:**  We have added experiments on European option pricing using real-world financial data. The results demonstrate that LSN performs well in this setting, further validating its applicability beyond the Black-Scholes equation. We are currently working on extending these experiments to American options.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/market.png width=200 height=150 />

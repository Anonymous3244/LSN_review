>**Q1:**  The paper introduces a new method that should work for somewhat general PDEs with Lie symmetries. I find it disheartening to just test this method on a single PDE. This is a major drawback in this paper.

**A1:**   Thanks. We acknowledge testing on a single PDE system is limited. We are expanding experiments to include the Vasicek model and other KDV ($u_t=u_{xxx}+uu_x$)　equations. Notably,　 in the Vasicek model where LPS's regularization coincides with the PINN loss, LPS fails while LSN remains effective. These results will be included in the final manuscript.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/vasicek.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/kdv.png width=200 height=150 />

>**Q2:**  There is no comparison against neural operator approaches and against state-of-the-art approaches from numerical analysis. 

**A2:**  Thanks. We are currently conducting experiments comparing LSN with neural operator approaches (e.g., FNO) and traditional numerical methods (e.g., FDM). Preliminary results show that LSN performs competitively, and we will include these comparisons in the final version of the manuscript.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/kdv_fno.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/fdm.png width=200 height=150 />

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

> **Q3:** It might sitll be helpful to add an experiment for a third PDE for the camera ready version.

**A3:** Thanks very much for your kind support! 

Following your suggestion, we further conducted experiments for a third PDE (Maxwellian tails model: $u_{xt}+u_x+u^2=0$).  LSN consistently outperforms other methods in terms of test error. These results will be included in the final version.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/maxwell1.png width=200 height=150 />


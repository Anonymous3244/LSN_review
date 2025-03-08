>**Q1:**   The application of the proposed method is restricted to a single PDE system.

**A1:**  We acknowledge testing on a single PDE system is limited. We are expanding experiments to include the Vasicek model and other KDV ($u_t=u_{xxx}+uu_x$)　equations. Notably, in the Vasicek model where LPS's regularization coincides with the PINN loss, LPS fails while LSN remains effective. These results will be included in the final manuscript.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/vasicek.png width=200 height=150 /><img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/kdv.png width=200 height=150 />

>**Q7: **  To demonstrate the overall effectiveness of all PINN-based methods, can you also include an error measure and an error plot for a dummy baseline, e.g., a second-order approximation of the option price using the Greeks?

**A7: **  Thanks.  Using the second-order finite difference as a reference (refer to the table and figures), we found that LSN does not affect the sample complexity. However, the overall accuracy of LSN is higher than that of PINNs.

<img src=https://github.com/Anonymous3244/LSN_review/blob/main/Fig/slope.png width=200 height=150 />

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

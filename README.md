# Loss-Functions
Regression Loss Functions\
Source: https://heartbeat.fritz.ai/5-regression-loss-functions-all-machine-learners-should-know-4fb140e9d4b0
<img align="centre" src="https://miro.medium.com/max/486/1*3MsFzl7zRZE3TihIC9JmaQ.png"><br/>

1. Mean Square Error, Quadratic loss, L2 Loss
2. Mean Absolute Error, L1 Loss
<br />
<img align="centre" src="https://miro.medium.com/max/257/1*xjarhfIDtRcaNhp7ZEyEdg.png"><br/>
<img align="left" src="https://miro.medium.com/max/255/1*mlXnpXGdhMefPybSQtRmDA.png"><br/>
<img align="left" src="https://miro.medium.com/max/700/1*JTC4ReFwSeAt3kvTLq1YoA.png"><br/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
MAE loss is useful if the training data is corrupted with outliers (i.e. we erroneously receive unrealistically huge negative/positive values in our training environment, but not our testing environment).
L1 loss is more robust to outliers, but its derivatives are not continuous, making it inefficient to find the solution. L2 loss is sensitive to outliers, but gives a more stable and closed form solution (by setting its derivative to 0.)
<br />
3. Huber Loss, Smooth Mean Absolute Error
<br />
One big problem with using MAE for training of neural nets is its constantly large gradient, which can lead to missing minima at the end of training using gradient descent. For MSE, gradient decreases as the loss gets close to its minima, making it more precise.
<br />
Huber loss can be really helpful in such cases, as it curves around the minima which decreases the gradient. And it’s more robust to outliers than MSE. Therefore, it combines good properties from both MSE and MAE. However, the problem with Huber loss is that we might need to train hyperparameter delta which is an iterative process.
<br />
<br />
<br />
<img align="left" src="https://miro.medium.com/max/525/1*0eoiZGyddDqltzzjoyfRzA.png"><br/>

<img align="left" src="https://miro.medium.com/max/504/1*jxidxadWSMLvwLDZz2mycg.png"><br/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
4. Log-Cosh Loss
<br />
<img align="left" src="https://miro.medium.com/max/436/1*hj5n5273jYX7rclO7bnfJg.png"><br/>
<img align="left" src="https://miro.medium.com/max/504/1*BAbgW_JdwyAWLZR2dE1Ujg.png"><br/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
log(cosh(x)) is approximately equal to (x ** 2) / 2 for small x and to abs(x) - log(2) for large x. This means that 'logcosh' works mostly like the mean squared error, but will not be so strongly affected by the occasional wildly incorrect prediction. It has all the advantages of Huber loss, and it’s twice differentiable everywhere, unlike Huber loss.
<br />
second derivative is available

5.Quantile Loss
<br />
<br />
<br />
<img align="left" src="https://miro.medium.com/max/700/1*ePh5hyrWS5f591nUORz8_A.png"><br/>
<img align="left" src="https://miro.medium.com/max/700/1*h_iOn3gSUa2bk6o0foudDA.png"><br/>
<br/>
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
<br />
Prediction interval from least square regression is based on an assumption that residuals (y — y_hat) have constant variance across values of independent variables. We can not trust linear regression models that violate this assumption. <br />
γ is the required quantile and has value between 0 and 1.

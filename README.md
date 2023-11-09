# Monte-Carlo
Monte carlo simulation to predict pv performance based on correlation factors and weather data at a given location <br />

When running on your machine, remove the first line, 
```import credentials.py``` <br />
Then in the ```API_KEY = credentials.API_KEY``` replace "credentials.API_KEY" with your NREL API key. <br />
Can be obtained at https://developer.nrel.gov/signup/ <br /> 
The line should then look like this ```API_KEY = <your api key here>```<br />
<br />
Information on Correlated Multivariate Monte Carlo Simulations can be found in this paper. https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4066115. 
My implementation is based on information from pages 10 and 11.

Monte Carlo steps <br />
Generate standard distribution for each input factor with mean=0 and standard deviation=1 <br />
Take lower cholesky decomposition of correlation coefficient matrix. Multiply this by the matrix of standard distribution samples. <br />
cholesky matrix = L, random samples matrix = S,     $LS = A$ where A is our new correlated samples. <br />
Then we take the mean and standard distribution for each input factor and preform these operations to make our data meaningful in the context of the problem as follows: <br/>

Ea_New = sd_Ea * ea.std() + mean_Ea <br />
lnR0_New = sd_lnR0 * lnR0.std() + mean_lnR0 <br />
x_NEW = sd_X * x.std() + mean_X <br />

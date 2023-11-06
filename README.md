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

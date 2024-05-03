# Black-Scholes-Merton_Option_Pricing

# Aim: Option Pricing using the Black-Scholes-Merton Model

In finance, the Black-Scholes-Merton model is one of the most widely used methods for pricing options. It calculates the theoretical value of an option based on five key variables:

<ul>
    <li>Underlying Price (S)</li>
    <li>Strike Price (K)</li>
   <li> Time to Expiration (T)</li>
    <li>Risk Free Rate (r)</li>
    <li>Volatility (σ)</li>
</ul>    

<h2>Import necessary libraries</h2>
<pre>import math
from scipy.stats import norm</pre>

<h2>Define the variables</h2>
<pre>#Define the variables
S = 22475.85      #Underlying Price
K = 22500     #Strike Price
T = 6     #Time to Expiration
r = 0.1     #Risk-Free Rate
vol = 0.1248   #Volatility (σ)</pre>

<h2>
Calculate d1

The formula for d1 in the Black-Scholes-Merton model is:
<img width="327" alt="image" src="https://github.com/anuragprasad95/Black-Scholes-Merton_Option_Pricing/assets/3609255/6dc531fb-13ff-40cc-b2e4-e7d38aa34b4d">
</h2>
<pre>
    d1 = (math.log(S/K) + (r + 0.5 * vol**2)*T)/(vol *math.sqrt(T))
</pre>

<h2>Calculate d2

The formula for d2 is simply:
<img width="463" alt="image" src="https://github.com/anuragprasad95/Black-Scholes-Merton_Option_Pricing/assets/3609255/f17c7468-7556-4e87-89d0-7399e0f66617">

</h2>
<pre>d2 = d1 - (vol * math.sqrt(T))</pre>

<h2>Calculate Call Option Price

The call option price (C) in the Black-Scholes-Merton model is calculated using the formula:
<img width="384" alt="image" src="https://github.com/anuragprasad95/Black-Scholes-Merton_Option_Pricing/assets/3609255/9a85c262-176d-44df-b77c-e80893ee459f">
</h2>

<pre>C = S * norm.cdf(d1) - K * math.exp(-r * T)* norm.cdf(d2)</pre>
<h2>
Calculate Put Option Price

Finally, the put option price (P) is calculated as:
<img width="410" alt="image" src="https://github.com/anuragprasad95/Black-Scholes-Merton_Option_Pricing/assets/3609255/cff21a19-0599-4efd-b4c5-d745048bb3a7">
</h2>
<pre>P = K * math.exp(-r * T) * norm.cdf(-d2) - S * norm.cdf(-d1)</pre>

<h2>Print the results</h2>
<pre>print("The value of d1 is:", round(d1,4))
print("The value of d2 is:", round(d2,4))
print("The price of the call option is:",round(C,2))
print("The price of the put option is:",round(P,2))</pre>
<samp><img width="419" alt="image" src="https://github.com/anuragprasad95/Black-Scholes-Merton_Option_Pricing/assets/3609255/8655e75b-62da-411c-9a4c-6f871943e61d">
</samp>

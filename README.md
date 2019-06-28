# A Percolation Model of Stock Price Fluctuations

This project is based on the [paper](https://repository.kulib.kyoto-u.ac.jp/dspace/handle/2433/42059) written by Tanaka Hisatoshi.In his paper, he wrote that the Gaussian model predicts that in order for NIKKEI 225 to experience change more than 7% for 6 occasions, it would need 2000 years, but in fact, the same scenario happened in just 11 years. The author then showed that by assuming that traders have bounded sight, and by using percolation theory, such phenomena can be explained.This project applies data from S&P 500 to the model.


## Theory
For the model I have programmed, I first created a 2D torus L*L and then filled it with 1s and 0s
randomly. One signifies that at that site, a trader holds a particular stock and zero means the trader
does not hold that particular stock. Then it proceeds to calculate the influence rate PU and PD. PU
and PD is a function of closing price, 𝛼 and 𝛿. The value of 𝛼 and 𝛿 were calculated by equating
𝑝𝑢 (𝑆̅) = 𝑝𝑑 (𝑆̅), this equation requires the average price, minimum price and maximum price.
Based on the average annual return rate for S&P 500, I made and educated guess on the maximum
price and set the current price as the minimum price. Since the author did not mention how the
values were obtained, I reversed the process by finding the floor and ceiling price before running
the simulation. After calculating the influence rate. A random number will then decide which
influence rate to use. The influence rate will be either PU or PD, if it is PU, the trader at a chosen
site will buy and affects its neighbor and opposite for the other case. A random site (can be viewed
as a trader) will then be chosen, if at the chosen site, the value is 0, the program will then find
another site until the value found at a site is 1. The trader at that site will buy or sell, the probability that its neighbor will follow his or her action depends on the influence rate. This process will then spread to the neighbors. At the end of the process, the number of people influenced will directly affect the return per day calculation. If the influence rate is PU then the return per day will be positive if its equals to PU, the influence rate will be negative. The return per day calculated will produce a new value for the price; this new value for price will then be used to calculate the PU and PD value for the next day. For more information about the theory please read the  [review paper](https://github.com/zhuohann/StockPriceFluctuations/blob/master/A%20percolation%20model%20of%20stock%20price%20fluctuations-a%20literature%20review.pdf) or the [original paper](https://repository.kulib.kyoto-u.ac.jp/dspace/handle/2433/42059).


## Usage

To run the program, download it, and run it using [MATLAB](https://www.mathworks.com/products/matlab.html).

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)

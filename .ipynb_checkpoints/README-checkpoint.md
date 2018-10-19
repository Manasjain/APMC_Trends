# APMC_Trends
Understanding trends in APMC (Agricultural produce market committee)/mandi price &amp; quantity arrival data for different commodities in Maharashtra.
## Objective
- Test and filter outliers.
- Understand price fluctuations accounting the seasonal effect
- Detect seasonality type (multiplicative or additive) for each cluster of APMC and commodities
- De-seasonalise prices for each commodity and APMC according to the detected seasonality type
- Compare prices in APMC/Mandi with MSP(Minimum Support Price)- raw and deseasonalised
## Getting Started
All the trends analysis is done using jupyter notebook and python libraries.

### Installation

#### Jupyter lab
- Easiest way to install Jupyter Notebook and other Ml libraries is using [Conda](https://conda.io/docs/),which is the package manager that the [Anaconda](http://docs.continuum.io/anaconda/) distribution is built upon.
Check your conda version after completing the installation.
```
$ conda -V
```
I am using 4.5.11 on my linux machine.

**Create a virtual environment for your project**

Check conda is up to date
```
$ conda update conda
```
Create and activate your virtual environment
```
$ conda create -n yourenvname python=3.6 anaconda
$ source activate yourenvname
```
If python3.6 is not install on your system you can install [python 3.6](https://www.python.org/downloads/) from here.

### From the source code
After activating your conda environment, clone this git repo using:
```
$ git clone https://github.com/Manasjain/APMC_Trends.git
```
Start Jupyter labs
```
$ jupyter lab
```
## Approach
# Data Cleaning
The Intial data preprocessing is done by removing all non-alphanumeric characters then converting all string objects to  lower alphabets, just to have a generalized data. This yields a common dataset with all relevant variables, including prices, dates, MSP, and crop season.


# Removing Outliers
Outliers are treated using standard statistical procedure, wherein all values not within the 5th to 95th percentile in the interquantile ranges are removed. Although different percentile range can be choosen. This is done after the data has been grouped by commodity, so as to be sensitive to the price of different commodities. For example, the normal price of commodity A may be much higher than that of commodity B, so the outlier detection must be performed as per individual commodity price range. 


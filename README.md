# Data Processing and Analysis Documentation

## Data Preprocessing
DataAccess performs dataset preprocessing, including time series interpolation for oil and gold futures data, and generates various dataset visualizations.

## Model Training and Optimization
- Find Epochs Line conducts continuous training and testing to collect average returns across different epoch numbers
- Bayesian optimization is applied to:
  - Buy/sell hyperparameters
  - Optimal number of epochs

## Correlation Analysis
Three correlation analyses were performed between S&P 500 and both oil and gold futures:
- Pearson correlation coefficient calculation
- Spearman rank correlation coefficient calculation 
- Kendall rank correlation coefficient calculation

## Model Testing
- TEST_Origin_DQN: Tests original DQN ROI for 2019 using S&P 500 + oil futures + gold futures dataset
- TEST_Softmax_DQN: Tests modified Softmax DQN ROI for 2019 using the same combined dataset

## Training and Testing Files
The study includes 16 training and testing files, divided between 200 epochs and 50 epochs, covering both 2019 and 2010-2019 periods. Dataset combinations are denoted as:
- Both: S&P 500 + oil futures + gold futures
- Gold: S&P 500 + gold futures
- WTI: S&P 500 + oil futures
- SPY: S&P 500 only

### 2019 Testing Files (2010-2018 Training)
Files are organized by dataset composition and epoch count (200 or 50), following the naming convention:
DL_SP500_SPY_10K-ActCount-2019-softmax2-[dataset]-[epochs]

### 2010-2019 Testing Files (2001-2010 Training)
Similar organization with naming convention:
DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-[dataset]-[epochs]

## Q-Network Files
NPZ files store trained Q-Network parameters:
- Q_network_epoch_29-299.npz: Stored results for Bayesian optimization
- Softmax_DQN.npz: TEST_Softmax_DQN training results
- Origin_DQN.npz: TEST_Origin_DQN training results

Additional files follow the naming convention:
[year]_[dataset]_[model type]_[network type].npz

## Precision, Recall, and F1 Score Analysis
All analyses conducted with 50 epochs across different training periods:
- 2001-2018 training, 2019 testing
- 2001-01-01 to 2010-07-02 training, 2010-07-02 to 2019-12-31 testing

Results are organized by dataset combination (SPY, WTI, Gold, Both) and time period.

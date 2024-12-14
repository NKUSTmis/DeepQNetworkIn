//其他處理  
DataAccess 資料集前處理，包括針對石油黃金期貨進行時間序列插值法，以及產生一些資料集的圖片。  
Find Epochs Line 針對Epochs 進行連續訓練與測試並收集平均收益。  
Pearson 針對石油期貨、黃金期貨，與S&P500進行皮爾森相關性係數計算  
spearmanr 針對石油期貨、黃金期貨，與S&P500進行斯皮爾曼等級相關性係數計算  
kendalltau 針對石油期貨、黃金期貨，與S&P500進行肯德爾等級相關性係數計算  
bayesian 針對買入賣出超參數進行貝葉斯優化；以及Epochs Num也進行超參數優化。  
TEST_Origin_DQN 測試原DQN的ROI，測試期間2019，資料集為S&P500+石油期貨+黃金期貨。  
TEST_Softmax_DQN 測試Softmax DQN的ROI，測試期間2019，資料集為S&P500+石油期貨+黃金期貨。  

//訓練與測試檔案  
訓練與測試檔案一共16個，其中分為200 epochs與50 epochs 和2019與2010-2019。  
檔名Both = 資料集為S&P500+石油期貨+黃金期貨  
檔名Gold = 資料集為S&P500+黃金期貨  
檔名WTI = 資料集為S&P500+石油期貨  
檔名SPY = 資料集為S&P500  
以下是2010-2018訓練，2019測試的檔案介紹:  
2019測試，資料集為僅S&P500，Epochs 200 DL_SP500_SPY_10K-ActCount-2019-softmax2-SPY  
2019測試，資料集為僅S&P500，Epochs 50 DL_SP500_SPY_10K-ActCount-2019-softmax2-SPY-50  
2019測試，資料集為S&P500+石油期貨，Epochs 200 DL_SP500_SPY_10K-ActCount-2019-softmax2-SPY-WTI  
2019測試，資料集為S&P500+石油期貨，Epochs 50 DL_SP500_SPY_10K-ActCount-2019-softmax2-SPY-WTI-50  
2019測試，資料集為S&P500+黃金期貨，Epochs 200 DL_SP500_SPY_10K-ActCount-2019-softmax2-SPY-Gold  
2019測試，資料集為S&P500+黃金期貨，Epochs 50 DL_SP500_SPY_10K-ActCount-2019-softmax2-SPY-Gold-50  
2019測試，資料集為S&P500+石油期貨+黃金期貨，Epochs 200 DL_SP500_SPY_10K-ActCount-2019-softmax2-SPY-Both  
2019測試，資料集為S&P500+石油期貨+黃金期貨，Epochs 50 DL_SP500_SPY_10K-ActCount-2019-softmax2-SPY-Both-50  

以下是2001-2010訓練，2010-2019測試的檔案介紹:  
2010-2019測試，資料集為僅S&P500，Epochs 200 DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-SPY  
2010-2019測試，資料集為僅S&P500，Epochs 50 DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-SPY-50  
2010-2019測試，資料集為S&P500+石油期貨，Epochs 200 DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-SPY-WTI  
2010-2019測試，資料集為S&P500+石油期貨，Epochs 50 DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-SPY-WTI-50  
2010-2019測試，資料集為S&P500+黃金期貨，Epochs 200 DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-SPY-Gold  
2010-2019測試，資料集為S&P500+黃金期貨，Epochs 50 DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-SPY-Gold-50  
2010-2019測試，資料集為S&P500+石油期貨+黃金期貨，Epochs 200 DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-Both  
2010-2019測試，資料集為S&P500+石油期貨+黃金期貨，Epochs 50 DL_SP500_SPY_10K-ActCount-2010-2019-softmax2-Both-50  

//Q網路NPZ檔案  
npz檔案為訓練完成後的Q-Network檔案。  
Q_network_epoch_29-299.npz為Find Epochs Line時每次訓練儲存的結果，方便貝葉斯優化時取用，不用重新訓練節省時間。  
Softmax_DQN.npz 為TEST_Softmax_DQN訓練完成的檔案。  
Origin_DQN.npz 為TEST_Origin_DQN訓練完成的檔案。  
其餘的會在檔名上有標示  
例如:  
2001_Both_ddqn_behavior_model.npz就是2001-2010訓練，2010-2019測試，資料集為S&P500+石油期貨+黃金期貨，ddqn的行為Q網路  
2001_Both_ddqn_target_model.npz就是2001-2010訓練，2010-2019測試，資料集為S&P500+石油期貨+黃金期貨，ddqn的目標Q網路  
2019_Both_dqn_model就是2010-2018訓練，2019測試，資料集為S&P500+石油期貨+黃金期貨，DQN的Q網路。  

//Precision&Recall&F1_Score
以下Epoch都是50
2001_SPY_Precision&Recall 代表訓練期間2001~2018 測試期間2019 使用S&P500
2001_WTI_Precision&Recall 代表訓練期間2001~2018 測試期間2019 使用S&P500 + 石油
2001_Gold_Precision&Recall 代表訓練期間2001~2018 測試期間2019 使用S&P500 + 黃金
2001_Both_Precision&Recall 代表訓練期間2001~2018 測試期間2019 使用S&P500 + 石油 + 黃金

2019_SPY_Precision&Recall 代表訓練期間2001-01-01~2010-07-02 測試期間2010-07-02~2019-12-31 使用S&P500
2019_WTI_Precision&Recall 代表訓練期間2001-01-01~2010-07-02 測試期間2010-07-02~2019-12-31 使用S&P500 + 石油
2019_Gold_Precision&Recall 代表訓練期間2001-01-01~2010-07-02 測試期間2010-07-02~2019-12-31 使用S&P500 + 黃金
2019_Both_Precision&Recall 代表訓練期間2001-01-01~2010-07-02 測試期間2010-07-02~2019-12-31 使用S&P500 + 石油 + 黃金

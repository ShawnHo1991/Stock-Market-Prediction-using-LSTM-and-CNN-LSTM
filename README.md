透過LSTM與比較CNN+LSTM來分析蘋果股價

結論：CNN+LSTM 模型比單純的 LSTM 更複雜，以這專案LSTM預估的loss較低，跟實際值也較接近

小結：early stop確實能有效降低CNN過度擬合的狀況

特徵：apple_stock股價2015-2024高低價、成交量、sp500成交價、VIX指數、14天RSI、CPI、蘋果季營收

比較兩種資料庫透過LSTM，資料庫1不考慮收盤價，資料庫2不考慮收盤價＋高低價
![image](https://github.com/user-attachments/assets/ffeae257-42cc-4ac5-98aa-fe210b9e9a77)

比較不同look Back的精準度：
![image](https://github.com/user-attachments/assets/10626163-0b91-4476-a554-826fa96b49ba)

比較不同的超參數：Lowest Loss: 0.000305 with parameters: units=100_dropout_rate=0.2_batch_size=32_epochs=100
![image](https://github.com/user-attachments/assets/07cfc50a-6574-442f-a5d6-88d51129b56c)

比較使用LSTM與先由 CNN 提取出關鍵特徵，再由 LSTM 對這些特徵進行時間序列分析。這種多層次的信息融合使得模型能夠更全面地理解數據，從而提高預測的準確性

比較不同超參數透過CNN+LSTM：Lowest Loss CNNLSTM: 0.000474 with parameters: filter=32,Kernel_size=3,pool_size=2
![image](https://github.com/user-attachments/assets/1262baa1-600e-4ed7-a5ce-bb00beb9d4db)

比較不同LSTM超參數透過CNN+LSTM：Lowest Loss: 0.000347 with parameters: units=100_dropout_rate=0.2_batch_size=64_epochs=100
![image](https://github.com/user-attachments/assets/935b48a6-1154-4c45-951d-e4bec149fbe8)

判斷過度擬合導致曲線不夠貼合，加入early stop，預估曲線更優化: patience=5：Lowest Loss: 0.000467 with parameters: units=100_dropout_rate=0.2_batch_size=32_epochs=100
![image](https://github.com/user-attachments/assets/a2b9a7c0-91ee-4958-8fd4-1c9502d458db)

一樣的early stop設定，CNN的pooling size改為2
![image](https://github.com/user-attachments/assets/17f59e62-15c5-4c06-b1c4-088333c7a7a9)



資料來源:
yfinance,ta,fredapi



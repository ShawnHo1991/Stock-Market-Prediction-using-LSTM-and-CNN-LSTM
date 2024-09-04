透過LSTM與比較CNN+LSTM來分析蘋果股價

特徵：apple_stock股價2015-2024高低價、成交量、sp500成交價、VIX指數、14天RSI、CPI、蘋果季營收

比較兩種資料庫透過LSTM，資料庫1不考慮收盤價，資料庫2不考慮收盤價＋高低價
![image](https://github.com/user-attachments/assets/e76f983f-93fe-43ca-8ffc-8802d5d9a77b)

比較不同look Back的精準度：
![image](https://github.com/user-attachments/assets/1b38e778-283a-4ca7-b419-6b8622929638)

比較不同的超參數：
![image](https://github.com/user-attachments/assets/0189b4c0-2a0c-4c57-9988-111feb1aa0b6)

比較使用LSTM與先由 CNN 提取出關鍵特徵，再由 LSTM 對這些特徵進行時間序列分析。這種多層次的信息融合使得模型能夠更全面地理解數據，從而提高預測的準確性

比較不同超參數透過CNN+LSTM
![image](https://github.com/user-attachments/assets/6433133b-f3b5-4f77-9ac9-cbbeaae640aa)



資料來源:
yfinance,ta,fredapi



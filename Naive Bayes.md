## 假設每個特徵都是相互獨立的，透過計算，可以知道哪個目標的發生機率最大 
## 公式 : P(A|B) = P(B|A) * P(A) / P(B)
## 原理
### 單純貝氏(離散變數)
1. 假設有一筆資料包含天氣、溫度以及活動，如果要判斷晴天以及溫度適中是否適合舉行活動
2. 先找出舉行活動的機率 P1 和取消的機率 P2，再找出P3(天氣晴|取消)，P4(溫度適中|取消)，P5(天氣晴|舉行)，P6(溫度適中|舉行)
3. P(取消|天氣晴，溫度適中) = P(取消)P(天氣晴|取消)P(溫度適中|取消) = P2 * P3 * P4 = p7
4. P(進行|天氣晴，溫度適中) = P(進行)P(天氣晴|進行)P(溫度適中|進行) = P1 * P5 * P6 = P8
5. 比較後驗機率 P7 與 P8 來決定是否要舉行活動，取最大後驗機率
6. P7 / (P7 + P8) 為真正的機率
### 高斯貝氏(連續變數)
* 藉由假設變數為常態分配的情況下，以樣本的資料的標準差及變異數來計算機率
## Python Package
1.      from sklearn.naive_bayes import GaussianNB, MultinomialNB, BernoulliNB(二元分類)
2.  Parameters :
    * GaussianNB()
      * var_smoothing : 添加到方差中的一個小常數，防止除以零
    * MultinomialNB()
      * alpha：防止某些特徵概率為零
    * BernoulliNB()
      * alpha
      * binarize：用於將數據二值化
  
## Reference
https://ithelp.ithome.com.tw/users/20107247/articles?page=5    

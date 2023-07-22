# Category Classfier

"Category Classifier" is a machine learning capable of performing multi-class classification.

# Background

When managing household expenses using mobile app, there are features available that allow users to classify their expneditures into different categories for easier tracking. 

However, manually inputting each category for every operation can be cumbersome. As a solution, I embarked on creationg a system that automativally classifies categories based on the recipient and payment amount provided.

# DEMO

### Training Data (Partial excerpt):
　　　
    Recipient 　Payment Amount　 Category ID
    
    etc sapporominami    910.0       7

                  bag  10510.0       8
                  
                 milk    200.0       1
                 
    convenience store   1608.0       1
    
    convenience store   1288.0       1
    
                 ...      ...     ...
                 
              　eneos    623.0       7
               
           　zozotown   7140.0       8
            
            rakuten pay noma   3520.0       8
    
     　     skyticket  26680.0       6
           


### Test Data:

          Recipient    Payment Amount
          
           etc kunimi    870
           
                milk    200
                
                convenience store   1608
   
                rent  50000
                
               water   5000
               
              ticket   7000
              
              kitaka   1490
              
           chocolate    500
           
           sumika ticket   8000
        
     oneokrock ticket  10000
     
        seven eleven    300
        
         family mart    500
         
            any café   2000
            
               pizza   3000
               
            zozotown   5000
            
           mini stop    300
           
                book   1000
                
             spotify   1440


             

### Category:

1: Grocery bills

2: Housing costs

3: Utilities


4: Telephone bill

5: Daily necessities costs

6: Leisure costs

7: Transport ation cost

8: Clothing costs


### Result for prediction:

[7 1 1 2 3 6 1 1 6 6 1 1 1 1 8 1 6 6 1]

# Features

Implementation in Python with scikit-learn.




* Algorithm : Random Forest

* Analyzer : Janome (Japanese morpthological analyzer)

* Vectorizer : TF-IDF Vectrizer





#### Training data : 100 entries of actual household account app history and credit card statements(past 6 months). ※private data





#### Test data : 20 entries (excerpt) from the same sources as the training data.





#### Algorithm (Random Forest):



1, Generate some decision trees from the original dataset.

2, Ganerate some decision trees from different subsets of the data.

3, Randomly select some features from the some available features.

4, Take the majority vote from the some decision trees as the final prediction.




# Requirement

* Python 3.10.6
* Janome-0.5.0-py2.py3-none-any.whl

Environments under Google Colaboratory is tested.


# Installation

Install janome with pip command.

```bash
!pip install janome
```

# Evaluation

To improve accuracy, it is considerd necessary to have a large training dataset that covers a wide range of words comprehensively. However, for personal use within a limited scope, this model may still be practical, as people tend to use  expenses within their regular routines and not do drastically different shopping.


Detail:

* When the same word was included, the classification worked well.
* When sendin words that were not included in the training data, it seemed that the payment amount took precedence ford the classification.

# 要約
「カテゴリ分類器」は、他クラス分類ができる機械学習です。

#### --- 背景 ---

　アプリで家計簿をつけるにあたって、支出や支払先、カテゴリを入力して、カテゴリ別に一覧を見ることができる機能があります。

　しかし、いろいろな項目を入力する手間が面倒に感じ、何度も家計簿をつける習慣を続けることができませんでした。そこで、最低限の入力で、カテゴリを自動で振り分けることができれば、手軽に家計簿をつけられるのではないかと思いつき、このカテゴリ分類器の作成に取りかかりました。

#### --- 実装 ---

　python、scikit-leanで実装し、

 アルゴリズムは Random Forest、

 analyzerとして、janome、

 vectorizerとして、TF-IDF vectrizerを使用します。

 * 教師データ：個人使用の、家計簿アプリの履歴100件、クレジットカード利用明細（過去6か月）
 * テストデータ：同上　20件（抜粋）

#### --- 評価 ---
　精度を高めるためには、ワードを網羅的に学習させる必要があり、大きな教師データを用いるべきだと考えられます。

 しかし、個人使用の範囲内であれば、支出のイレギュラーは極めて少ないと考えられるので、実用可能なシステムだと評価します。




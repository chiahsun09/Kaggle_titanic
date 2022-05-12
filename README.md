# Kaggle_titanic

結論:

#選用特徵13個: 
'Pclass', 'Sex', 'Age', 'Fare', 'Cabin', 'Embarked', 'Family', 
'Title', 'Sex_Pclass', 'Age_Range', 'Alone', 'Ticket_info', 'Fare_Range'

#特徵處理:
'Pclass':無需處理

#'Sex':
1.新增Sex_Pclass欄位,依據在不同艙等中的男女性生存率，給予不同的生存率級別(3最高、1最小),
2.'Sex'作權重編碼

#'Age':
1.利用每個 Title 的年齡平均數，填補每個 Title 所對應 Age 的缺漏值,
2.有新增Age_Range，測試過後，應可捨棄'Age',測試後模型效果不好,故保留
3.Age作常態化處理,
4.Age,Age_Range作權重編碼

#'Fare':
1.新增'Fare_Range'欄位,應可捨棄'Fare',測試後模型效果不好,故保留。
2.Fare因有離群值,作常態化處理
3.Fare_Range作權重編碼


#'Cabin':作權重編碼

#'Embarked':作權重編碼

#新增'Family':'SibSp'+'Parch'

#'Title':
1.由Name而來,分為'Mr', 'Mrs', 'Miss', 'Master', 'Rare', 'the Countess'
2.作權重編碼

#'Sex_Pclass:同'Sex'步驟

#Age_Range:同'Age'步驟

#'Alone':新增是否獨行欄位

#'Ticket_info':由Ticket處理而來,作權重編碼

#'Fare_Range':同'Fare'步驟


#模型選用:
使用LogisticRegression()

#超參數:
C=162.6536408785796,multi_class='multinomial', penalty='none',solver='newton-cg', tol=1e-06



#其模型準確率約84%
#上傳後最佳成績得到了Score: 0.77272,
#看到有人是100分?太神奇了,要繼續努力!!

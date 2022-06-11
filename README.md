# Fraudulent-Transactions-Analysis


## Context
It is important that finance companies are able to recognize fraudulent transactions so that customers are not charged for items that they did not purchase.


## Content
The datasets contains transactions made by customers of a finance company. This dataset presents transactions that occurred in some days, where we have 8213 frauds out of 63,62,619 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.129% of all transactions.

It contains not only numerical input variables but also sum categotical variables as well. The dataset has columns as Step, type, amount, nameOrig, oldbalanceOrg, newbalanceOrig, nameDest, oldbalanceDest, isFraud, isFlaggedFraud which indicated to perticular features and all of them are also mentioned below.

**step** maps a unit of time in the real world. In this case 1 step is 1 hour of time. Total steps 744 (30 days simulation).

**type** CASH-IN, CASH-OUT, DEBIT, PAYMENT and TRANSFER.

**amount** amount of the transaction in local currency.

**nameOrig** customer who started the transaction

**oldbalanceOrg** initial balance before the transaction

**newbalanceOrig** new balance after the transaction

**nameDest** - customer who is the recipient of the transaction

**oldbalanceDest** - initial balance recipient before the transaction. Note that there is not information for customers that 
start with M (Merchants).

**newbalanceDest** - new balance recipient after the transaction. Note that there is not information for customers that start with M (Merchants).

**isFraud** - This is the transactions made by the fraudulent agents inside the simulation. In this specific dataset the fraudulent behavior of the agents aims to profit by taking control or customers accounts and try to empty the funds by transferring to another account and then cashing out of the system.

**isFlaggedFraud** - The business model aims to control massive transfers from one account to another and flags illegal attempts. An illegal attempt in this dataset is an attempt to transfer more than 200.000 in a single transaction.



## Exploratory Data Analysis

Talking about any null or missing values in the dataset, I would say that there were no missing or NaN values in the raw dataset. Also, from the descriptive statistics of our dataset we could clearly see that our data is wide spread, i.e is having high variance. At this point, I could guess that the dataset might be unbalanced and would require undersampling in order to train our machine learning model well. 
Moving forward with the Exploratory data analysis, we encountered the unbalanced characteristic of our dataset, we also analysed the presence of fraudulent transactions deeply for different types of transactions in order to get more clarified and proper view of how data is present. After this, I filtered the dataset by dropping the column which were not contributing significantly in providing any fruitful information for our model, such as “nameOrig” and “nameDest”. 
Moving forward, I analysed the pattern of transactions for both fraudulent transactions and genuine/valid transactions. I did this by checking the balance in the account of both the sender and the receiver before and after the transaction on a condition that the amount given is less than or equal to the amount that is in the sender's account.
and, the amount received is less than or equal to the amount that is in the receiver's account. I found that,

Number of observations where the amount given is greater than the amount that is in the sender's account:  4079080

Number of observations where the amount given is greater than the amount that is in the sender's account:  4079080

After getting these results, for double checking of fraudulent transactions or can say getting one more feature to analyse the transaction being valid or fraud, I checked for error balance in the accounts, and found that 

Percentage of observations with balance errors in the account giving money:  85.0

Percentage of observations with balance errors in the account receiving money:  74.0

And thus, from such outcomes I was able to conclude that
1.	There is erroneous results in the new and old balance accounts for both sender and receiver
2.	Some of this erroneous results are due to fraudulent transactions
3.	We cannot get rid of this features as well so we will let them be and add a new feature called 'errorbalance’


After adding these feature I went to check the time of a day when fraudulent transaction happen. By visualizing the data against time, I found that from hour 0 to hour 9, valid/genuine transactions very rarely occur. On the other hand, fraudulent transactions still occur at similar rates to any hour of the day outside of hours 0 to 9.
And that is why I added the hours of a day feature into our data set as a column. 


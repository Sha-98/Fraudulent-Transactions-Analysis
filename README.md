## Fraudulent-Transactions-Analysis

### Context
It is important that finance companies are able to recognize fraudulent transactions so that customers are not charged for items that they did not purchase.


### Content
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

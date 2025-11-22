# HCL-NOV22-java-backend-repo
HCL NOV22 java backend repo , e-wallet application

Database Design

1. CustomerDetails
    feilds  -> cust_id , cust_name , mail , phone , account_id(foreign key)
   
2. AccountDetails
    fields  -> account_id , amount , currency
   
3. Products
   fields  -> product_id , product_name , product_description cost , Quantity , merchant_id(foreign key)
   
4. Merchant
     fields -> merchant_id, merchant_name  , amount , currency

5. TransactionLog
     fields  -> timestamp , userid , product id , product name , quantity , amount , merchant_id
   

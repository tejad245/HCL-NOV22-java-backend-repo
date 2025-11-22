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
   


Base URL: /api/wallentApi

@GetMapping
/user/fetchUserDetails/userid

respose
{
userid : 322,
username : ssss,
accout balance : 10000
}

---------------------
@GetMapping

/product/getALlproducts

response
{
product id : 1,
product name : mobile,
prouct cost : 2000,
Quantity : 2
},
{
product id : 1,
product name : mobile
}

-----------------------
@GetMapping
/product/getProductbyId/1

response
{

}

------------------------
@postMapping
/user/placeOrder(@RequestBody dto){}

Request :
 new DTO(String userid,String product id,Long quantity)

Response:
{
Product name : "dfs";
amount : 334,
message : "Success"
}

Steps to follow :
1. Validate the product quantity as well as request quantity.
2. Validate the user currency if requires need to do conversion calculation based on merchant preference
3. calculate total product amount (Quantity * cost)do the necessary validation and throw the exception.
4.once the user is allowed perform the transaction debit with user account and credit in merchant account, if needed need to do OTP verification from user.
5.after successful transaction need to update details in transaction table with details.

-------------------------
@PostMapping/
/notification/ @RequestBody 
RequestBody{
user id: 4343,
transaction id :4324343
}

ResponseBody{
 message : "Success"
}
6.notification mail should be shared to merchant with txn details.
/transaction/sendEmail

-------------------------

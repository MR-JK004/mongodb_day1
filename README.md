**MongoDB Day 1 Tasks**
This document provides a summary of the MongoDB tasks completed on Day 1. The tasks include creating a database, inserting products, and executing various queries to manipulate and retrieve data from the database.

**Setup**
Create the Database
To create and switch to a new database named guviTask, use the following command:

- use guviTask

**Insert Products**
Insert the provided products into the guviTask database. Use the following command to insert multiple products:

db.users.insertMany([ Product JSON here… ])

**Queries**
Below are the queries executed for various tasks:

1.	Find all the information about each products
Ans : db.users.find()

2.	Find the product price which are between 400 to 800
Ans : db.users.find({
  	      	product_price: { 
   			 $gte: 400, 
    			 $lte: 800 
 			}
})


3.	Find the product price which are not between 400 to 600
Ans : db.users.find({
  		product_price: {
    			$not: {
      		$gte: 400,
      		$lte: 600
    			}
  		    }
})

4.	List the four product which are greater than 500 in price 
Ans : db.users.find({
product_price:{
			$gt:500
}
}).limit(4)

5.	Find the product name and product material of each products
Ans :  db.users.find({},{
			product_name:1,
			product_material:1,
   })

6.	Find the product with a row id of 10
    Ans : db.users.find({id:"10"})



7.	Find only the product name and product material
Ans : db.users.find({},{
			_id:0,
			product_name:1,
			product_material:1,
   })

8.	Find all products which contain the value of soft in product material 
Ans : db.users.find({product_material:"Soft"})

9.	Find products which contain product color indigo  and product price 492.00
Ans: db.users.find({product_color:"indigo",product_price:492})

   10.Delete the products which product price value are 28
    Ans : db.users.deleteMany({product_price:28})


Notes
Replace Product JSON here… with the actual JSON data for the products.
Ensure that the field names and values in the queries match the structure and data types of your actual documents.




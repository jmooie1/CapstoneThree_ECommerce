# Product Management System 

This project that we have been working on is a product management system that was built with Spring Boot. It includes a search functionality and CRUD 
(Create, Read, Update and Delete) operations for products. 

## Table of Contents
- Setup
- Usage
- Phase 1
- Phase 2 
  Bug 1: Product Search
  Bug 2: Product Duplication

# Setup 
Prerequisites
- Needs to be Java 11 or higher
- Maven
- Needs MYSQL

# Usage
Endpoints -
- GET '/products' - Get all products
- GET '/products' - Get product by ID
- POST /products - Add a new product
- PUT /products/{id} - Update an existing product
- DELETE /products/{id} - Delete a product

# Example would be like this
POSTMAN 
http://localhost:8080/products/3
{
    "productId": 3,
    "name": "Headphones",
    "price": 99.99,
    "categoryId": 1,
    "description": "Immerse yourself in music with these high-quality headphones.",
    "color": "White",
    "stock": 100,
    "imageUrl": "headphones.jpg",
    "featured": true
}

# Phase 1 

In Phase 1, I implemented the CRUD (Create, Read, Update and Delete) operations and search functionality for the products.
The endpoints REST methods that are needed for Phase 1 are shown below as well such as 

GET http://localhost:8080/categories NO body: 

GET http://localhost:8080/categories/1 NO body:

POST http://localhost:8080/categories Category: 

PUT http://localhost:8080/categorids/1 Category:

DELETE http://localhost:8080/categorids/1 NO body:


# CategoriesController Implementation

The 'CategoriesController' provides endpoints for managing product categories. It allows users to retrieve categories and products within a category 
and admins are able to add, update, or delete categories.

![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/707dba0b-83c5-46b0-9f15-d4033b2c05b6)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/46e5d968-032d-4ded-9b55-ad394d62923f)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/cb7dabdf-4ab6-4b0a-afd1-9da1fcfbc6d6)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/15380363-0ad0-45a6-ae02-525bfc4a5294)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/42dc1109-7d95-4da6-8d10-a50c3b921012)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/6091094c-8bcb-41ad-9c48-3631d050a21a)



![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/c4f31c16-07d8-4dcf-b66a-0b26fdce5d7c)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/b2942c68-14a7-475b-9c36-a66ebfdf6a93)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/c94eb540-19ad-4329-925e-cbab4afe52d4)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/d00ba93d-8e08-418d-b40c-7d31399c8b6c)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/0299ddc8-5245-475e-9033-f86faa7103f1)


# Phase 2 

In Phase 2, I focused on fixing bugs that was in the website. I also had to do figure out ProductsController on Postman.

![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/7e300b4b-102e-49bb-a894-026b75653407)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/93b4d96a-fcfb-4c93-836e-a0bdbf6f811c)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/63711f82-7b7e-4aa6-af9c-457eb82da64e)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/3a057efd-33c4-4111-a1f8-1f387b89faab)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/868fcd2f-3314-455b-bffd-a95746f0ca95)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/7b609c8c-6b2e-43da-9461-ca72a1b864b2)


# Bug 1: Product Search

The issue was that users reported incorrect results when trying to use the product search functionality. 
The minimum price slider was not working. 

![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/e4a3c692-028d-4a5e-8bc6-c2113dc587a8)

The solution to this is that the 'search' method in 'MySqlPproductDao' was reviewed and looked over to handle the search parameters.

![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/c3bcf2e6-c6fc-411a-9b36-4074a7e1fe61)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/8fae42c6-a5bb-4aa9-8133-8017acfcde22)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/4c465089-c326-40e0-8232-5845f323f5d5)

# Bug 2: Product Duplication

The issue here is that users reported that products appeared duplicated after updates, instead of being updated.

The soulution here was, The 'update' method in 'MySqlProductDao' was verified to ensure that it correctly updates the existing products. Also, the 
'updateProduct' method in 'ProductsController' was confirmed to properly call the 'update' method in 'ProductDao';

## Postman Results and website results
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/3a057efd-33c4-4111-a1f8-1f387b89faab)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/f68fcb3b-e273-4aaa-bcc7-7bb3a62ac3cd)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/3928dbb3-f6b5-42e2-897f-f50f2c0a1fc5)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/ab1c7d82-058e-4d66-8d3b-e2451191dd6b)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/bd11c429-066b-426c-bab8-0beb663fe9ad)


![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/4d82dc36-0058-4db7-a92e-0d5a4bae9d83)
![image](https://github.com/jmooie1/CapstoneThree_ECommerce/assets/166542491/8b0ca7aa-6650-4ac3-b522-d020778c30ea)







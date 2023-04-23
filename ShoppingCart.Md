


## 1. Creating a Database 
### Login-Register Database
- Navigate to http://localhost/phpmyadmin/
- Click the Databases tab at the top
- Under Create database, type in login-register in the text box
- Select utf8_general_ci as the collation (UTF-8 is the default encoding in HTML5)
- Click Create
![image](https://user-images.githubusercontent.com/68326118/233860552-c4d78e88-de83-4d0d-a3e3-d94cbf756ef2.png)

### 2. Before creating the shopping cart page we first need to create a registration and login page for the users.
- If the user is new to the shopping site then the user should register with field as username, email address, password.

### The Registration Page
![image](https://user-images.githubusercontent.com/68326118/233861915-2ec0291c-9e6c-425a-be9b-098203b02ff0.png)
- If the user has already registered then the user choose login enter the login detials and upon succesful login detial validation the user 
will be directed to the shopping page.

### Login Page
![image](https://user-images.githubusercontent.com/68326118/233861967-69be32a0-aa99-4d0f-a0ba-818e49782b00.png)
- If the user enters the login credentials the user will not be loged in instead will be asked to go to the login page again.

### redirect Page
![image](https://user-images.githubusercontent.com/68326118/233862166-1b444f6e-861d-4a45-b45b-26b92c967b17.png)

## 1. Creating a Database 
### Shopping Cart Database
- Navigate to http://localhost/phpmyadmin/
- Click the Databases tab at the top
- Under Create database, type in shoppingcart in the text box
- Select utf8_general_ci as the collation (UTF-8 is the default encoding in HTML5)
- Click Create
![image](https://user-images.githubusercontent.com/68326118/233860539-fb0bab8d-5ccc-43b1-965b-cbe11eb3cd32.png)
## 2. Designing shopping cart system with css
 - Used to design a responsive web and the code for this is stored under file name - style.css in below folder
`C:\xampp\htdocs\login-register`

## 3. Creating a functions file
- This contains all the functions which we use in our shopping website which contains template header, footer and database connection functions making the user to connect easily 
  with database.
  
## 4. Creating the index file
- Its a main file that access all our pages. Here we setup the `GET`-request to dertimine the pages.

`<?php
session_start();
include 'functions.php';
$pdo = pdo_connect_mysql();`

- Here the session_start will create the session, which helps to store the products that are added to the cart and connects to the mysql db.

## 5. Creating a Home Page
- This will execute a SQL query to retrieve the four most recently added products from our database. All we have to do with this query is ORDER BY the date_added column and limit the number of results by 4 and
store the result in the $recently_added_products variable as an associated array. Here we add a homepage template also.
### The shopping page
![image](https://user-images.githubusercontent.com/68326118/233861218-cd9e0876-bbfb-4331-8fbe-e989983cbf85.png)

## 6. Creating the Products Page
- The products page will be where our customers will go to browse all of our products. We will limit the number of products to show on each page and
add pagination that will allow the customers to navigate between pages.
- `$num_products_on_each_page` variable will limit the number of products to show on each page.

![image](https://user-images.githubusercontent.com/68326118/233861293-3dada4ee-4609-497f-aac4-b892564bc616.png)

## 7. Creating the Product Page
- The product page will display all details for a specified product, determined by the GET request ID variable. Customers can view the price, image, and description. 
The customer will be able to change the quantity and add to cart with a click of a button. 
### The particular product page 
![image](https://user-images.githubusercontent.com/68326118/233861471-2759e8d3-8efa-453b-8fa5-2d28c7a1949c.png)

## 8.Creating the Shopping Cart Page
- Here the customer will be able to see a list of their products added to the shopping cart. 
They will have the ability to remove products and update the quantities. Here we have different codes to remove , app or update product quantities in the cart.
- After adding product to the cart we can place the order by getting the products in the cart and select from the database.
### The shopping cart
![image](https://user-images.githubusercontent.com/68326118/233861667-3e2af098-2682-495c-8c91-130047e6feff.png)
- And now when we place the order we get the below page
![image](https://user-images.githubusercontent.com/68326118/233861755-2407ac6a-54cd-4bdc-9868-855626e4c1f4.png)







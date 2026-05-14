FirstRespAPI
A simple REST API built with Java and Spring Boot. It allows you to create, read, update and delete products.

How to run the application

Open the project in IntelliJ IDEA
Run FirstRespApiApplication.java
Open your browser and go to http://localhost:8080


Swagger UI
You can test all the endpoints using Swagger UI:
http://localhost:8080/swagger-ui/index.html

<img width="1920" height="1080" alt="Screenshot 2026-05-14 at 22 05 41 (2)" src="https://github.com/user-attachments/assets/53198920-5c77-4c11-82ff-6678f9f48a91" />

Endpoints
MethodURLWhat it doesPOST/api/v1/productsCreates a new productGET/api/v1/products/{id}Gets a product by IDGET/api/v1/productsGets all productsPUT/api/v1/products/{id}Updates a productDELETE/api/v1/products/{id}Deletes a product

Creating a product (POST)
Send a POST request to http://localhost:8080/api/v1/products with this body:
json{
  "name": "First product"
}
Response:
json{
  "id": 1,
  "name": "First product"
}

<img width="1710" height="1107" alt="Screenshot 2026-05-14 at 22 09 11" src="https://github.com/user-attachments/assets/28453af5-b872-43e3-bfdd-81be5d549431" />


Getting a product (GET)
Send a GET request to http://localhost:8080/api/v1/products/1
Response:
json{
  "id": 1,
  "name": "First product"
}

Updating a product (PUT)
Send a PUT request to http://localhost:8080/api/v1/products/1 with this body:
json{
  "name": "Updated product",
  "id": 1
}

Deleting a product (DELETE)
Send a DELETE request to http://localhost:8080/api/v1/products/1
Response: 204 No Content

Error handling
If you request a product that does not exist you will get:
json{
  "message": "Product with 999 not found"
}

Database
The application uses an H2 in-memory database. You can view it at:
http://localhost:8080/console/
Set the JDBC URL to jdbc:h2:mem:testdb and click Connect.

<img width="1710" height="1107" alt="Screenshot 2026-05-14 at 22 10 25" src="https://github.com/user-attachments/assets/88db4760-a9e9-4efe-aba1-fb4807a348c1" />

You can run SQL queries like:
sqlSELECT * FROM PRODUCTS;
<img width="1710" height="1107" alt="Screenshot 2026-05-14 at 22 11 17" src="https://github.com/user-attachments/assets/5d32b75b-c707-4078-8067-911626ccd24f" />

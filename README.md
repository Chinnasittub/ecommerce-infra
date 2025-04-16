# Ecommerce Microservices Infrastructure

This repository contains the infrastructure setup for the Ecommerce Microservices project using Docker Compose.

It includes:

- RabbitMQ (for message communication)
- PostgreSQL (for each service database)
- Three microservices:
  - `user-service`
  - `product-service`
  - `order-service`

---

## Project Structure
ecommerce-infra/ 
  - EcommerceSln.sln
  - docker-compose.yml 
  - user-service/ 
  - product-service/ 
  - shared-library/ 
  - order-service/

Each service is in its own GitHub repository and should be cloned into the correct folder.

---

## How to Clone All Projects

1. Clone this infrastructure project:
   git clone https://github.com/Chinnasittub/ecommerce-infra.git

2. Clone the microservice projects into their folders:
git clone https://github.com/Chinnasittub/ecommerce-user-service.git 
git clone https://github.com/Chinnasittub/ecommerce-product-service.git 
git clone https://github.com/Chinnasittub/ecommerce-shared-library.git 
git clone https://github.com/Chinnasittub/ecommerce-order-service.git 

3. Your folder should look like this:
  - EcommerceSln.sln
  - docker-compose.yml 
  - user-service/ 
  - product-service/ 
  - shared-library/ 
  - order-service/

## How to Run the Project
Make sure you have Docker and Docker Compose installed.
    docker-compose up --build

This will start all services.
  - RabbitMQ UI: http://localhost:15672
  - User Service: http://localhost:5031
  - Product Service: http://localhost:5032
  - Order Service: http://localhost:5033

## Notes
PostgreSQL ports are mapped to:
  - postgres_user: 5443
  - postgres_product: 5444
  - postgres_order: 5445
  - RabbitMQ uses default user: guest / guest

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
  - ecommerce-frontend

Each service is in its own GitHub repository and should be cloned into the correct folder.

---

## How to Clone All Projects

1. Clone this infrastructure project:
   git clone https://github.com/Chinnasittub/ecommerce-infra.git

2. Clone the microservice projects into their folders:
  - git clone https://github.com/Chinnasittub/ecommerce-user-service.git 
  - git clone https://github.com/Chinnasittub/ecommerce-product-service.git 
  - git clone https://github.com/Chinnasittub/ecommerce-shared-library.git 
  - git clone https://github.com/Chinnasittub/ecommerce-order-service.git 
  - git clone https://github.com/Chinnasittub/ecommerce-frontend

3. Your folder should look like this:
  - EcommerceSln.sln
  - docker-compose.yml 
  - user-service/ 
  - product-service/ 
  - shared-library/ 
  - order-service/
  - ecommerce-frontend/

## How to Run the Project
  ### Prerequisites

  1. **Ensure Docker is Installed**
    - **Check if Docker is installed:**
      ```sh
      docker --version
      ```
      If Docker is installed, this command will display the version.
    - **Install Docker:**
      - Download Docker Desktop from [Docker's official website](https://www.docker.com/products/docker-desktop).
      - Follow the installation instructions for your operating system.

  2. **Ensure .NET SDK is Installed**
    - **Check if .NET is installed:**
      ```sh
      dotnet --version
      ```
      If .NET is installed, this command will display the version.
    - **Install .NET SDK:**
      - Download the latest .NET SDK from [Microsoft's .NET download page](https://dotnet.microsoft.com/download).
      - Follow the installation instructions for your operating system.

  ### Steps to Run the Project

1. **Start Docker**
   - Open Docker Desktop and ensure it is running.

2. **Build and Start All Services**
   - Run the following command in the project root directory:
     ```sh
     docker-compose up --build
     ```

3. **Apply Database Migrations**
   - Navigate to each service folder (../Ecommerce_microservices_project/user-service, ../Ecommerce_microservices_project/product-service, ../Ecommerce_microservices_project/order-service) and run:
     ```sh
     dotnet ef database update
     ```
     This will create the necessary databases for each service.

### Access the Services
This will start all services.
  - RabbitMQ UI: http://localhost:15672
  - User Service: http://localhost:5031
  - Product Service: http://localhost:5032
  - Order Service: http://localhost:5033
  - Front-end: http://localhost:5000

## Notes
PostgreSQL ports are mapped to:
  - postgres_user: 5443
  - postgres_product: 5444
  - postgres_order: 5445
  - RabbitMQ uses default user: guest / guest

## How to Use the Website

1. **Access the Website**
   - Open your browser and go to [http://localhost:5000](http://localhost:5000).

2. **Navigate Through the Services**
   - All services are listed in the left-side menu.

   - **User Management**
     - This page displays all registered users.
     - You can manage users (e.g., add, edit, or delete users) on this page.

   - **Product Management**
     - This page displays all available products.
     - You can manage products (e.g., add, edit, or delete products) on this page.

   - **Order Management**
     - This page displays all orders.
     - To create a new order:
       1. Select a registered user.
       2. Select a product.
       3. Specify the order quantity.
       - Note: The product quantity will be reduced based on the order quantity.

Enjoy managing your ecommerce platform!

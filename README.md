# Microservices Obsservability - Practical Implementation (Spring Boot + MySQL + Redis + Kafka + Zipkin)
 Microservice Observability and the practical implementation with real time use case.
 
 YT Playlist - https://youtube.com/playlist?list=PLq3uEqRnr_2Ff6PD8lJNihIuX1ymhXUNB&si=kWQywJjkgiA2trRv

 ## Distributed Tracing

 ### [Sneak Peak into the tracing demo](https://youtu.be/jx_-0qfn-hc?si=-rjxkQVj7BceFghw)
 ### What are we going to build? Complete Road map!

 * [sequence diagram](https://www.plantuml.com/plantuml/uml/XPB1JiCm38RlVWgpEo_00KtQ2S5WgEe3cDGTKTS4ETwalZtfqcg5fShL-JxxZ-LjK18zzoTuq6_k6RzEPpuA3H0wwr1yO22ZNh0E0b075dnynWzfM2gMYpNyX3jXKav5M3xTevLwcKYC_VT3zVbsfxnIsr5asJMuIMmQqMnmpo7GaG6kq4WVQEZPwJnYrVZBvSo3U1FXkNupyiccPznvrrhfIQrtkO0lxX8nByCygAJ-5_9Dwf-6bCUDckwsomMNJvtu96Vt-UxLjjPSCnMNchVA_opBwqapzDXalCtfaqi2jh4I3_mN)

### Important concepts about distributed tracing

* Opentelemetry
* Brave
* TraceId / SpanId / TraceParent
* W3C Context
 
 ### Kafka Setup
 * Cluster
 * Topics
   * order-topic
   * payment-topic
   * inventory-topic
 * Monitoring

Command to start the zookeeper
```
bin\windows\zookeeper-server-start.bat config\zookeeper.properties
```

Command to start the kafka
```
bin\windows\kafka-server-start.bat config\server.properties
```

Commands to create the Kafka topics on your local machine (Windows):  

```sh
bin\windows\kafka-topics.bat --create --topic order-topic --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1

bin\windows\kafka-topics.bat --create --topic payment-topic --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1

bin\windows\kafka-topics.bat --create --topic inventory-topic --bootstrap-server localhost:9092 --partitions 3 --replication-factor 1
```

Command to list the kafka topics

```
bin\windows\kafka-topics.bat --list --bootstrap-server localhost:9092
```
 ### MYSQL DB Setup
 * DB Setup
 * DB Creation
 * Tables
   * order_info
   * payment_info
   * inventory_info
   * notification_info
 
 Here are the SQL commands to create tables for each service in MySQL, with fields tailored to the example scenario.
 
 **Create database and use that**
 ```sh
CREATE DATABASE IF NOT EXISTS observability;

USE observability;
```

 **1. Order Table**
Stores details of each order in the **Order Service**.

```sql
CREATE TABLE orders (
    order_id VARCHAR(50) PRIMARY KEY,
    user_id VARCHAR(50) NOT NULL,
    product_id VARCHAR(50) NOT NULL,
    quantity INT NOT NULL,
    total_price DECIMAL(10, 2) NOT NULL,
    status VARCHAR(20) DEFAULT 'PENDING',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

 **2. Payment Table**
Stores details of each payment in the **Payment Service**.

```sql
CREATE TABLE payments (
    payment_id VARCHAR(50) PRIMARY KEY,
    order_id VARCHAR(50) NOT NULL,
    user_id VARCHAR(50) NOT NULL,
    amount DECIMAL(10, 2) NOT NULL,
    payment_method VARCHAR(20) NOT NULL,
    status VARCHAR(20) DEFAULT 'PENDING',
    processed_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (order_id) REFERENCES orders(order_id)
);
```

 **3. Inventory Table**
Stores stock details of each product in the **Inventory Service**.

```sql
CREATE TABLE inventory (
    product_id VARCHAR(50) PRIMARY KEY,
    quantity INT NOT NULL,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```

 **4. Notification Table**
Stores details of each notification sent in the **Notification Service**.

```sql
CREATE TABLE notifications (
    notification_id VARCHAR(50) PRIMARY KEY,
    user_id VARCHAR(50) NOT NULL,
    message TEXT NOT NULL,
    type VARCHAR(20) NOT NULL,
    sent_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Redis Setup
* Installation
* Interacting with CLI

  Detailed guide is here - [link](https://github.com/codefarm0/observability/blob/main/redis-installation.md)
  
 ### Order Microservice
 * Tech Stack --> Spring Boot + MYSQL + Kafka + Redis
 ### Payment Service
  * Tech Stack --> Spring Boot + MYSQL + Kafka
 ### Inventory Service
  * Tech Stack --> Spring Boot + MYSQL + Kafka + Redis
 ### Notification Service
  * Tech Stack --> Spring Boot + MYSQL + Kafka
 ### Zipkin Setup
 * Local Setup
 * DB Integration for persistence
 ### Complete Demo
 * Final demo with all the pieces connected
 * Postman Collection for interaction with API
 * API and contracts Documentation for reference
 * Chat GPT page - https://chatgpt.com/share/67308fa0-bef0-800e-b1d5-bc183d6c0001
 ### Next Steps
 * What next?
 

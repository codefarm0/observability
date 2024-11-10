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

 ### MYSQL DB Setup
 * DB Setup
 * DB Creation
 * Tables
   * order_info
   * payment_info
   * inventory_info
   * notification_info

### Redis Setup
* Installation
* Interacting with CLI
  
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
 ### Next Steps
 * What next?
 

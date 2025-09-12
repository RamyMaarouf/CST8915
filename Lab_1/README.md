## Lab 1: Running Algonquin Pet Store on an Azure VM

1. Please find below the YouTube video link:

- https://youtu.be/4fewOSYlx_0

2. The short technical explanation:


- #### Order Service (Node.js)

    - **Responsibility:** Manages all customer orders. It takes a new order request from the front-end and queues it for processing.

    - **Language/Framework:** It's built using Node.js, which is a JavaScript runtime environment for server-side applications.

    - **Interaction:** It communicates with the Store Front via an API endpoint. After receiving an order, it sends a message to RabbitMQ to be consumed by other services (even though we only have the Order Service and Product Service running in this lab).

Product Service (Rust)

Responsibility: Handles all product-related data, including product listings, details, and inventory.

Language/Framework: It's written in Rust, a systems programming language known for its performance and memory safety.

Interaction: It provides product information to the Store Front through an API.

Store Front (Vue.js)

Responsibility: This is the user interface—the part of the application the customer interacts with to browse and place orders.

Language/Framework: It's built with Vue.js, a progressive JavaScript framework for building user interfaces.

Interaction: It calls the APIs of both the Product Service to fetch product data and the Order Service to submit customer orders.
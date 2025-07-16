# Restaurant Order Management - Multithreading Application

## Overview

This Java console application simulates a restaurant order management system using multithreading. It demonstrates the concepts of:

- **Multithreading**: Multiple threads run concurrently, simulating customers placing orders, kitchen staff preparing them, and delivery agents delivering the orders.
- **Producer-Consumer Pattern**: Orders flow through stages managed by separate threads communicating via thread-safe blocking queues.
- **Thread Synchronization**: Uses `ArrayBlockingQueue` from `java.util.concurrent` for safe exchange of data between threads.

## Components

- **Order**: Represents an order placed by a customer.
- **Customer (Producer Thread)**: Places orders into the `orderQueue`.
- **Kitchen (Consumer/Producer Thread)**: Takes orders from `orderQueue`, prepares them, and places them into `deliveryQueue`.
- **Delivery (Consumer Thread)**: Takes prepared orders from `deliveryQueue` and simulates delivery.

## How It Works

1. The `Customer` thread generates orders and puts them into the `orderQueue`.
2. The `Kitchen` thread retrieves orders from `orderQueue`, simulates preparation, then puts them into `deliveryQueue`.
3. The `Delivery` thread retrieves prepared orders from `deliveryQueue` and simulates delivering them.
4. The program uses blocking queues (`ArrayBlockingQueue`) to ensure thread-safe communication and proper synchronization.

## Running the Application

1. Ensure you have JDK 8 or higher installed.
2. Compile the Java file:


You will see console output tracing the lifecycle of orders from placement to delivery.

## Code File

`RestaurantMultithreadingApp.java` - Contains all classes and is executable as a standalone console Java app.

## Future Improvements

- Add GUI (e.g., using JavaFX) to visualize order flow.
- Implement thread termination and proper shutdown.
- Add order status tracking and statistics.
- Use thread pools for dynamic thread management.

## Author

DIBBO DUTTA
---

*This project serves as an educational example to demonstrate multithreading and producer-consumer design pattern in Java.*

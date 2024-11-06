# Kafka Script Examples

This repository contains a collection of scripts I created to learn and experiment with Apache Kafka. These scripts cover basic Kafka operations such as producing and consuming messages, setting up Kafka topics, and understanding how data flows through Kafka.

## Requirements

- **Apache Kafka**: Install and set up Kafka on your system. [Installation Guide](https://kafka.apache.org/quickstart).
- **Zookeeper**: Required by Kafka to manage brokers and maintain state.
- **Python**: Some scripts may use Python with the `kafka-python` library.
  - Install `kafka-python` using pip:
    ```bash
    pip install kafka-python
    ```

## Scripts Overview

### 1. Producer Script (`producer.py`)

- **Purpose**: Publishes messages to a specified Kafka topic.
- **How to Use**:
  ```bash
  python producer.py --topic <topic_name> --message "Your message here"
  ```
- Functionality:

  Connects to Kafka, creates a producer, and sends messages to the specified topic.
  Can be customized to send messages in batches or at set intervals.

### 2. Consumer Script (consumer.py)

- **Purpose**: Consumes messages from a specified Kafka topic.
- **How to Use**:
  ```bash
  python consumer.py --topic <topic_name>
  ```

- Functionality:

  Connects to Kafka, subscribes to the specified topic, and continuously listens for new messages.
  Prints each message as it is consumed from the topic.

### 3. Topic Setup Script (setup_topics.sh)

- **Purpose**: Automates the creation of Kafka topics.
- **How to Use**:
  ```bash
  ./setup_topics.sh <topic_name> <partitions> <replication_factor>
  ```

- Functionality:

  Runs Kafka commands to create topics with custom configurations.
  Allows specifying the number of partitions and replication factor.

## Getting Started
  
### 1. Start Zookeeper and Kafka  
  
  Zookeeper:
  ```bash
  bin/zookeeper-server-start.sh config/zookeeper.properties
  Kafka Broker:
  bin/kafka-server-start.sh config/server.properties
  ```
### 2. Run Scripts
  
  Producer: Use the producer script to send messages to a Kafka topic.  
  Consumer: Start the consumer to listen for messages on the topic.

  Example Workflow
  Create a topic using setup_topics.sh.
  Start a consumer on the topic.
  
  Use the producer to send messages, which should appear in the consumer’s output.
  
## Learning Notes

These scripts helped me understand:

  - The basics of Kafka’s publish-subscribe model.
  - How producers and consumers interact with topics.
  - Kafka's message distribution and partitioning features.

## Troubleshooting
    
- Broker Connection Issues: Ensure Kafka and Zookeeper are running and that your scripts point to the correct broker address.
- Dependencies: If using Python, make sure to install kafka-python.
  
##Resources
  
Kafka Documentation
kafka-python Library


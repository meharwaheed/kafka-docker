# Kafka Docker Compose

This repository provides a simple setup for running Apache Kafka using Docker Compose. Kafka is a distributed streaming platform that allows you to publish and subscribe to streams of records.

## Repository

[GitHub Repository](git@github.com:meharwaheed/kafka-docker.git)

## Prerequisites

Before you begin, ensure you have the following installed:

- [Docker](https://docs.docker.com/get-docker/) (version 20.10 or higher)
- [Docker Compose](https://docs.docker.com/compose/install/) (version 1.27 or higher)

## Getting Started

Follow these steps to set up and run Kafka with Docker Compose.

### 1. Clone the Repository

Open a terminal and run the following commands:

```bash
git clone git@github.com:meharwaheed/kafka-docker.git
cd kafka-docker
````

### 2. Run Kafka and Zookeeper
```bash
docker-compose up -d
```
### 3.bash Check docker containers
```
docker ps
```
### 4. Create Topics / Produce / Consume Messages

```bash
docker-compose exec kafka kafka-topics --create --topic your-topic-name --bootstrap-server localhost:9092 --partitions 1 --replication-factor 1
docker-compose exec kafka kafka-console-producer --topic your-topic-name --bootstrap-server localhost:9092
docker-compose exec kafka kafka-console-consumer --topic your-topic-name --from-beginning --bootstrap-server localhost:9092
```bash

### 5. Stop Kafka
```bash
docker-compose down
```

### 6. View Logs
```bash
docker-compose logs kafka
docker-compose logs zookeeper
```


### Notes:
- Make sure to replace `your-topic-name` with a specific topic relevant to your application.
- You can customize sections further based on any specific features or configurations in your `docker-compose.yml` file.

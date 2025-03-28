# RabbitMQ Message Queue Demo

A simple demonstration of message queuing using RabbitMQ, Node.js, and Docker.

## Prerequisites

- Docker
- Node.js
- npm

## Installation

1. Install dependencies:
```bash
npm install
```

2. Start RabbitMQ using Docker:
```bash
docker run -d --name rabbitmq \
    -p 5672:5672 \
    -p 15672:15672 \
    rabbitmq:4.0-management
```

This will:
- Run RabbitMQ in detached mode (-d)
- Name the container "rabbitmq"
- Map port 5672 (AMQP protocol)
- Map port 15672 (Management UI)
- Use the management version of RabbitMQ 4.0

## Usage

1. Start the receiver in one terminal:
```bash
node receive.js
```

2. Send the file name you want to fetch (Change base_url to desired folder on local device):

```bash
Ready to send messages. Enter filenames or "exit" to quit.
Enter filename to send (or "exit" to quit): 
```

3. Start the sender in another terminal:
```bash
node send.js
```

## Management Interface

Access the RabbitMQ management interface at:
- URL: http://localhost:15672
- Default username: guest
- Default password: guest

## Port Information

- 5672: AMQP protocol port
- 15672: Management UI port

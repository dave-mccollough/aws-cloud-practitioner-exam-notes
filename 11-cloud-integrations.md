# Cloud Integrations

## Amazon SQS

- Simple Queue Service
- Oldest AWS offering
- Fully managed service - use to decouple applications
- Scales from 1 message per second to 10,000s per second
- Default retention of messages - 4 days to maximum of 14 days
- No limit to how many messages can be in queue
- Messages can be deleted after they are read by consumers
- Low latency < 10ms on publish and receive
- Messages are FIFO

## Kinesis

- Real-time big data streaming
- Managed service to collect, process, and analyze real-time streaming data at any scale

## SNS

- Amazon SNS (Simple Notification Service)
- Allows you to send on message to many receivers
- Fully managed AWS service for sending messages from publishers (apps, users) to subscribers (email, SMS, Lambda, SQS queues, etc.) via topics
- Acts as a pub/sub messaging bus for application integration (A2A) and user notifications (A2P)
- Features includ: message filtering, ordering, archiving, and retries for reliable, scalable communication. 

## Amazon MQ

- Managed service broker for RabbitMQ and ActiveMQ
- Use for cloud migration use cases to avoid re-engineering application to use SQS or SNS
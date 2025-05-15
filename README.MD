## Module 9 Reflection
Ivan Jehuda Angi - 2306152222

---
### a. How much data will your publisher program send to the message broker in one run?

In one execution, the publisher sends 5 distinct AMQP messages to the broker. This is because it calls the `publish_event` function five times, and each call sends a message containing a Borsh-serialized `UserCreatedEventMessage`.

### b. What does the URL “amqp://guest:guest@localhost:5672” mean when used in both publisher and subscriber?

This URL serves as the connection string to the AMQP broker (like RabbitMQ). By using the same URL in both the publisher and subscriber programs, both are configured to:
- Use the AMQP protocol (`amqp://`)
- Log in with the username `guest` and password `guest`
- Connect to a broker running on the local machine (`localhost`)
- Communicate over port `5672`, the standard AMQP port

This ensures both the publisher and subscriber are connected to the same broker instance, allowing messages sent by the publisher to be received by the subscriber.

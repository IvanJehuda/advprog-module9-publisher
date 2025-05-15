[## Module 9 Reflection
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
### Running RabbitMQ as message broker
![Screenshot1](images/screenshot1.png)
### Sending and Processing Event
![Screenshot2](images/screenshot2.png)
![Screenshot3](images/screenshot3.png)


When RabbitMQ (the message broker) is up and running and we run both the Publisher and Subscriber programs using `cargo run`, the Publisher transmits data to the message broker, while the Subscriber retrieves it. As shown in the illustration, the Publisher sends the data one time, and the Subscriber successfully receives that data from the broker.
### Monitoring chart based on publisher
![Screenshot4](images/screenshot4.png)
In the image above, I executed the Publisher multiple times to noticeably boost the message rates. From this, I learned that sending data more often from the Publisher to the message broker increases the message rate. A high message rate indicates that the broker is handling a large amount of incoming data, which is reflected in the chart pattern.










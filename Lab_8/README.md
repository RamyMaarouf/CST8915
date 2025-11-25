**The YouTube demo video link**

https://youtu.be/xtkOLHBJHxs

**Solution Explanation of Task2**

- The initial MongoDB deployment was a single StatefulSet replica without persistence, making it unsuitable for production. The solution required migrating it to a Replica Set configuration. The solution implemented was:
  1. high availability -- The replicas field in the mongodb StatefulSet was increased from 1 to 3. This allows the instances to form a MongoDB Replica Set, providing data redundancy and automatic failover capabilities.
  2. persistent storage -- The volumeClaimTemplates block was added to the mongodb StatefulSet spec. This dynamically provisions a dedicated 8Gi Persistent Volume Claim (PVC) for each of the three replicas (mongodb-0, mongodb-1, mongodb-2).
  3. headless service: The mongodb Service was converted to a Headless Service by setting clusterIP: None. This is mandatory for a StatefulSet, as it assigns each replica a stable and unique DNS name, which is necessary for the members of the Replica Set to discover and communicate with each other.
 
- The initial RabbitMQ configuration suffered from message and queue loss upon Pod restart. The solution was to treat RabbitMQ as a stateful application and assign it persistent storage. The solution implemented was:
  1. persistent storage -- The rabbitmq StatefulSet was updated to include a volumeClaimTemplates block, requesting a 4Gi PVC. This ensures that queue definitions, message metadata, and persistent messages are safely stored on disk.
  2. config map retention -- The existing volume mount for the rabbitmq-enabled-plugins ConfigMap was retained, ensuring necessary management and Prometheus plugins are correctly loaded upon restart.

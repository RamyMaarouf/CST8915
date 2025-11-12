**The YouTube demo video link**


**Whether RabbitMQ is a Stateless or Stateful Application?**

RabbitMQ is a Stateful application.
The persistence of messages and queue definitions is essential for reliable messaging, making it a classic example of a Stateful Backing Service.
The provided algonquin-pet-store-all-in-one.yaml file defines the RabbitMQ component as a standard Kubernetes Deployment which means that it is storing its critical configuration files, queue definitions, and message data only on the Pod's local filesystem.
This makes it vulnerable to complete data loss under normal operational circumstances in a cloud-native environment.

**The implications of running RabbitMQ without persistent storage?**

The provided algonquin-pet-store-all-in-one.yaml file defines the RabbitMQ component as a standard Kubernetes Deployment.
This means RabbitMQ is storing its critical configuration files, queue definitions, and message data only on the Pod's local filesystem.
The primary implication is that the application is not durable. It is vulnerable to complete data loss under normal operational circumstances in a cloud-native environment.

**What Happens When the RabbitMQ Pod is Deleted or Restarted?**

When the RabbitMQ Pod is manually deleted or automatically failed/restarted:
1. Kubernetes terminates the current Pod instance.
2. The Pod's entire local filesystem, including all RabbitMQ data stored in the default location, is permanently destroyed.
3. The Deployment controller sees that a replica is missing and immediately provisions a brand-new Pod using the base rabbitmq management image.
4. This new Pod will start with an empty volume, resetting the broker to its default state. All previously created queues, messages, and any user/permission changes made via the Management Console are lost.
This behavior directly proves the misconfiguration and confirms the vulnerability identified in Lab 7.

**Potential Solutions to this Problem (Research-Based)?**

There are two main architectural solutions to handle the statefulness of RabbitMQ in a cloud environment:
1. Kubernetes-Native Solution: Use a StatefulSet
A StatefulSet is designed for stateful applications. It ensures that each Pod is assigned a stable identity and is coupled with a dedicated Persistent Volume Claim (PVC) which provisions external, durable cloud storage.
The storage persists independently of the Pod. If the Pod dies, the new Pod attaches to the existing volume, and the data is preserved.
2. Cloud-Native Best Practice: Use a Managed Backing Service
This is can be done by adopting a Managed Backing Service for messaging, eliminating the need to self-host and manage the persistence layer.
Migrate the messaging workload from RabbitMQ to a cloud provider's managed service, such as Azure Service Bus.
The application processes become completely stateless, relying entirely on the cloud vendor to handle persistence, scaling, high availability, and patching.

**Does using Azure Service Bus Solve the Issues Identified with RabbitMQ Configuration in this Lab?**

Yes, using Azure Service Bus absolutely solves the issues identified with the RabbitMQ configuration.
Azure Service Bus is a fully Managed Backing Service provided by Microsoft Azure.
By replacing the self-hosted RabbitMQ container with a Service Bus connection string, the messaging system is externalized from the Kubernetes cluster.
The microservices no longer manage the state (queues and messages); they simply consume the Service Bus API over the network.
Azure handles all data durability, replication, and persistence automatically, guaranteeing that messages and queue definitions are safe, regardless of what happens to the Pods in your AKS cluster.

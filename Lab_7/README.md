**The YouTube demo video link**


**Is RabbitMQ a Stateless or Stateful Application?**

RabbitMQ is a Stateful application.
The persistence of messages and queue definitions is essential for reliable messaging, making it a classic example of a Stateful Backing Service.
The provided algonquin-pet-store-all-in-one.yaml file defines the RabbitMQ component as a standard Kubernetes Deployment, which means it stores its critical configuration files, queue definitions, and message data only on the Pod's local filesystem.
This makes it vulnerable to complete data loss under normal operational circumstances in a cloud-native environment.

**What Are the Implications of Running RabbitMQ Without Persistent Storage?**

The provided algonquin-pet-store-all-in-one.yaml file defines the RabbitMQ component as a standard Kubernetes Deployment.
This means RabbitMQ stores its critical configuration files, queue definitions, and message data only on the Pod's local filesystem.
The primary implication is that the application is not durable. It is vulnerable to complete data loss under normal operational circumstances in a cloud-native environment.

**What Happens When the RabbitMQ Pod Is Deleted or Restarted?**

When the RabbitMQ Pod is manually deleted or automatically fails/restarts:
1. Kubernetes terminates the current Pod instance.
2. The Pod's entire local filesystem, including all RabbitMQ data stored in the default location, is permanently destroyed.
3. The Deployment controller observes that a replica is missing and immediately provisions a new Pod using the base RabbitMQ management image.
4. This new Pod will start with an empty volume, resetting the broker to its default state. All previously created queues, messages, and user/permission changes made via the Management Console are lost.
This behaviour directly highlights the misconfiguration and confirms the vulnerability identified in Lab 7.

**What Are Potential Solutions to This Problem (Research-Based)?**

There are two main architectural solutions to handle RabbitMQ's statefulness in a cloud environment:
1. Kubernetes-Native Solution: Use a StatefulSet
A StatefulSet is designed for stateful applications. It ensures that each Pod has a stable identity and is coupled with a dedicated Persistent Volume Claim (PVC), which provisions external, durable cloud storage.
The storage persists independently of the Pod. If the Pod dies, the new Pod attaches to the existing volume, and the data remains intact.
2. Cloud-Native Best Practice: Use a Managed Backing Service
This can be achieved by adopting a Managed Backing Service for messaging, removing the need to self-host and manage the persistence layer.
Migrate the messaging workload from RabbitMQ to a cloud provider's managed service, such as Azure Service Bus.
The application processes become entirely stateless, relying on the cloud vendor to handle persistence, scaling, high availability, and patching.

**Does Using Azure Service Bus Resolve the Issues Identified With RabbitMQ Configuration in This Lab?**

Yes, using Azure Service Bus definitely solves the issues identified with the RabbitMQ configuration.
Azure Service Bus is a fully Managed Backing Service provided by Microsoft Azure.
By replacing the self-hosted RabbitMQ container with a Service Bus connection string, the messaging system is externalized from the Kubernetes cluster.
The microservices no longer manage the state (queues and messages); they simply consume the Service Bus API over the network.
Azure handles all data durability, replication, and persistence automatically, ensuring that messages and queue definitions are safe, regardless of what happens to the Pods in your AKS cluster. The persistence of messages and queue definitions is essential for reliable messaging, making it a classic example of a Stateful Backing Service.
The provided algonquin-pet-store-all-in-one.yaml file defines the RabbitMQ component as a standard Kubernetes Deployment, which means that it is storing its critical configuration files, queue definitions, and message data only on the Pod's local filesystem.
This makes it vulnerable to complete data loss under normal operational circumstances in a cloud-native environment.

### Lab 6: Deploy Algonquin Pet Store to Azure Kubernetes Service (AKS)

1. #### Please find below the YouTube video link:

- https://www.youtube.com/watch?v=EspQ8gfEGhY

2. #### Added txt/md file in the repo showing the tests done for the kubectl commands in the provided Kubectl-Cheat-Sheet.md file.

3. The microservices application achieves single-IP access for all its backend components through path-based routing managed by NGINX.
- Single Entry Point: The K8S deployment exposes only the store-front application via a LoadBalancer service type. This is the only component in the cluster that receives a public, and external IP from Azure.
- Internal Services: All other services (product-service, order-service, and rabbitmq) are exposed using the ClusterIP service type, making them accessible only from inside the K8S cluster using their internal service names.
- Proxy Logic: The NGINX instance running inside the store-front container is configured to intercept all traffic coming to the external IP. It then inspects the URL path and uses the proxy to forward the request to the correct internal service. This makes NGINX the central traffic dispatcher for the entire microservices architecture.

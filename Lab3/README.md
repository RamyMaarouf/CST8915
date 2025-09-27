### Lab 3: Deploying the Algonquin Pet Store on Azure

1. #### Please find below the YouTube video link:

- https://www.youtube.com/watch?v=udXWYah61F8


2. #### Reflection Questions:

i. **What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?**
    I didn't face a challenge or maybe I didn't understand the question correctly, sorry.

ii. **How does deploying microservices on Azure Web App Service differ from running them locally?**
    Deploying on Azure Web App Service changes the operational hassle compared to running locally or even on VMs (as we did in Lab 2). We manually start the process locally and rely on local .env files. On a PaaS platform, it handles infrastructure management and process supervision automatically. Our responsibility shifts entirely to code deployment and configuration management via the Azure Portal settings, allowing the development teams to focus on business logic rather than server maintenance.

iii. **Why is it important to use environment variables for configurations in a cloud environment?**
    Because it adheres to the 12-Factor App, it separates configuration from code, allowing the system to isolate sensitive information from source control. This will ensure that the settings can be changed instantly via the Azure Portal without requiring the application code to be rebuilt. So, using environment variables enables runtime portability and enhanced security.

3. #### Links to the three service repositories:

- https://github.com/RamyMaarouf/order-service.git
- https://github.com/RamyMaarouf/product-service.py.git
- https://github.com/RamyMaarouf/store-front.git
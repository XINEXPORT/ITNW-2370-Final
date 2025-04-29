# Create a microservice, containerize it, and deploy it to Azure Cloud 

> **READ THIS ENTIRE DOCUMENT CAREFULLY BEFORE BEGINNING YOUR PROJECT**  
> Then use it along with the Microservice Tutorial Instructions.

---

## Part 1: Create and Run a Microservice

1. Navigate to the **Microservice Tutorial** to complete this project.
2. On the “Intro” page of **.NET Tutorial – Your First Microservice**, select **Linux**. Complete all steps for the Linux operating system.
3. On the **Install .NET SDK** page, use the following link instead of the one in the tutorial:  
[Install .NET on Ubuntu - .NET | Microsoft Learn](https://learn.microsoft.com/en-us/dotnet/core/install/linux-ubuntu)
4. Select the **20.04 distribution**, scroll down to **Add the Microsoft Package Repository**, and run the `wget` command for **.NET 8**.
5. Install the SDK.
6. Return to the tutorial and verify that everything installed correctly. *(You do not need to install the runtime.)*
7. Follow the directions in the tutorial to **Create your service**.
8. Then **Run your service**.
9. **Take a screenshot** of your browser results showing the weather forecast data of your application. Be sure to include the URL in your screenshot.  
   - Label this screenshot: **1-Running the Service**
10. Underneath the screenshot, **answer the following question**:  
    > **What port was your application listening on?**
11. Check your Docker version with:
    ```bash
    docker --version
    ```
    - If your version is **less than 23.0.0**, skip the "Download and install" section in the tutorial and instead run:
    ```bash
    curl -fsSL https://get.docker.com -o get-docker.sh
    sudo sh get-docker.sh
    ```
12. After updating Docker, verify the Docker version again (it should now be higher than 23.0.x).
13. Return to the tutorial and make sure the **Linux tab** is selected.
14. In the section **Add Docker Metadata**, follow the instructions.  
    - You may use `nano` instead of `touch` to create the Dockerfile:
    ```
    nano Dockerfile
    ```
    - Press `Ctrl + S`, then `Ctrl + X` to save and exit.
15. Complete the steps for **Optional: Add a .dockerignore file**.
16. Follow the tutorial instructions to **Create Docker image** and **Run Docker image**.
17. **Take a screenshot** of your application running in the container (include the URL).  
    - Label this screenshot: **2-Running the Docker image**

---

## Part 2: Deploy Your Microservice to Azure Cloud

> ⚠️ **You will need a Docker Hub account and an Azure subscription.**  
> Make sure you have set up your **Azure for Students** free account if you haven't already.

**Important:** Always ensure the **Linux tab** is selected when completing steps.

1. Follow the instructions to **Push to Docker Hub**.
2. In the section **Setup Azure Tools**, **skip** "Create an Azure Account". *(You should already have an Azure for Students account.)*
3. Click **Install the Azure CLI**.
   - In the article **"How to install the Azure CLI"**, select **Install on Ubuntu/Debian with apt**.
4. On the "Install the Azure CLI" page:
   - Scroll down and select **Option 1 - Install with one command**, then upgrade the CLI with:
   ```bash
   sudo apt-get update && sudo apt-get upgrade -y
   ```
5. Return to the tutorial and follow the instructions to **Sign in to Azure** using your personal email (the one linked to Azure).
6. Use the `sudo` command to install the AKS CLI.  
   - If you get an error `"MissingSubscriptionRegistration"`, run:
   ```bash
   az provider register --namespace Microsoft.ContainerService
   ```
7. Follow the instructions to **Create Azure Resources**.
8. In the **Deploy to Azure** section, use `nano` to create the `deploy.yaml` file.
9. Run the deployment and **Test your deployment service**.
10. **Take a screenshot** of your browser results showing the weather forecast data.  
    - Label this screenshot: **3 – Deployed Service**
11. **Scale your service**.
12. Display the pods with:
    ```bash
    kubectl get pods -o wide
    ```
    - **Take a screenshot** of the results.  
      Label it: **4 - Scaled Application**

---

### Optional: Five Extra Credit Points

13. In a browser window, navigate to [Azure Portal](http://portal.azure.com).
14. In the blue search box, type **Kubernetes Service**.
15. Click on **MyMicroServiceCluster**.
16. On the left menu under **Kubernetes Resources**, click **Workloads** and observe the results.
    - **Take a screenshot** of this page.  
      Label it: **5 – Kubernetes Resources in Azure**

---

## **FINALLY, Cleanup your resources.**

---

# 🎉 CONGRATULATIONS! 🎉
You have created a microservice, containerized it, and deployed it to the cloud!

# Kubernetes Deployment - jaagdesh Pod

## Project Overview
This project demonstrates how to deploy a simple Kubernetes **Pod** and **Deployment** with **2 replicas** using a **Deployment YAML** file. The pod runs the **nginx** web server.

### Key Features
- Kubernetes **Pod** and **Deployment** for **jaagdesh**.
- Runs **nginx** as the container image.
- Configured with **2 replicas** to ensure high availability.

## Requirements
- Kubernetes cluster set up and configured.
- `kubectl` command-line tool installed and configured.
- A GitHub account to host the project (optional).

## Steps to Deploy

1. **Create a new Kubernetes Deployment:**
    - Save the provided `jaagdesh-deployment.yaml` file in your local machine.

2. **Apply the YAML file using kubectl:**
    ```bash
    kubectl apply -f jaagdesh-deployment.yaml
    ```

3. **Verify the pods are running:**
    ```bash
    kubectl get pods
    ```

4. **Check Deployment status:**
    ```bash
    kubectl get deployment
    ```

5. **Accessing the Application (Optional):**
    If you want to access the nginx server externally, you can expose the deployment using a service. Create a service YAML file (e.g., `nginx-service.yaml`) and apply it:

    ```yaml
    apiVersion: v1
    kind: Service
    metadata:
      name: jaagdesh-service
    spec:
      selector:
        app: jaagdesh
      ports:
        - protocol: TCP
          port: 80
          targetPort: 80
      type: LoadBalancer
    ```

    Then apply it:

    ```bash
    kubectl apply -f nginx-service.yaml
    ```

6. **View logs (Optional):**
    To check logs for a particular pod:
    ```bash
    kubectl logs jaagdesh
    ```

## Additional Notes
- This project is a basic demonstration of Kubernetes Pods and Deployments.
- You can modify the YAML file to scale the replicas or change the container image.
- Kubernetes cluster must have enough resources (CPU, RAM) to run multiple replicas.

## Author
- **Busireddy Jagadeswar Reddy**

## License
MIT License


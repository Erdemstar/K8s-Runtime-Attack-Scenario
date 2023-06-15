# Scenario-2

Welcome to Scenario-2 :)

In this attack scenario, I will use the Docker image of the .NET Core API application that I have developed [VulnerableApp4Kubernetes](https://github.com/Erdemstar/VulnerableApp4Kubernetes) before and which has many web vulnerabilities. By using the 2 vulnerabilities on this application and connecting with container with kubectl exec command, we will read the sensitive files of the container.

## Goals

The goal here should be to generate an alarm and capture this situation when the sensitive files owned by the container are read by the attackers.

## Content of Environment file

 - **Namespace Object** : A Namespace object named "vulnerable" has been created. As the work will continue under this namespace, the other objects below are created under this namespace.
 - **Deployment Object** : A Deployment object named "vulnerable-deployment" with a single replicaSet using the "erdemstar/vulnerableapp4kubernetes:arm64" (If you are using an Intel or AMD based processor, I recommend you to change the image information to emrestar/vulnerableapp4kubernetes:amd64.) image was created under the "vulnerable" Namespace. 
 - **Service Object** : In order to access the Deployment object named "vulnerable-deployment" under the "vulnerable" Namespace from outside the Cluster, a nodePort type Service object named "vulnerable-service" has been created.

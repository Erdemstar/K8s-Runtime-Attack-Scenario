# Scenario-1

Welcome to Scenario-1 :)

In this attack scenario, I will use the Docker image of the .NET Core API application that I have developed [VulnerableApp4Kubernetes](https://github.com/Erdemstar/VulnerableApp4Kubernetes) before and which has many web vulnerabilities. Image uses only "dotnet VulnerableApp4Kubernetes.dll" command to work, other than that it doesn't use any other command. Here, the Remote Code Execution vulnerability will be exploited to run a different command on the relevant container.

## Goals

Related Container continues to run using the command "dotnet VulnerableApp4Kubernetes.dll". Here, using the relevant RCE vulnerability, it will be useful to run different commands other than "dotnet" and check whether an alarm is generated for these commands, to detect the RCE vulnerability.

## Content of Environment file

 - **Namespace Object** : A Namespace object named "vulnerable" has been created. As the work will continue under this namespace, the other objects below are created under this namespace.
 - **Deployment Object** : A Deployment object named "vulnerable-deployment" with a single replicaSet using the "erdemstar/vulnerableapp4kubernetes:arm64" (If you are using an Intel or AMD based processor, I recommend you to change the image information to emrestar/vulnerableapp4kubernetes:amd64.) image was created under the "vulnerable" Namespace. 
 - **Service Object** : In order to access the Deployment object named "vulnerable-deployment" under the "vulnerable" Namespace from outside the Cluster, a nodePort type Service object named "vulnerable-service" has been created.

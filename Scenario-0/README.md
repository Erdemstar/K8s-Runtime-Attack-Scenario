# Scenario-0

Welcome to Scenario-0 :)

This folder has been prepared for people who have completed the installation phase and was created to share a sample K8s manifest file with you before starting the work. The healthy operation of the shared manifest file in your environment will be important when creating the environment for the attack scenarios that I will describe in the future.

## Content of Environment file

 - **Namespace Object** : A Namespace object named "vulnerable" has been created. As the work will continue under this namespace, the other objects below are created under this namespace.
 - **Role Object** : Created a role object with any rights under the "vulnerable" Namespace
 - **Service Account Object** : A Service Account object named "attacker" has been created under the "vulnerable" Namespace.
 - **RoleBinding Object** : A RoleBinding object has been created to connect Role and Service Account under the "vulnerable" Namespace.
 - **Deployment Object** : A Deployment object named "nginx-deploy" with a single replicaSet using the Nginx image was created under the "vulnerable" Namespace.
 - **Service Object** : In order to access the Deployment object named "nginx-deploy" under the "vulnerable" Namespace from outside the Cluster, a nodePort type Service object named "nginx-deploy-service" has been created.
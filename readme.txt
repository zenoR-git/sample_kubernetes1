---------------------------------------------
dockerFiles folder contains dockerfile used to create ruby image

----------------------------------------------
Deployments folder contains ruby app Deployment manifest file and postgres statefulset manifest file.


-----------------------------------------------
services folder contains services required for pods to comminucate with each other

------------------------------------------------

Order of execution:
    1st ./deployments/database.yaml
    2nd   ./services/internal_network.yaml
    (the above two must be executed using "kubectl apply -f filename" command. 
    ruby-app pod creation will fail if not done.)
    3rd   ./deployments/rubyApp.yaml
    4th   ./services/ext_access.yaml

---------------------------------------------------
access app at: http://(minikube ip):31317

---------------------------------------------------
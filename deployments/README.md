### Deploying the famous mongo-db and mongo-express with Kubernetes
-------------------------------------------
* Note: Is not a good practice to deploy environment variables like username and passwords into the deployment file
* so we need to use secret.yaml file to keep our passwords safe.
* I also use a config file to setup the database_url 

* Requirements *
-----------------------------
- a running kubernetes cluster either on local system or cloud based
- make sure you're in the deployment folder

1. Run the following in order:
- kubectl apply -f *.yaml files
-                  mongo-secret.yaml
-                  demo-service.yaml
-                  express-svc.yaml
-                  express-config.yaml
-                  mongo-depl.yaml
-                  mongo-express.yaml

##### OR
- run `kubectl apply -k kustomization.yaml` this contain all the files and will deploy them in a go 
- When you run this, you will see deployment created for all the components

2. run `kubectl get pods -A` to get all the pods

3. To get the endpoint of the application, run `kubectl get svc` 
    - You will get something in the form of this 
      "a999b47ed277c46dea60ce7196def2b4-376647347.us-east-1.elb.amazonaws.com/"
    - Copy it and attach the port number to it "a999b47ed277c46dea60ce7196def2b4-376647347.us-east-1.elb.amazonaws.com/:port_number" and access it in your browser

-------------------|-------------|-------------------
-------------------|-------------|-------------------
-------------------|-------------|-------------------
-------------------|Just an ambition|-------------------
-------------------|-------------|-------------------
-------------------|-------------|-------------------
-------------------|-------------|-------------------
-------------------|-------------|-------------------
-------------------|-------------|-------------------

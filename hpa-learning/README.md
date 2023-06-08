## Horizontal Pod Autoscaling
- This method of kubernnetes deployment requires automatically increasing the number of application pods in use when their is a surge in workload and vice versa

*** This is a test deployment ***
    - *With this, I'm going to rely on a python script to generate an iteration on an absurd number to increase the workload on the application*
    - *This is why I'm deploying a ConfigMap to accommodate that script*
    - *The ConfigMap is referenced in the volumes of the application pod (.spec.template.spec.volumes)*
    - *Then I'll deploy the ConfigMap first followed by the application.*
    - *For now, you won't see much. It's just the running pod*
    - *The finally, I'll deploy the HorizontalPodAutoscaler*
    - *This will not start collecting the cpu metrics immediately. It gathers metrics every 15s*
    - *After the first 15s, if you run /*kubectl get hpa */ you should see something like 210%/50% and the number of replicas will change from 1 to 3*


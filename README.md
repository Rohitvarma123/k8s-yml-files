# 1. Get nodes
kubectl get nodes

# 2. Get nodes with detailed information
kubectl get nodes -o wide

# 3. Get all pods with detailed information
kubectl get pods -o wide

# 4. Get a specific service
kubectl get svc nginx-service

# 5. Get service endpoints
kubectl get endpoints nginx-service

# 6. View Pod YAML file
cat nginx-pod.yaml

# 7. View Service YAML file
cat nginx-service.yaml

# 8. Get all pods
kubectl get pods

# 9. Describe a Pod
kubectl describe pod nginx-pod

# 10. Enter inside the Pod
kubectl exec -it nginx-pod -- /bin/bash

# 11. Enter a specific container
kubectl exec -it nginx-pod -c nginx -- /bin/bash

# 12. View Pod logs
kubectl logs nginx-pod

# 13. View logs with timestamps
kubectl logs nginx-pod --timestamps=true

# 14. Follow live logs
kubectl logs -f nginx-pod

# 15. Follow live logs with timestamps
kubectl logs -f nginx-pod --timestamps=true

# 16. Display first 10 log lines
kubectl logs nginx-pod | head -10

# 17. Display last 10 log lines
kubectl logs nginx-pod | tail -10

# 18. Display first 10 log lines with timestamps
kubectl logs nginx-pod --timestamps=true | head -10

# 19. Display last 10 log lines with timestamps
kubectl logs nginx-pod --timestamps=true | tail -10

-----------------------------------------------------------------------------
-------Replica set----------
# Check ReplicaSet
kubectl get rs

# Check Pods
kubectl get pods -o wide

# Scale from 5 to 3
kubectl scale rs nginx-replicaset --replicas=3

# Scale from 3 to 10
kubectl scale rs nginx-replicaset --replicas=10

# Describe ReplicaSet
kubectl describe rs nginx-replicaset

# Delete ReplicaSet
kubectl delete rs nginx-replicaset

------------------------------------------------------------------------
---------DEPLOYMENT COMMANDS---------
KUBERNETES DEPLOYMENT – COMMANDS WITH MEANING

1. Describe Deployment

Command:
kubectl describe deploy nginx-deployment

Meaning:
To see complete information about the Deployment, such as Pods, replicas, image and events.

2. Scale Deployment

Command:
kubectl scale deploy nginx-deployment --replicas=5

Meaning:
To increase or decrease the number of Pods.
Example: If you have 3 Pods, this command increases them to 5.

3. Update Nginx Image

Command:
kubectl set image deployment/nginx-deployment nginx=nginx:1.27

Meaning:
To update the existing Nginx container image to a new version.
Kubernetes performs a rolling update.

4. Check Rollout Status

Command:
kubectl rollout status deployment/nginx-deployment

Meaning:
To check whether the Deployment update is completed successfully.

5. Check Rollout History

Command:
kubectl rollout history deployment/nginx-deployment

Meaning:
To see the previous versions or revisions of the Deployment.

6. Rollback Deployment

Command:
kubectl rollout undo deployment/nginx-deployment

Meaning:
To return the Deployment to its previous version if the new update has a problem.

7. Restart Deployment

Command:
kubectl rollout restart deployment/nginx-deployment

Meaning:
To restart all Pods managed by the Deployment without changing the container image.

8. Delete Deployment

Command:
kubectl delete -f nginx-deployment.yaml

Meaning:
To delete the Deployment created using the YAML file. Its managed ReplicaSet and Pods are also deleted.

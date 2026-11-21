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

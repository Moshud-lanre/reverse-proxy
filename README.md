# reverse-proxy
kubectl apply -f reverse_deployment.yml 
kubectl apply -f reverse_service.

#Reverse-proxy test
kubectl exec -it <pod_name> bash
curl http:reverseproxy-svc:8080/api/health

#Cleanup
kubectl delete service my-app-2-svc
kubectl delete service reverseproxy-svc
kubectl delete deployment my-app-2
kubectl delete deployment reverseproxy
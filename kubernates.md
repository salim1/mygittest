```sh
minikube start
```

```sh
kubectl get nodes
```

```sh
kubectl describe node

```

```sh
kubectl describe node [node name]
```


Each pod is like a separate logical machine with its own IP, hostname, processes, and so on, running a single application.

```sh
kubectl run kubia --image=luksa/kubia --port=8080
```
To make the pod accessible from the outside, you’ll expose it through a Service object.
#in this book, used command is kubectl run kubia --image=luksa/kubia --port=8080 --generator=run/v1 which used to create ReplicationController back in the days when book was written however this object #is currently depracated.
#Minikube doesn’t support LoadBalancer services, so the service will never get an external IP.
```sh
kubectl expose pod kubia --type=LoadBalancer --name kubia-http
```

```sh
kubectl get services
```

```sh
kubectl get svc
```

#When a service is created, it gets a static IP, which never changes during the lifetime of
#the service. Instead of connecting to pods directly, clients should connect to the service
#through its constant IP address. The service makes sure one of the pods receives the con-
#nection, regardless of where the pod is currently running (and what its IP address is).

```sh
kubectl api-resources
```

```sh
kubectl scale --replicas=3 pod/kubia-http
```
```sh
kubectl get pods -o wide
```
```sh
kubectl logs kubia-manual
```
#Container logs are automatically rotated daily and every time the log file reaches 10MB in size. The kubectl logs command only shows the log entries from the last rotation.



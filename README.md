# k8s-redis
Kubernets dployment for standalone Redis, which enables Redis authentication and uses a custom redis.conf file for configuration

### prerequisites
- Docker
- Minikube
- Kubectl

### Setup
```
1. Launch Minikube
2. Apply configMap & secret files
3. Deploy redis-deployment.yml
```

### Validation
```
1. kubectl exec --stdin --tty $(pod) -- /bin/bash
2. redis-cli
3. Try to implemet any db interaction (such as 'set foo 100') - you should get error message: 
```
![alt text](https://github.com/shahar5/k8s-redis/blob/main/Pics_for_README.md/auth_err.PNG)
```
4. Authenticate with - auth <your_password>
```
![alt text](https://github.com/shahar5/k8s-redis/blob/main/Pics_for_README.md/auth_ok.PNG)
```
5. Validate Log-Level set to Debug mode - config get loglevel
```
![alt text](https://github.com/shahar5/k8s-redis/blob/main/Pics_for_README.md/log_level.PNG)

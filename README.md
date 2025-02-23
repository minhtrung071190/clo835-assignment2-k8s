# Create secret to authenticate ECR

```
kubectl create secret docker-registry ecr-secret \
  --docker-server=063388721629.dkr.ecr.us-east-1.amazonaws.com \
  --docker-username=AWS \
  --docker-password=$(aws ecr get-login-password --region us-east-1) \
  --namespace default
```

# Create secret to store db password

```
kubectl create secret generic db-password --from-literal=MYSQL_ROOT_PASSWORD=pw
```
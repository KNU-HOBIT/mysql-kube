# mysql-kube
Kubernetes configuration files for deploying MySQL

## Directory tree
```
mysql-kube/
├── deployment.yaml
├── nodeport-svc.yaml
├── pvc.yaml
├── README.md
└── secrets.yaml
```
```
git clone https://github.com/KNU-HOBIT/mysql-kube.git

cd mysql-kube
```
```
kubectl create ns mysql

kubectl create -f deployment.yaml nodeport-svc.yaml pvc.yaml secrets.yaml

kubectl get all -n mysql
```
```
NAME                         READY   STATUS    RESTARTS   AGE
pod/mysql-6687bbbdd9-hbc77   1/1     Running   0          12d

NAME                    TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
service/mysql-service   NodePort   10.43.255.84   <none>        3306:30036/TCP   12d

NAME                    READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/mysql   1/1     1            1           12d

NAME                               DESIRED   CURRENT   READY   AGE
replicaset.apps/mysql-6687bbbdd9   1         1         1       12d

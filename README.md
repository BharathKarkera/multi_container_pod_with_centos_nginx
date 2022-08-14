# multi_container_pod_with_centos_nginx


12:53PM @Bharath ~ kubectl apply -f deployment.yml                  
deployment.apps/centos-nginx-deployment created
12:53PM @Bharath ~ 




12:53PM @Bharath ~ kubectl get deployments        
NAME                      READY   UP-TO-DATE   AVAILABLE   AGE
centos-nginx-deployment   2/2     2            2           5s
12:53PM @Bharath ~ 




12:53PM @Bharath ~ kubectl get pods --show-labels
NAME                                       READY   STATUS    RESTARTS   AGE   LABELS
centos-nginx-deployment-6c9595df66-bcq2b   2/2     Running   0          11s   app=centos-nginx,pod-template-hash=6c9595df66
centos-nginx-deployment-6c9595df66-zf2j5   2/2     Running   0          11s   app=centos-nginx,pod-template-hash=6c9595df66
12:53PM @Bharath ~ 
12:53PM @Bharath ~ 



12:53PM @Bharath ~ kubectl exec -i -t centos-nginx-deployment-6c9595df66-bcq2b bash


kubectl exec [POD] [COMMAND] is DEPRECATED and will be removed in a future version. Use kubectl exec [POD] -- [COMMAND] instead.
Defaulted container "centos-producer" out of: centos-producer, nginx-consumer
[root@centos-nginx-deployment-6c9595df66-bcq2b /]# 







[root@centos-nginx-deployment-6c9595df66-bcq2b /]# curl -i http://localhost:80
HTTP/1.1 200 OK
Server: nginx/1.23.1
Date: Sun, 14 Aug 2022 19:54:32 GMT
Content-Type: text/html
Content-Length: 13
Last-Modified: Sun, 14 Aug 2022 19:54:24 GMT
Connection: keep-alive
ETag: "62f952f0-d"
Accept-Ranges: bytes

test website
[root@centos-nginx-deployment-6c9595df66-bcq2b /]# 

# Kuberbetes example chat api

![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75446114-d6538700-5977-11ea-9069-b47b60ad257c.png)

Integration of the chat application prepared with asp .net core on Kubernet with all open source products is provided.

Code repo for image [github\chat_api_example](https://github.com/OktaySavdi/chat_api_example)

## [](https://github.com/OktaySavdi/kubernetes_chat_api_example)Tools & technologies used

1.  Asp .Net Core
2.  Elasticsearch
3.  Fluentd
4.  Redis
5.  RabbitMQ
6.  Docker
7. Kubernetes
8. Swagger (OpenApi 3.0)

## [](https://github.com/OktaySavdi/kubernetes_chat_api_example) Required

-   Docker
-   Kubernetes
-   Ingress Controller

## [](https://github.com/OktaySavdi/kubernetes_chat_api_example) We used on Kubernetes

 1. Probe (liveness,readness)
 2. Config (servername,port)
 3. Secret (user_name,password)
 4. Environment
 5. Fluentd sidecar injection on pods
 6. Resource
 7. Strategy

## [](https://github.com/OktaySavdi/kubernetes_chat_api_example) Install

Give execute permission for install.sh

    chmod +x install.sh

Install example

    ./install.sh

Call URL
**Chat**
```json
http://[NodeIP]/chat
http://chat.10.10.10.10.nip.io/chat
```
**Api**
```json
http://[NodeIP]/api/swagger
http://api.10.10.10.10.nip.io/api/swagger
```
## [](https://github.com/OktaySavdi/kubernetes_chat_api_example) Control
**Elasticsearch**
```json
KibanaPASSWORD=$(kubectl get secret elasticsearch-es-elastic-user -o=jsonpath='{.data.elastic}' | base64 --decode)

curl -u "elastic:$KibanaPASSWORD" -k "https://10.96.175.207:9200"
  ``` 
**Redis**
```json
kubectl exec -it $(kubectl get po -l run=redis -o jsonpath='{.items[*].metadata.name}') -- redis-cli client list
  ```
**RabbitMQ**
```json
http://[NodeIP]
http://rabbit.10.10.10.10.nip.io
  ```
  
**Kibana**
```json
http://[NodeIP]
http://kibana.10.10.10.10.nip.io
  ```

## [](https://github.com/OktaySavdi/kubernetes_chat_api_example) Screen
**Chat** 

![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75439673-4c9dbc80-596b-11ea-8ae6-069801dddb1e.png)

**Message**
![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75439713-5e7f5f80-596b-11ea-98c5-5b3179921afb.png)

**Elastic Log**
![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75439741-6b9c4e80-596b-11ea-9f77-cc0726936f52.png)

**Health**
![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75439765-7b1b9780-596b-11ea-8cfe-a0ef39c14cfc.png)

**Swagger**

![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75446728-00597900-5979-11ea-998e-07513d6490a4.png)

**Chatters**
![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75446814-30a11780-5979-11ea-8211-5ba0a5b3dc65.png)

**Send Message**

![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75446919-66de9700-5979-11ea-99c6-cb5298596e6b.png)

![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75446993-81b10b80-5979-11ea-9dfb-f279ede812ec.png)

**Receive Message**

![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75447063-a73e1500-5979-11ea-8a54-649ba36545e3.png)

**HealthCheck**

![https://github.com/OktaySavdi/kubernetes_chat_api_example](https://user-images.githubusercontent.com/3519706/75447140-d2286900-5979-11ea-8246-f427b570e4ce.png)

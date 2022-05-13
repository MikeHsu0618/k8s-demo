#  Blue Whale and Purple Whale Demo

## Using Kinds

- deployment
- service
- ingress

## Description

在本地的 `minikube` 使用 ingress 實現出 proxy, load balance 功能

運行成功即可以在本地 `purple.demo.com/` `blue.demo.com/` 成功分流看到兩種不同顏色的小鯨魚

## Steps

1. 開啟 minikube

```
minikube start
```

2. 預先開啟 ingress 設定， 以及打開 ingress 對本地的 tunnel

```
minikube addons enable ingress

minikube tunnel
```

3. 移動到設定檔目錄，並且執行 k8s 設定檔

```
cd ./whale

# kubectl create -f ./
kubectl apply -f ./
```

4. 分別拜訪路徑

```
curl purple.demo.com

curl blue.demo.com
```
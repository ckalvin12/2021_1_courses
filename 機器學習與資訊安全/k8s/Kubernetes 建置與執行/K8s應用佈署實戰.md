# K8s應用佈署實戰
```
Jupyter :一個開源的科學計算工具
Parse :設計給行動裝置APP 使用的開源API 伺服器
Ghost :部落格和內容管理平台
Redis :輕量、高性能的主鍵／值資料庫
```
```
Kubernetes 建置與執行 : 邁向基礎設施的未來, 2/e 
Kubernetes: Up and Running: Dive into the Future of Infrastructure, 2/e)
Brendan Burns,Kelsey Hightower,Joe Beda 林毅民（Sammy Lin）、謝智浩（Scott） 譯

歐萊禮 2019/2020
```
# Jupyter
```
Step 1: kubectl create namespace jupyter

Step 2:建立一個單一的Deployment 來執行Jupyter 應用程式==>jupyter.yaml

Step 3:佈署 ==> kubectl create -f jupyter.yaml
     
使用watch 這個指令來觀察容器建立的狀態
watch kubectl get pods --namespace jupyter

觀看容器的Log 檔案並取得首次登入所需的密鑰
pod_name=$(kubectl get pods --namespace jupyter --no-headers | awk'{pri.nt $1}') \
kubectl logs --namespace jupyter ${pod_name}
==> 複製登入密鑰

設定Jupyter 容器的連接埠轉發
kubectl port-forward ${pod_name} 8888:8888

開啟你的瀏覽器並輸入
http:l/localhost:8888/?token=<toke登入密鑰>
```
## jupyter.yaml
```

```

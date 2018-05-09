# **__安裝伺服器系統__**
## 安裝elasticsearch [ZIP]
### 下載[elasticsearch](https://www.elastic.co/downloads/elasticsearch) 
### 進行解壓縮後將資料夾名稱改為 `elasticsearch` 並放置在C:\Program Files內
### 修改C:\Program Files\elasticsearch\config\ `elasticsearch.yml` 檔

    network.host: 0.0.0.0
    
![elasticsearchsetyml](image/elasticsearchsetyml.png)
### 執行C:\Program Files\elasticsearch\bin\ `elasticsearch.bat` 檔    
![batfile](image/elasticsearchbatfile.png)
### 開啟網頁，在網頁輸入以下網址

    http://localhost:9200/

![localhost9200](image/localhost9200.png)

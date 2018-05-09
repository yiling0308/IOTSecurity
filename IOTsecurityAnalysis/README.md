# **__安裝伺服器系統__**
> ## 安裝[JAVA8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) (Windows x64)
### 安裝好以後記得設定環境變數
`檔案總管 > 本機(右鍵) > 內容 > 進階系統設定 > 環境變數(N)... > 找到系統變數(Path) > 編輯(I)... > 新增Java路徑`
![computer content](image/computer.png)
![JAVA setting](image/javasetting.png)
> ## 安裝[elasticsearch](https://www.elastic.co/downloads/elasticsearch) [ZIP]
### 進行解壓縮後將資料夾名稱改為 `elasticsearch` 並放置在C:\Program Files內
### 修改C:\Program Files\elasticsearch\config\ `elasticsearch.yml` 檔
    network.host: 0.0.0.0
![elasticsearchsetyml](image/elasticsearchsetyml.png)
### 執行C:\Program Files\elasticsearch\bin\ `elasticsearch.bat` 檔
![batfile](image/elasticsearchbatfile.png)
### 開啟網頁，在網頁輸入網址 `http://localhost:9200/`
![localhost9200](image/localhost9200.png)
> ⚠若elasticsearch無法正確執行，請使用[msi安裝方法](https://www.elastic.co/downloads/elasticsearch) [MSI (BETA)]
![elasticsearchmsi](image/elasticsearchmsi1.png)
![elasticsearchmsi](image/elasticsearchmsi2.png)
![elasticsearchmsi](image/elasticsearchmsi3.png)
![elasticsearchmsi](image/elasticsearchmsi4.png)
![elasticsearchmsi](image/elasticsearchmsi5.png)                                 
### 執行C:\Program Files\Elastic\Elasticsearch\6.2.4\bin `elasticsearch.exe` 檔
### 開啟網頁，在網頁輸入網址 `http://localhost:9200/`
> ## 安裝[Kibana](https://www.elastic.co/downloads/kibana) (WINDOWS)
### 進行解壓縮後將資料夾名稱改為 `Kibana` 並放置在C:\Program Files內
### 修改C:\Program Files\kibana\config `kibana.yml` 檔
    server.host: "0.0.0.0"
![kibanayml](image/kibanayml.png)
### 執行C:\Program Files\kibana\bin `kibana.bat` 檔
![kibanabat](image/kibanabat.png)
### 開啟網頁，在網頁輸入網址 `http://localhost:5601/`
![kibana5601](image/kibana5601.png)
> ## 安裝[Winlogbeat](https://www.elastic.co/downloads/beats/winlogbeat) (WINDOWS 64-BIT)
### 進行解壓縮後將資料夾名稱改為 `winlogbeat` 並放置在C:\Program Files內
>> ## 使用powershell`(以系統管理員身分執行)`安裝    
![powershell](image/powershell1.png)

    Set-ExecutionPolicy RemoteSigned (y)
    cd 'C:\Program Files\Winlogbeat'
    .\install-service-winlogbeat.ps1

![powershell](image/powershell2.png)
### 修改C:\Program Files\winlogbeat `winlogbeat.yml` 檔
![winlogbeat](image/winlogbeatyml.png)

    .\winlogbeat.exe test config -c .\winlogbeat.yml -e
    .\winlogbeat setup --template -E output.logstash.enabled=false -E 'output.elasticsearch.hosts=["localhost:9200"]'

![winlogbeat](image/winlogbeat9200.png)
### 開啟網頁，在網頁輸入網址 `http://localhost:9200/winlogbeat-*`     
![winlogbeat](image/winlogbea9200web.png)

    .\winlogbeat setup --dashboards
    Start-Service winlogbeat
    
![winlogbeat](image/winlogbeatstart.png)
### 在網頁輸入網址 `http://localhost:5601/app/kibana#/discover?_g=()` 可看到資料傳輸成功
![winlogbeat](image/kibana5601after.png)
> ## 安裝 logstash@Ubuntu MATE (64-bit)

    sudo apt-get install openjdk-8-jre
    sudo apt-get install grok
    curl -L -O https://artifacts.elastic.co/downloads/logstash/logstash-5.2.0.zip
    unzip logstash-5.2.0.zip
    sudo mv logstash-5.2.0/ /opt
    cd /opt 
    sudo mv logstash-5.2.0/ logstash 

    sudo apt-get install ant texinfo openjdk-8-jdk build-essential
    git clone https://github.com/jnr/jffi.git
    cd jffi
    ant jar
    sudo cp build/jni/libjffi-1.2.so /opt/logstash/vendor/jruby/lib/jni/arm-Linux

    cd /opt/logstash
    sudo vim config/jvm.options
    
### jvm.options設定黨內容
    
    -Xms512m
    -Xmx512m
    
![logstash](image/jvmoptions.png)

    cd /opt/logstash
    sudo vim apache-filter.conf 
    
### apache-filter.conf設定黨內容
    
    input {
      file {
        path => "/var/log/apache2/access.log"
        start_position => "beginning"
      }
    }
    filter {
      if [path] =~ "access" {
        mutate { replace => { "type" => "apache_access" } }
        grok {
          match => { "message" => "%{COMBINEDAPACHELOG}" }
        }
      }
      date {
        match => [ "timestamp" , "dd/MMM/yyyy:HH:mm:ss Z" ]
      }
    }
    output {
      elasticsearch {
        hosts => ["120.114.135.24:9200"]
      }
      stdout { codec => rubydebug }
    }    

![logstash](image/apache-filterconf.png)

    sudo bin/logstash -f apache-filter.conf
    
![logstash](image/-fapache-filter.png) 
### 在網頁輸入網址 `http://120.114.135.24:9200/_search?q=DVWA` 
![logstash](image/searchDVWA9200.png) 
### 在網頁輸入網址 `http://localhost:5601/app/kibana#/discover?_g=()` 
![logstash](image/5601finish.png) 

# docker_lamp_laravel

■ 動作確認方法
1. ssl用の鍵を作る  
参考) https://qiita.com/ukei2021/items/9fd5a46253f0a43f7ddb
```
cd docker/PhpApache/config/key

openssl genrsa -out ssl.key 2048

openssl req -new -sha256 -key ssl.key -out ssl.csr
# Common Nameだけ「localhost」と入力して、後全部Enter

openssl x509 -req -sha256 -days 365 -signkey ssl.key -in ssl.csr -out ssl.crt -extfile
```

2. 下記ファイルを設置 
* srcディレクトリに案件毎のgitリポジトリを置く想定  
src/html/index.php
```
<?php phpinfo();
```

3. Dockerイメージ作成
```
docker-compose build
```

4. Dockerコンテナを立ち上げ
```
docker-compose up -d
```

5. ブラウザで確認  
http://localhost:8080

![image](https://user-images.githubusercontent.com/2200168/139356271-3aefeaaf-02d1-4c10-b87f-b1c5fbd75e05.png)

https://localhost:8443

![image](https://user-images.githubusercontent.com/2200168/139355922-37cfdbfa-1cd0-46ea-be47-df2e28a260dd.png)



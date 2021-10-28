# docker_lamp_laravel

■ 動作確認方法
1. 下記ファイルを設置 
* srcディレクトリに案件毎のgitリポジトリを置く想定  
src/html/index.php
```
<?php phpinfo();
```

2. Dockerイメージ作成
```
docker-compose build
```

3. Dockerコンテナを立ち上げ
```
docker-compose up -d
```

4. ブラウザで確認  
http://localhost:8080

![image](https://user-images.githubusercontent.com/2200168/139213663-d0b20a8d-2c57-4bc7-9a61-6d21d9ccc586.png)


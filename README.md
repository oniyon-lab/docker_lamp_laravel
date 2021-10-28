# docker_lamp_laravel

■ 動作確認方法
1. 下記ファイルを設置
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

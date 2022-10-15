# terraria_multi
自宅の Mac Mini(Intel CPU) に terraria サーバーを建て、管理しています。

# 準備
1. Mac Mini に Docker for Mac をインストール
1. Terminalを起動
1. 初回起動  
  `$ git clone https://github.com/mabubu0203/terraria_multi.git`   
  `$ docker-compose -f ./docker/docker-compose.yml up --build --remove-orphans`  
  docker-composeのログより起動を確認  
  `$ docker-compose -f ./docker/docker-compose.yml stop`
1. world作成    
  `$ cd docker`  
  `$ docker-compose ps`  
  `$ docker-compose exec terraria bash`
  `$ sh ./bootstrap.sh` 
  world生成後、設定修正
  `$ cp ./docker/.env.sample ./docker/.env`  
  `$ vi ./docker/.env`  
     

# 起動と停止
start -> `$ docker-compose -f ./docker/docker-compose.yml start`  
stop -> `$ docker-compose -f ./docker/docker-compose.yml stop`  

# ディレクトリ構成

```bash
root
- docker
  - data
    - logs
    - plugins
    - worlds
    - config.json
- README.md
```
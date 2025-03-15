# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

---
# Memo
- Rails入門1-1:3分で掲示板を作ってみよう | プログラミング学習サイト【paizaラーニング】での環境に合わせる
## セットアップ
```bash
sudo rm -r {app,bin,config,db,lib,log,public,test,tmp,vendor}
sudo rm .gitignore config.ru Rakefile README.md 
rm -f Gemfile.lock
touch Gemfile.lock
docker-compose down
docker-compose down -v
docker-compose build --no-cache
docker-compose up -d

docker-compose run web rails new . --force --database=mysql --skip-bundle --skip-gemfile
```

[config/database.yml](config/database.yml)  を以下のように修正
```yml
default: &default
  adapter: mysql2
  encoding: utf8
  pool: 5
  username: root
  password:
  host: localhost ⇒ db
```

引き続き以下を実行
```Dockerfile
docker-compose down
docker-compose down -v
docker-compose build --no-cache
docker-compose up -d
docker-compose run web rails db:create
```

## 結果
[http://localhost:3000/](http://localhost:3000/)で確認

![image](https://github.com/user-attachments/assets/73499c95-eddb-4150-b082-e6ed8dfb9d54)

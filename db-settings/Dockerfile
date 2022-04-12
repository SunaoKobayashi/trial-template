# MongoDB の Docker化：MongoDB イメージを構築する Dockerfile
# 本操作は下記サイトを参考に実施
# ubuntu:latest をベースとし、MongoDB は以下の手順でインストール：
# http://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/

# 書式：FROM    リポジトリ[:バージョン]
FROM ubuntu:latest
# apt-get ソースを更新し、gnupg2 をインストール
RUN apt-get update && apt-get install -y gnupg2
# インストール：
# MongoDB 公開 GPG 鍵を取り込み、MongoDB リストファイルを作成
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
RUN echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-3.0.list
# MongoDB をインストール
RUN apt-get install -y mongodb-org
# MongoDB データ・ディレクトリの作成
RUN mkdir -p /data/db
# コンテナのポート 27017 をホスト側に露出（EXPOSE)
EXPOSE 27017
# usr/bin/mongod を Docker 化アプリケーションのエントリ・ポイントに設定
ENTRYPOINT ["/usr/bin/mongod"]
FROM node:12
# アプリケーションディレクトリを作成する
WORKDIR /usr/src/app
# アプリケーションの依存関係をインストールする
# ワイルドカードを利用して、package.json と package-lock.json の両方が各汁にコピーされるようする。
COPY package*.json ./

RUN npm install
# 本番用にコードを作成している場合
# RUN npm ci --only=production

# アプリケーションのソースをバンドルする
COPY . .

EXPOSE 8080

CMD ["node", "server.js"]

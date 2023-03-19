##　 Docker にて Rails7 環境構築テスト

- DB は postgresql
- docker-compose build
- docker-compose run web rails new . --force --no-deps --database=postgresql
- docker-compose up -d
- docker-compose run web bundle exec rails db:create

### Gem を追加する方法

- プロジェクトの Gemfile に追加したい gem を追記
- bundle install
- その後、Docker コンテナ内で新しい gem をインストール docker-compose run web bundle install
- 再ビルド docker-compose build
- イメージが再ビルドされたら、コンテナを再起動して変更を反映 docker-compose up -d
- 再度接続するのに多少時間かかるから焦らないで大丈夫！

### イメージ変わってもいいならそのままぶち込んでもいい気がする。

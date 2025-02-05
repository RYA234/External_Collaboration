# 開発

名称|バージョン|説明
---|----|------
Windows|10|
Docker|--|コンテナ型仮想環境
Oracle||データベース
sqlplus||OracleのCLI



# コンテナ起動方法
```bash 
# ビルド
docker-compose build

# 起動
docker-compose up -d

# コンテナに入る
docker-compose exec -it  oracle_db bash




# sqlplusを実行できることを確認　
docker-compose exec -it  oracle_db bash -c "sqlplus -v"

# 結果
SQL*Plus: Release 23.0.0.0.0 - for Oracle Cloud and Engineered Systems on 水 2月 5 06:32:12 2025
Version 23.5.0.24.07


# select文を打てるか確認
docker-compose exec -it  oracle_db bash -c "sqlplus system/pass"

# ユーザー「system」 パスワード「pass」を入力する。
SQL> SELECT * FROM v$version;

# 結果
Oracle Database 23ai Free Release 23.0.0.0.0 - Develop, Learn, and Run for Free


docker-compose exec -it  oracle_db bash;
sqlplus system/pass  show parameter service;

echo "show parameter service;" | sqlplus system/pass
```
# 一言


# 参考資料

以下の記事を参考

イメージの準備とかを参考
https://qiita.com/h-i-ist/items/a67acbce0e7c6bdebd69

docker-compose　A5SQLの設定など　書き方を参考
https://qiita.com/hrk_okd/items/f098ee234b702975c4fd

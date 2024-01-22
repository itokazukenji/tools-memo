```
# squidインストール
$ sudo yum -y install squid

# squidスタート
$ sudo systemctl start squid

# squid自動起動
$ sudo systemctl enable squid

# squid起動確認
$ sudo systemctl status squid

# ファイル修正
$ sudo vi /etc/squid/squid.conf

### 48行目辺りに下記行追加(正確には「http_access deny all」より前のセクションに記載します)
## IP許可設定
# Squidを使用する自宅PCのIPアドレス
acl myip src xx.xx.xx.xx/32
# 接続元PCのアクセス許可
http_access allow myip
## セキュリティ設定(必須では無いが推奨)
# Proxyサーバのホスト名を擬態
visible_hostname unknown
# アクセス先に自宅PCのIPアドレスを知られないようにする
forwarded_for off
# ヘッダ情報出力抑制
request_header_access X-Forwarded-For deny all
request_header_access Via deny all
request_header_access Cache-Control deny all
```

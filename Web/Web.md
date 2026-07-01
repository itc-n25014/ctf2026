# Webサーバインストールマニュアル

## １．パッケージをインストールする

```bash
sudo apt update
sudo apt install apache2 apache2-utils -y
```

## ２．Apacheの状態を確認する

```bash
sudo systemctl status apache2 
```
active (running) が表示されていることを確認

## ３．ベーシック認証用のパスワードファイルを作成する

```bash
sudo htpasswd -c /etc/apache2/.htpasswd vagrant
```
ユーザー名をvagrantとして、パスワードを設定

## ４．Apacheの設定ファイルを編集する

```bash
sudo nano /etc/apache2/sites-available/000-default.conf
```
追記する内容

```bash
<Directory "/var/www/html">
    AuthType Basic
    AuthName "Restricted Area"
    AuthUserFile /etc/apache2/.htpasswd
    Require valid-user
</Directory>
```

## ６．設定を反映させる

```bash
sudo apache2ctl configtest
sudo systemctl restart apache2
```

## ７．動作確認

```bash
ip a
```

ブラウザで http://<IPアドレス> にアクセス





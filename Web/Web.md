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




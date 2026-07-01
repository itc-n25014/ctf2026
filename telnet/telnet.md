## telnetサーバインストールマニュアル

# ２．xinetdとtelnetdをインストールする

```bash
sudo apt update
sudo apt install xinetd telnetd -y
```

# ３．xinetd用の設定ファイルを作成する

```bash
sudo nano /etc/xinetd.d/telnet
```
記述する内容
```bash
service telnet
{
    disable = no
    flags = REUSE
    socket_type = stream
    wait = no
    user = root
    server = /usr/sbin/in.telnetd
    log_on_failure += USERID
}
```

# xinetdサービスを起動・再起動する

```bash
sudo systemctl restart xinetd
sudo systemctl status xinetd
```

# ５．IPアドレスを確認する

```bash
ip a
```

# 6. Telnetサーバへ接続する

```bash
telnet <IPアドレス>
```
ユーザー名
```bash
vagrant
```
パスワード
```bash
vagrant
```


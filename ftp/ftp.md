#ftpサーバインストールマニュアル

##　１．vsftpdをインストールする

```bash
sudo apt update
sudo apt install vsftpd -y
```

##　２．起動しているか確認する

```bash
sudo systemct status vsftpd
```

active (running)　が表示されているか確認

##　３．設定ファイルを編集する

```bash
sudo nano /etc/vsftpd.conf

anonymous_enable=NO
local_enable=YES
write_enable=YES
```

##　４．IPアドレスを確認する

```bash
ip a
```

##　５．FTPサーバへ接続する

```bash
ftp <IPアドレス>
```

ユーザ名

```bash
vagrant
```

パスワード

```bash
vagrant
```

#　６．接続の確認

```bash
ftp localhost
```



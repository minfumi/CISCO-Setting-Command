# Switch
## 特権EXECモードに切り替える
```
Switch> enable
Switch#
```

## configuration モードに切り替える
```
Switch# configure terminal
Switch(config)#
```

## hostname を設定する
```
Switch(config)# hostname S1
S1(config)#
```

## グローバルコンフィギュレ―ションモードからIPアドレス設定
```
S1# config t
S1(config)# interface ???
S1(config-if)# ip address ???.???.???.??? ???.???.???.???
S1(config-if)# no shutdown
S1(config-if)# exit
S1(config)# 

## 不要なDNS lookupを防止する
```
S1(config)# no ip domain-lookup
S1(config)#
```

## ローカルパスワードを設定する
### 接続時PASSWORD(cisco)要求
#### コンソールポート
```
S1(config)# line con 0
S1(config-line)# password cisco
S1(config-line)# login
S1(config-line)# exit
```
#### VTY
```
S1(config)# line vty 0 4
S1(config-line)# password cisco
S1(config-line)# login
S1(config-line)# exit
```
### 特権EXECモード移行時PASSWORD(class)を要求
```
S1(config)# enable secret class
```

## ログインバナーを設定する
```
S1(config)# banner motd #
Unauthorized access is strictly prohibited and prosecuted to the full extent of the law. #
S1(config)# exit
S1#
```

## 設定を保存する
copy コマンドを使用して、Non-Volatile Random Access Memory（NVRAM; 不揮発性 RAM）にあるスタートアップ ファイルに実行コンフィギュレーションを保存します。
```
S1# copy running-config startup-config
Destination filename [startup-config]? [Enter]
Building configuration...
[OK]
S1#
```

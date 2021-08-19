# EC2とRDSにrailsアプリをデプロイ

## 準備
private.ymlの準備
```
__database_password:  <DB接続パスワード>
__secret_key_base: <secret key base>
```

## 実行
```
$ ansible-playbook -i hosts site.yml --extra-vars="@private.yml"
```

## roles
### nginx
    nginxのインストール
    nginxのスタート、自動起動


### rails
    nginxの実行ユーザを変更
    gitからプロジェクトファイルを取得
    /etc/nginx/conf.d配下にrails.dを配置

### bundle
    bundle installの実行
    asset:precompireの実行


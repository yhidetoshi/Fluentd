Puppet

- Type Reference
http://docs.puppetlabs.com/references/latest/type.html
- Function Reference
http://docs.puppetlabs.com/references/latest/function.html

- puppetでわからない時はここを読む
⇨http://docs.puppetlabs.com/guides/style_guide.html


- (重要) 私とPuppet ベストプラクティス編 その1 (ディレクトリ構成とその役割)
http://qiita.com/takeuchikzm/items/5e303e03a48ab2f0db1a


- Puppet(サーバ/クライアン)インストール（Server world）
http://www.server-world.info/query?os=CentOS_6&p=puppet


- 書く順番?
```params.pp ⇨ init.pp ⇨  config.pp  ⇨ install.pp ⇨ service.pp```

>
>概要メモ
>params.pp
>⇨ インストールする際に使うファイルや設定の類
>
>init.pp
>⇨ params.ppで定義したコンフィグ設定
>⇨ 開始から終了までの処理順番を定義
>
>config.pp
>⇨ 設定ファイルの定義（パーミッションなど）
>
>install.pp
>⇨ モジュールに必要なパッケージインストールを定義
>
>service.pp
>⇨ デーモンに関しての定義

- puppetサーバにクライアントから適用のリクエストを投げる

```# puppet agent --test --waitforcert 10 --server puppet --certname web-a001-pre.sjdc.in.fluct.me --environment prd```





```/etc/sysconfig/puppet
# The puppetmaster server
PUPPET_SERVER=puppet

# If you wish to specify the port to connect to do so here
#PUPPET_PORT=8140

# Where to log to. Specify syslog to send log messages to the system log.
PUPPET_LOG=/var/log/puppet/puppet.log

# You may specify other parameters to the puppet client here
#PUPPET_EXTRA_OPTS=--waitforcert=500
PUPPET_EXTRA_OPTS=--environment=prd
```


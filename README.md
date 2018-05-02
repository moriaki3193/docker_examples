# Docker Examples

## setup docker-machine with fish
やっていることはシンプル。
1. `start`コマンドでホストを立ち上げ
2. `env`コマンドで、そのホストに接続するための環境変数を設定するshell scriptを表示する
3. そのスクリプトを利用して、実際にホストに接続するために、`eval`している。

```shell
$ docker-machine start MACHINE_NAME  # ホストを立ち上げる
$ docker-machine env MACHINE_NAME  # ローカルの環境変数を更新(今立ち上げたホストに対応させる)
$ eval (docker-machine env default)  # 環境変数を切り替える
```

### 1. docker-machine start MACHINE_NAME
実行すると次のようなメッセージが表示される。

```
Starting "default"...
(default) Check network to re-create if needed...
(default) Waiting for an IP...
Machine "default" was started.
Waiting for SSH to be available...
Detecting the provisioner...
Started machines may have new IP addresses. You may need to re-run the `docker-machine env` command.
```

### 2. docker-machine env MACHINE_NAME
コマンドを実行すると、環境変数を設定するためのスクリプト(スニペット？)が表示される。
`fish`を利用しているので、`fish`に適したスクリプトが表示される。

```
set -gx DOCKER_TLS_VERIFY "1";
set -gx DOCKER_HOST "tcp://192.168.99.100:2376";
set -gx DOCKER_CERT_PATH "/path/to/default"
set -gx DOCKER_MACHINE_NAME "default";
# Run this command to configure your shell:
# eval (docker-machine env default)
```

### 3. eval (docker-machine env MACHINE_NAME)
これを実行すると、環境変数が反映される。
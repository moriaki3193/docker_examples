# Docker Hands On
- [Reference](https://github.com/kakakakakku/docker-hands-on)
- [docker-machine create](http://docs.docker.jp/machine/get-started.html)

## Prerequisities
| tool name | description |
|:----------|:------------|
| Docker Client | Dockerを操作するツール (dockerコマンド) |
| Docker Machine | Docker仮想マシンを簡単に構築・管理するためのツール (docker-machineコマンド) |
| Docker Compose | マルチコンテナ・アプリケーションを定義・実行するためのツール(docker-composeコマンド) |

## ケーススタディ
### ミドルウェアのコンテナをイメージにする
イメージ名は任意で良いが、`${USERNAME}/${IMAGENAME}`にする習慣に従う。
`CONTAINER ID`は`docker ps -a`で表示されたものを指定する。

```shell
$ docker commit CONTAINER_ID moriaki3193/manual-httpd
```

`docker commit`を行うと、`docker images`した際にイメージが追加されていることが確認できる。

```shell
$ docker images
REPOSITORY               TAG     IMAGE ID     CREATED        VIRTUAL SIZE
moriaki3193/manual-httpd latest  4021b02c4720 13 seconds ago 257.5 MB
centos                   centos6 a005304e4e74 7 weeks ago    203.1 MB
```

### httpdイメージをMacにポートマッピングした状態で起動する
Macの8080ポートをDockerコンテナの80ポートにマッピングした状態で、
すでに作ったhttpdイメージを起動する。

## Commands
| command | description |
|:--------|:------------|
| docker ps | 稼働しているコンテナを確認する |
| docker run -it centos:centos6 /bin/bash | centos:centos6イメージのbashを対話モードでログインする |
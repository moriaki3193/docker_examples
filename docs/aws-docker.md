# AWS + Docker
目標は、AWSの実行環境にDockerアプリケーションを乗せて運用すること。
Rust製のチャットボットAPIをDocker上に構築し、Recipioと連携させる。

## References
- [Dockerコンテナのデプロイ](https://aws.amazon.com/jp/getting-started/tutorials/deploy-docker-containers/)

## Dockerコンテナのデプロイ
利用するサービスとしては、`Amazon Elastic Container Service (Amazon ECS)`があげられる。Amazon ECSでは、Dockerアプリケーションをスケーラブルなクラスターで実行する環境を提供している。
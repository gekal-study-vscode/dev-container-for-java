# Dev Containers

![architecture containers](images/architecture-containers.png)

## Dev Containersとは

Visual Studio Codeの拡張機能の1つで、Dockerコンテナを使用してVisual Studio Codeのフル機能を使用できる開発環境を構築できる仕組みのこと。

Containerで開発環境の一貫性を持たれます。

## 関連の設定ファイル

```text
.
└─── .devcontainer
    ├── devcontainer.json
    └── Dockerfile
```

### Dev Containerコンフィグ

1. 自由度を上げるため、`Dockerfile`を使ったほうが良い。

    ```jsonc
    "build": {
        // Path is relative to the devcontainer.json file.
        "dockerfile": "Dockerfile",
        "context": ".",
        "args": {}
    },
    ```

2. チームで開発する場合、事前にゴールドイメージをビルドして共有したほうがよい。

3. features

    Dev Containerのほうで事前に用意したfeatureがあるため、こちらを利用すれば手間を省けます。

## Java開発環境例

1. ベースイメージ

    空のベースイメージ: `mcr.microsoft.com/devcontainers/base:bullseye`

2. features

    Javaのfeature: `ghcr.io/devcontainers/features/java`

## 参照

1. [Development Containers](https://containers.dev/)
2. [Developing inside a Container](https://code.visualstudio.com/docs/devcontainers/containers)
3. [Base Development Container Images](https://mcr.microsoft.com/en-us/product/devcontainers/base/about)
4. [Development Containers Images - GitHub](https://github.com/devcontainers/images)

![Frame 294](https://github.com/user-attachments/assets/0656ab69-4352-452b-a8f4-1c05cec108d1) ![Frame 292](https://github.com/user-attachments/assets/49db0363-3f89-48a1-ba2b-e30bd5d083b3)

# PeterCat

<div align="center">

<img src="https://gw.alipayobjects.com/zos/antfincdn/R8sN%24GNdh6/language.svg" width="18"> [简体中文](./README.md) | [English](./README.en-US.md) | 日本語

**コミュニティメンテナと開発者のために特別に設計されたインテリジェント Q&A ボットソリューション。**

[![npm](https://img.shields.io/npm/dm/@petercatai/assistant.svg)](https://www.npmjs.com/package/@petercatai/assistant) [![Version](https://img.shields.io/npm/v/petercat-lui/latest.svg)](https://www.npmjs.com/package/petercat-lui) [![DockerHub Version](https://img.shields.io/docker/v/petercatai/petercat?logo=docker&logoColor=white)](https://hub.docker.com/r/petercatai/petercat) [![CI Test Status](https://github.com/petercat-ai/petercat/actions/workflows/pr-tests.yml/badge.svg)](https://github.com/petercat-ai/petercat/actions/workflows/pr-tests.yml) [![codecov](https://codecov.io/github/petercat-ai/petercat/graph/badge.svg?token=2HAO18FB6X)](https://codecov.io/github/petercat-ai/petercat) [![License](https://img.shields.io/badge/License-MIT%40Peter%20Cat-yellow.svg)](https://github.com/petercat-ai/petercat/blob/master/LICENSE)

</div>

## 🏠 ホームページ

[🐱Nest: petercat.ai](https://petercat.ai)

## ✨ 特徴

会話型 Q&A エージェントの構成システム、自ホスト型デプロイメントソリューション、および便利なオールインワンアプリケーション SDK を提供し、GitHub リポジトリのためのインテリジェント Q&A ボットをワンクリックで作成し、さまざまな公式ウェブサイトやプロジェクトに迅速に統合し、コミュニティのためのより効率的な技術サポートエコシステムを提供します。

### 会話で作成

リポジトリのアドレスまたは名前を提供するだけで、Peter Cat がボットの作成プロセス全体を自動的に完了します。

![Create with Conversations](https://mdn.alipayobjects.com/huamei_j8gzmo/afts/img/A*aQ9uRoNZGe8AAAAAAAAAAAAADrPSAQ/original)

### 自動化されたナレッジベース

ボットが作成されると、関連するすべての GitHub ドキュメントと問題が自動的にナレッジベースに追加され、ボットの知識源となります。

![Automated Knowledge Base](https://mdn.alipayobjects.com/huamei_j8gzmo/afts/img/A*hkkFSaR1UqgAAAAAAAAAAAAADrPSAQ/original)

### マルチプラットフォーム統合

公式ウェブサイトへの SDK 統合や GitHub リポジトリへのワンクリックインストールなど、さまざまな統合オプションを提供します。

| ![Website](https://mdn.alipayobjects.com/huamei_j8gzmo/afts/img/A*REw3QYgdJ44AAAAAAAAAAAAADrPSAQ/original) | ![GitHub](https://mdn.alipayobjects.com/huamei_j8gzmo/afts/img/A*jlYzSqlcpRIAAAAAAAAAAAAADrPSAQ/original) |
| :-: | :-: |

## エージェントワークフロー

![Agent workflow](https://mdn.alipayobjects.com/huamei_j8gzmo/afts/img/A*m24tTIZpW7cAAAAAAAAAAAAADrPSAQ/original)

## 📦 自ホスト型デプロイメント

デプロイメントソリューション: [AWS](https://aws.amazon.com) + [Supabase](https://supabase.com)

完全なガイドはこちらで見つけることができます:

- [Self-Hosting - Start the Service Locally](./docs/guides/self_hosted_local.md)
- [Self-Hosting - Deploy to AWS](./docs/guides/self_hosted_aws.md)

![Deployment Solution](https://mdn.alipayobjects.com/huamei_j8gzmo/afts/img/A*0_aUTJpyx1YAAAAAAAAAAAAADrPSAQ/original)

[![Self hosted Video](https://mdn.alipayobjects.com/huamei_j8gzmo/afts/img/A*spdZSbWsVhkAAAAAAAAAAAAADrPSAQ/fmt.webp)](https://www.youtube.com/watch?v=Al6R9Ye5mBY)

## ⚙️ 環境変数

プロジェクトには環境変数の設定が必要です:

### クライアント

`.env.local`

| 環境変数 | タイプ | 説明 | 例 |
| --- | --- | --- | --- |
| `NEXT_PUBLIC_API_DOMAIN` | 必須 | バックエンドサービスの API ドメイン | `https://api.petercat.ai` |

### サーバー

`.env`

| 環境変数 | タイプ | 説明 | 例 |
| --- | --- | --- | --- |
| **基本アプリケーション環境変数** |
| `API_URL` | 必須 | バックエンドサービスの API ドメイン | `https://api.petercat.ai` |
| `WEB_URL` | 必須 | フロントエンドウェブサービスのドメイン | `https://petercat.ai` |
| `STATIC_URL` | 必須 | 静的リソースドメイン | `https://static.petercat.ai` |
| **AWS 関連環境変数** |
| `X_GITHUB_SECRET_NAME` | 必須 | AWS シークレットファイル名 | `prod/githubapp/petercat/pem` |
| `STATIC_SECRET_NAME` | オプション | AWS が管理する CloudFront のプライベートキーの名前。設定されている場合、CloudFront の署名付き URL が使用され、リソースが保護されます。詳細については、[AWS ドキュメント](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-trusted-signers.html)を参照してください。 | `prod/petercat/static` |
| `LLM_TOKEN_SECRET_NAME` | オプション | AWS が管理する LLM 署名プライベートキーの名前。設定されている場合、Petercat は RSA アルゴリズムを使用してユーザーの LLM トークンを管理します。 | `prod/petercat/llm` |
| `LLM_TOKEN_PUBLIC_NAME` | オプション | AWS が管理する LLM 署名公開キーの名前。設定されている場合、Petercat は RSA アルゴリズムを使用してユーザーの LLM トークンを管理します。 | `prod/petercat/llm/pub` |
| `STATIC_KEYPAIR_ID` | オプション | AWS CloudFront のキー ID。設定されている場合、CloudFront の署名付き URL が使用され、リソースが保護されます。詳細については、[AWS ドキュメント](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-trusted-signers.html)を参照してください。 | `APKxxxxxxxx` |
| `S3_TEMP_BUCKET_NAME` | 必須 | 一時的な画像ファイル用の AWS S3 バケット | `xxx-temp` |
| **Supabase 関連環境変数** |
| `SUPABASE_URL` | 必須 | Supabase サービス URL、[こちら](https://supabase.com/dashboard/project/_/settings/database)で見つけることができます | `https://***.supabase.co` |
| `SUPABASE_SERVICE_KEY` | 必須 | Supabase サービスキー、[こちら](https://supabase.com/dashboard/project/_/settings/database)で見つけることができます | `{{SUPABASE_SERVICE_KEY}}` |
| **Auth0 関連環境変数** |
| `AUTH0_DOMAIN` | 必須 | Auth0 ドメイン、Auth0 / Application / Basic Information から取得 | `petercat.us.auth0.com` |
| `AUTH0_CLIENT_ID` | 必須 | Auth0 クライアント ID、Auth0 / Application / Basic Information から取得 | `artfiUxxxx` |
| `AUTH0_CLIENT_SECRET` | 必須 | Auth0 クライアントシークレット、Auth0 / Application / Basic Information から取得 | `xxxx-xxxx-xxx` |
| `API_IDENTIFIER` | 必須 | Auth0 API 識別子 | `https://petercat.us.auth0.com/api/v2/` |
| **LLM 関連環境変数** |
| `OPENAI_API_KEY` | 必須 | OpenAI API キー | `sk-xxxx` |
| `OPENAI_BASE_URL` | オプション | API リクエストのためのベース URL。プロキシやサービスエミュレーターを使用する場合のみ指定します。 | `https://api.openai.com/v1` |
| `GEMINI_API_KEY` | オプション | Gemini API キー | `xxxx` |
| `TAVILY_API_KEY` | オプション | Tavily API キー | `tvly-xxxxx` |
| **GitHub App 登録環境変数** |
| `X_GITHUB_APP_ID` | オプション | GitHub App ID | `123456` |
| `X_GITHUB_APPS_CLIENT_ID` | オプション | GitHub App クライアント ID | `Iv1.xxxxxxx` |
| `X_GITHUB_APPS_CLIENT_SECRET` | オプション | GitHub App クライアントシークレット | `xxxxxxxx` |
| **レート制限構成** |
| `RATE_LIMIT_ENABLED` | オプション | レート制限が有効かどうか | `True` |
| `RATE_LIMIT_REQUESTS` | オプション | レート制限のリクエスト数 | `100` |
| `RATE_LIMIT_DURATION` | オプション | レート制限の期間（分単位） | `1` |
| **RAG server config** |
| `WHISKER_API_URL` | 必須 | WHISKER RAG Server Path | `http://....` |
| `WHISKER_API_KEY` | 必須 | WHISKER RAG Server KEY | `sk-xxxx` |

## 🤝 貢献

> Peter Cat は yarn をパッケージマネージャーとして使用しています。

```bash
git clone https://github.com/petercat-ai/petercat.git

# 依存関係をインストール
yarn run bootstrap

# クライアントをデバッグ
yarn run client

# アシスタントをデバッグ
yarn run assistant

# サーバーをデバッグ
yarn run server

# ローカルでウェブサイトを開始
yarn run client:server

# ローカルでアシスタントコンポーネントを開始
yarn run assistant:server

# アシスタントをビルド
cd assistant
yarn run build
npm publish

# Dockerビルド
yarn run build:docker

# PyPIビルド
yarn run build:pypi
yarn run publish:pypi
```

## 💼 エンタープライズ統合

プロジェクトのアドレス、使用シナリオ、使用頻度などの情報を[petercat.assistant@gmail.com ](petercat.assistant@gmail.com)に送信してください。

## 📧 問題の報告

Peter Cat はまだ成長段階にあり、時折「癇癪」を起こすことがあります。以下のチャンネルを通じて問題を報告してください：

- [Submit an Issue(https://github.com/petercat-ai/petercat/issues/new/choose)
- [Discussions](https://github.com/petercat-ai/petercat/discussions)

👬 貢献者

![https://github.com/petercat-ai/petercat/graphs/contributors](https://contrib.rocks/image?repo=petercat-ai/petercat)

## 📄 ライセンス

MIT@[PeterCat](https://github.com/petercat-ai/petercat/blob/main/LICENSE)

# aspire-sample-app

.NET Aspire を使って、Web フロントエンドと API サービスをオーケストレーションするサンプルアプリです。

## このリポジトリの目的

- .NET Aspire の基本構成（AppHost / ServiceDefaults / API / Web）を最小構成で確認する
- サービスディスカバリ、ヘルスチェック、OpenTelemetry などの標準連携を試す
- ローカルでの起動・疎通確認手順を共有する

## 構成

- `AspireSampleApp.AppHost`  
  分散アプリのエントリーポイント。`ApiService` と `Web` を起動し、依存関係を構成します。
- `AspireSampleApp.ServiceDefaults`  
  サービス共通設定（OpenTelemetry、ヘルスチェック、サービスディスカバリ、HTTP クライアント設定）を提供します。
- `AspireSampleApp.ApiService`  
  `GET /weatherforecast` を提供する ASP.NET Core Minimal API です。
- `AspireSampleApp.Web`  
  Blazor Web アプリ。`ApiService` を呼び出して天気情報を表示します。
- `AspireSampleApp.sln`  
  ソリューションファイルです。

## 検証ポイント

1. 依存関係の復元とビルド
   - `dotnet build AspireSampleApp.sln`
2. アプリ起動
   - `dotnet run --project AspireSampleApp.AppHost`
3. 動作確認
   - Web フロントエンドが起動すること
   - `/weather` 画面で API のデータが表示されること
   - 開発環境で `/health` と `/alive` が応答すること

## GitHub リポジトリ Description（例）

`.NET Aspire sample app with AppHost, API service, Blazor Web frontend, and observability defaults.`
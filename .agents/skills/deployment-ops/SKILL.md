---
name: deployment-ops
description: >-
  コンテナ化 (Docker)、CI/CD パイプライン構成、環境設定、ビルド、デプロイ検証および運用手順をサポートするスキル。
---

# デプロイ・運用スキル (Deployment & Operations Skill)

このスキルは、作成されたアプリケーションを本番環境・検証環境へ安全にデプロイし、再現可能な運用構成を構築するためのガイドラインを提供します。

---

## 主な手順

### 1. コンテナ化 (Docker化)
- マルチステージビルドを活用した軽量な `Dockerfile` の作成
- ローカル検証用 `docker-compose.yml` の作成

### 2. CI/CD パイプライン構成
- GitHub Actions または GitLab CI 用のワークフロー定義
- 自動テスト、静的解析、イメージビルド、デプロイの自動化

### 3. 環境設定と環境変数管理
- 本番・検証・開発環境の構成分離
- シークレット情報 (Secret) の適切な管理手法の確立

### 4. デプロイ後検証 (Post-Deployment Verification)
- ヘルスチェックエンドポイント (`/health` や `/status`) の実行
- ログ確認と動作検証

---

## テンプレート例 (`Dockerfile` / `docker-compose.yml`)

```dockerfile
# Node.js マルチステージビルド例
FROM node:20-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM node:20-alpine AS runner
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production
COPY --from=builder /app/dist ./dist
EXPOSE 3000
CMD ["node", "dist/index.js"]
```

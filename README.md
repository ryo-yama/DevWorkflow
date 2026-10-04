# 🤖 AI-Driven Full-Stack Development Workflow (`.agents`)

本リポジトリは、新規・既存のプロジェクトに **`.agents` ディレクトリをコピー配置するだけ** で、AI アシスタント（Antigravity 等）を活用した「要件定義 → 仕様策定 → 設計 → 実装 → テスト → デプロイ」の一連の開発フローを自律的かつ安全に推進できる **ポータブル AI スキルパッケージ** です。

---

## 🎯 本パッケージの目的

個人開発やチーム開発において、アイデア段階から本番デプロイまでの開発ライフサイクル全般を AI にサポートさせつつ、以下の課題を解決することを目的としています。

1. **プロジェクト初期化の手間の削減**: 設定やフォルダ作成不要で、`.agents` を置くだけでスタート。
2. **手戻りの防止**: 要件定義・仕様策定・設計・テストなどの重要局面で確実な合意形成（Stop Conditions）を行う。
3. **開発の停滞防止**: 判断に迷う仕様決定待ちが発生しても、申し送り事項（Pending Issues）に記録して別タスクを並行進行させる。

---

## ✨ 主な特徴と仕組み

### 1. 📦 完全ポータブル設計 (`.agents/`)
テンプレート、開発ルール、個別フェーズ用スキルがすべて `.agents/` ディレクトリ内に集約されています。

### 2. ⚡ 自動環境初期化 (Bootstrap)
初回実行時、AI が `.agents/templates/` 内の各種テンプレートを参照し、プロジェクトルート配下に `docs/` や申し送り管理ファイル (`docs/pending_issues.md`) を自動生成します。

### 3. 📋 申し送り事項 (Pending Issues) の自動管理
作業中にユーザーの意思決定待ちや外部依存が発生した場合、AI は作業を完全停止させず、`docs/pending_issues.md` に課題を記録した上で、ブロッカーにならない他のタスク（例: UI決定待ちの間にDB設計を進める）へ自動移行します。

### 4. 🛑 明確な停止・承認条件 (Stop Conditions & Approval Gates)
以下の重要な節目では AI は自動進行を停止し、ユーザーのレビュー・合意（Proceed）を得てから次工程に進みます。
- 要件定義書 (`docs/requirements.md`) 完成時
- 仕様書 (`docs/specifications.md`) 完成時
- アーキテクチャ設計書 (`docs/design.md`) 完成時
- 主要マイルストーンの実装完了時
- テスト実行・品質検証結果の確認時
- 実環境 / インフラへのデプロイ実行直前

---

## 📂 `.agents` パッケージ構造

```
.agents/
├── README.md               # スキルセットの利用マニュアル
├── docs/                   # AIスキル自体の管理・保守ガイドライン
├── templates/              # 各種初期ドキュメントのテンプレート群
│   ├── prompt-template.md  # 開発指示用プロンプトテンプレート
│   ├── pending_issues.md   # 申し送り課題管理表の雛形
│   ├── requirements.md     # 要件定義書の雛形
│   ├── specifications.md   # 仕様書の雛形
│   └── design.md           # 設計書の雛形
└── skills/                 # 各開発フェーズを実行する AI スキル
    ├── full-stack-workflow/
    ├── requirements-definition/
    ├── specification-authoring/
    ├── architecture-design/
    ├── implementation-guide/
    ├── testing-quality/
    └── deployment-ops/
```

---

## 🚀 使い方（新規/既存プロジェクトへの導入）

### Step 1. `.agents` ディレクトリのコピー
本リポジトリの `.agents` ディレクトリを、開発したいプロジェクトのルートディレクトリにコピー＆ペーストします。

### Step 2. AI アシスタントへ指示を送信
AI アシスタント（Antigravity 等）に対し、以下のプロンプトを送信してください。

```markdown
`full-stack-workflow` スキルに従って、以下のアイデアから開発フロー（要件定義→仕様作成→設計→実装→テスト→デプロイ）を開始してください。

■ 作りたいものの概要:
【例: 個人開発者向けのタスク・習慣管理ダッシュボード】

■ 解決したい課題 / 背景:
【例: シンプルに日々の習慣化とタスク完了率を視覚化したい。】

■ 希望する技術スタック (任意):
【例: Next.js (TypeScript), Supabase, Tailwind CSS など】

※ 初回実行時に docs/ や申し送り管理ファイルが未作成の場合、自動的に作成・初期化してください。
まず最初はステップ1の「要件定義 (requirements-definition)」から開始してください。
```

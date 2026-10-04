# 🤖 Portable AI Agent Skills (`.agents/`)

この `.agents` ディレクトリは、新規プロジェクトや既存プロジェクトに**コピー配置するだけ**で、Antigravity などの AI アシスタントを用いたフルスタック AI 駆動開発（要件定義〜デプロイ）を即座に開始できるようにパッケージ化されたスキルセットです。

---

## 🚀 使い方（クイックスタート）

1. 本 `.agents` ディレクトリを新規プロジェクトのルート配下にコピー・配置します。
2. AI アシスタント（Antigravity 等）に対して、以下のプロンプトを送信してください。

### コピペ用プロンプト

```markdown
`full-stack-workflow` スキルに従って、以下のアイデアから開発フロー（要件定義→仕様作成→設計→実装→テスト→デプロイ）を開始してください。

■ 作りたいものの概要:
【例: 個人開発者向けのタスク・習慣管理ダッシュボード】

■ 解決したい課題 / 背景:
【例: シンプルに日々の習慣化とタスク完了率を視覚化したい。】

■ 希望する技術スタック (任意):
【例: Next.js (TypeScript), Supabase, Tailwind CSS など】

※ 初回実行時に `docs/` や申し送り管理ファイルが未作成の場合、自動的に作成・初期化してください。
まず最初はステップ1の「要件定義 (requirements-definition)」から開始してください。
```

---

## 📂 フォルダ構成と収録スキル

### 1. スキル定義 (`.agents/skills/`)
- `full-stack-workflow`: 開発プロセス全体を進行管理・統括し、判断留保事項（`docs/pending_issues.md`）の管理とフェーズごとの承認ポイントを制御します。
- `requirements-definition`: アイデアから要件定義書 (`docs/requirements.md`) を作成。
- `specification-authoring`: データモデル・API仕様書 (`docs/specifications.md`) を作成。
- `architecture-design`: アーキテクチャ設計書 (`docs/design.md`) を作成。
- `implementation-guide`: 設計に準拠した型安全なコード実装を指導。
- `testing-quality`: テストコードの作成と品質検証を実行。
- `deployment-ops`: Docker / CI/CD などのデプロイ設定を作成・検証。

### 2. 内蔵テンプレート (`.agents/templates/`)
新規プロジェクトへの配置時、AI が自動初期化（Phase 0: Bootstrap）を行う際に参照する標準ドキュメントテンプレート群です。
- `pending_issues.md`: 判断保留・申し送り管理用テンプレート
- `requirements.md` / `specifications.md` / `design.md`: 各設計書の雛形テンプレート
- `prompt-template.md`: 開発指示用テンプレート

### 3. ドキュメントガイド (`.agents/docs/`)
- `skills-management.md`: スキル自体の作成・保守・拡張ガイドライン

# Full-Stack Development AI Skills Project

本プロジェクトは、**「作りたいものの要求を入力すると、要件定義 → 仕様作成 → 設計 → 実装 → テスト → デプロイまでの一連の開発フローを AI にサポートしてもらう」** ための SKILLS.md （Antigravity スキルセット）を作成・管理・最適化するリポジトリです。

---

## 📁 スキル構成一覧 (`.agents/skills/`)

| スキル名 | ディレクトリ | 概要・役割 |
| :--- | :--- | :--- |
| **`full-stack-workflow`** | [.agents/skills/full-stack-workflow/SKILL.md](file:///home/cheesecake/Src/.agents/skills/full-stack-workflow/SKILL.md) | 要件定義〜デプロイまでの開発ライフサイクル全体を進行管理する統合統括マスターガイド |
| **`requirements-definition`** | [.agents/skills/requirements-definition/SKILL.md](file:///home/cheesecake/Src/.agents/skills/requirements-definition/SKILL.md) | 背景・目的・機能/非機能要件・ユースケースの整理と要件定義書の作成 |
| **`specification-authoring`** | [.agents/skills/specification-authoring/SKILL.md](file:///home/cheesecake/Src/.agents/skills/specification-authoring/SKILL.md) | データモデル、API仕様、UI/画面遷移仕様、ビジネスロジック詳細の策定 |
| **`architecture-design`** | [.agents/skills/architecture-design/SKILL.md](file:///home/cheesecake/Src/.agents/skills/architecture-design/SKILL.md) | 技術選定、ディレクトリ構造、コンポーネント分離、セキュリティ設計 |
| **`implementation-guide`** | [.agents/skills/implementation-guide/SKILL.md](file:///home/cheesecake/Src/.agents/skills/implementation-guide/SKILL.md) | 段階的実装、型安全性・コーディング規約遵守、リファクタリング指導 |
| **`testing-quality`** | [.agents/skills/testing-quality/SKILL.md](file:///home/cheesecake/Src/.agents/skills/testing-quality/SKILL.md) | 単体/結合テスト作成、品質チェック、自動テスト実行・検証 |
| **`deployment-ops`** | [.agents/skills/deployment-ops/SKILL.md](file:///home/cheesecake/Src/.agents/skills/deployment-ops/SKILL.md) | Dockerコンテナ化、CI/CDワークフロー構成、環境設定、デプロイ検証 |

---

## 🚀 使い方

ユーザーが新しいプロダクトや機能を作成したい場合、以下のように AI アシスタントへ指示を出します。

### 1. フロー全体を開始する場合
入力用テンプレート: [docs/prompt-template.md](file:///home/cheesecake/Src/docs/prompt-template.md) を使用して、アイデアや概要を入力してください。
> 例: 「`full-stack-workflow` スキルに従って、〇〇のアイデアから開発フローを開始してください。」

### 2. 特定のフェーズのみ実行・相談する場合
> 「現在機能要件が固まっているので、`specification-authoring` スキルを使って API 仕様とデータモデルを作成してください。」

---

## ⚙️ スキルのカスタマイズ・最適化

既存のスキルをプロジェクト固有の規約やチームの運用に合わせて編集・拡張する場合は、対象の `SKILL.md` を編集するか、新しいスキルを `.agents/skills/<skill-name>/SKILL.md` に追加してください。

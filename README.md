# 🚀 Gemini CLI テンプレート

> Gemini CLI を効率的に活用するためのベストプラクティステンプレート集

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 📋 概要

社内で Gemini CLI を利用する際に、`.gemini` フォルダの構成や各設定ファイルをバラバラに管理するのではなく、**統一されたベストプラクティス**に基づいてプロジェクトを構築するためのテンプレートです。

- **Gemini CLI** 最新版のベストプラクティスを反映
- **Claude Code** のベストプラクティスで Gemini にも適用可能なものを取り入れ
- コンテキスト管理、ワークフロー設計、スキル・サブエージェントのモジュール化

## 🗂️ テンプレート構成

```
template/
├── .geminiignore              # AI除外設定（.gitignore形式）
└── .gemini/
    ├── GEMINI.md              # プロジェクトコンテキスト（最重要）
    ├── AGENT.md               # エージェント定義・振る舞い
    ├── settings.json          # プロジェクト固有の設定
    ├── prompts/               # 汎用プロンプト集
    │   ├── code-review.md
    │   ├── refactoring.md
    │   └── documentation.md
    ├── tools/                 # カスタムツール定義
    ├── agents/                # サブエージェント（experimental）
    │   ├── code-reviewer/
    │   └── git-assistant/
    ├── skills/                # スキル定義
    │   ├── tdd-workflow/
    │   ├── code-refactoring/
    │   ├── bug-investigation/
    │   └── project-setup/
    ├── workflows/             # 開発フロー
    │   ├── development.md
    │   └── release.md
    └── rules/                 # コーディング規約
        ├── general.md
        └── _TEMPLATE.md
```

## 🚀 クイックスタート

### 1. テンプレートをプロジェクトにコピー

```bash
# .gemini フォルダをプロジェクトルートにコピー
cp -r template/.gemini /path/to/your-project/.gemini

# .geminiignore もプロジェクトルートにコピー
cp template/.geminiignore /path/to/your-project/.geminiignore
```

### 2. 必須設定を編集

| ファイル | 説明 | 優先度 |
|---------|------|--------|
| `.gemini/GEMINI.md` | プロジェクトの概要・技術スタック・フォルダ構成 | ⭐⭐⭐ 必須 |
| `.gemini/AGENT.md` | エージェントのペルソナ・作業ルール | ⭐⭐⭐ 必須 |
| `.gemini/rules/` | コーディング規約（言語別に作成） | ⭐⭐ 推奨 |
| `.gemini/settings.json` | モデル・チェックポイント設定 | ⭐ 任意 |

### 3. 言語別のカスタマイズ

```bash
# 例: TypeScript用の規約ファイルを作成
cp .gemini/rules/_TEMPLATE.md .gemini/rules/typescript.md
```

## 📝 ベストプラクティス

| ✅ やるべきこと | ❌ やってはいけないこと |
|---------------|----------------------|
| GEMINI.md を 300行以下に収める | すべての情報を1ファイルに詰め込む |
| `@include` で情報を分割する | 巨大なコンテキストファイルを作る |
| 禁止事項を明確に記載する | 暗黙の前提に頼る |
| 技術スタックを明記する | 自明な情報を省略する |
| 具体的な指示を出す | 曖昧な指示で結果を期待する |

## 📖 ドキュメント

- **[利用ガイド（GUIDE.md）](GUIDE.md)** - 各ファイルの詳細な説明とカスタマイズ方法
- **[仕様書（SPEC.md）](SPEC.md)** - テンプレート作成の背景と要件

## 🤝 コントリビューション

テンプレートの改善提案やフィードバックは Issue または Pull Request でお願いします。

## 📄 ライセンス

MIT License

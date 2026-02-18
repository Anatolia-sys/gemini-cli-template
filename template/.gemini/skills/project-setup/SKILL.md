---
name: プロジェクト初期セットアップ
description: 新規プロジェクトの初期構築を標準化するスキル。環境構築からCI/CDまでを一気通貫で設定する
---

# プロジェクト初期セットアップ スキル

新規プロジェクトを開始する際の初期セットアップを標準化します。
リポジトリ作成からCI/CD設定まで、プロジェクトの土台を一気に構築します。

## 前提条件

- Git がインストールされていること
- 使用する言語のランタイムがインストールされていること
- GitHub / GitLab 等のアカウントがあること

## 手順

### ステップ 1: リポジトリ初期化 📁

1. プロジェクトディレクトリを作成する
2. Git リポジトリを初期化する
3. `.gitignore` を設定する
4. `.geminiignore` を設定する

```bash
# リポジトリ作成
mkdir project-name && cd project-name
git init

# .gitignore を言語に合わせて生成
# https://www.toptal.com/developers/gitignore から取得
```

### ステップ 2: プロジェクト構造の作成 🏗️

1. ディレクトリ構成を作成する
2. パッケージマネージャの初期化
3. 必要な依存パッケージをインストール

#### 標準ディレクトリ構成

```
project-root/
├── src/               # ソースコード
│   ├── components/    # UIコンポーネント（フロントエンド）
│   ├── services/      # ビジネスロジック
│   ├── models/        # データモデル
│   ├── utils/         # ユーティリティ関数
│   └── config/        # 設定ファイル
├── tests/             # テストコード
│   ├── unit/          # ユニットテスト
│   └── integration/   # 統合テスト
├── docs/              # ドキュメント
├── scripts/           # ビルド・デプロイスクリプト
├── .gemini/           # Gemini CLI設定
├── .github/           # GitHub Actions
│   └── workflows/
├── .gitignore
├── .geminiignore
├── README.md
├── LICENSE
└── CHANGELOG.md
```

### ステップ 3: 開発環境設定 ⚙️

1. リンター / フォーマッターを設定する
2. エディタ設定を統一する（`.editorconfig`）
3. Git フック（pre-commit）を設定する

#### .editorconfig テンプレート
```ini
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false

[*.py]
indent_size = 4

[Makefile]
indent_style = tab
```

### ステップ 4: ドキュメント整備 📝

1. `README.md` を作成する（プロジェクト概要、セットアップ手順）
2. `.gemini/GEMINI.md` を作成する
3. `CHANGELOG.md` を作成する
4. `LICENSE` を選択・配置する
5. `CONTRIBUTING.md` を作成する（チームプロジェクトの場合）

### ステップ 5: CI/CD 設定 🔄

1. CI パイプラインを設定する（テスト・リント自動実行）
2. CD パイプラインを設定する（自動デプロイ、必要に応じて）

#### GitHub Actions テンプレート例

```yaml
# .github/workflows/ci.yml
name: CI
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup
        # 言語に応じたセットアップ
      - name: Install dependencies
        # 依存パッケージのインストール
      - name: Lint
        # リンターの実行
      - name: Test
        # テストの実行
```

### ステップ 6: 初回コミット 🎉

1. すべてのファイルをステージングする
2. 初回コミットを行う
3. リモートリポジトリにプッシュする

```bash
git add -A
git commit -m "chore: initial project setup"
git remote add origin <repository-url>
git push -u origin main
```

## チェックリスト

- [ ] リポジトリを初期化した
- [ ] ディレクトリ構成を作成した
- [ ] パッケージを初期化し依存関係をインストールした
- [ ] リンター・フォーマッターを設定した
- [ ] `.editorconfig` を作成した
- [ ] Git フック（pre-commit）を設定した
- [ ] README.md を作成した
- [ ] .gemini/ を設定した
- [ ] .gitignore / .geminiignore を設定した
- [ ] CI/CD を設定した
- [ ] 初回コミット・プッシュを行った

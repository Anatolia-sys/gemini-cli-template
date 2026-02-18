# Gemini CLI用の資料作成
## 目的
社内でGemini CLIを用いている。現在、GEMINI.mdや.gemini配下のファイルに関してバラバラに使用しており、ノウハウもないため試行錯誤しながら使用している。
今回はベストプラクティスにのっとってテンプレートを作成し、配布したいと思っている。

## 要件
- Gemini CLI、Claude Codeのベストプラクティスを調査する。
- ベストプラクティスにのっとったテンプレートを作成する。
- テンプレートの利用方法を記載した資料を作成する。

## 成果物
- テンプレートファイル、フォルダ構成
- 利用方法を記載した資料


## 補足
- テンプレートには必ず以下の内容を含めること
    - .gemini/GEMINI.md *プロジェクト全体の概要、ゴール、制約条件、どこにどのフォルダがあるかなどを記載
    - .gemini/AGENT.md *エージェントの定義、役割分担
    - .gemini/config.toml
    - .gemini/prompts *汎用的に使用できるプロンプトをまとめる
    - .gemini/tools *使用できるツール、カスタムツールの作成
    - .gemini/agents *サブエージェントを保管
    - .gemini/workflows *開発フローを記載
    - .gemini/rules *コーディング規約を記載
    - .gemini/skills *スキルを記載
    - .gemini/settings.json *設定ファイルを記載


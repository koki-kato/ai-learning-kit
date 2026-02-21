# AI学習キット for Claude Code

プログラミング学習をサポートするAIエージェント設定キットです。

Claude Code にルールを設定して、**AIを自分だけの先生**にします。

## 何が入っている？

### ルール = AIの行動指針
`.claude/rules/` に定義されたルールが**常に有効**になります。

| ルールファイル | 内容 |
|--------------|------|
| `teaching.md` | 教え方の基本（日本語で回答、考え方→ヒント→コードの順で教える） |
| `hint.md` | ヒントベース教育（答えを書かず3段階のヒントで導く） |
| `documentation.md` | 公式ドキュメント参照（URLを根拠に説明する） |
| `progress.md` | 進捗管理（MDファイルでタスクリストを自動作成・管理） |

## セットアップ

### 前提
- Node.js（[nodejs.org](https://nodejs.org/) からLTS版をインストール）
- Claude Code（`npm install -g @anthropic-ai/claude-code`）

### 導入方法

#### 方法1: git clone（おすすめ）
```bash
git clone https://github.com/koki-kato/ai-learning-kit.git my-learning
cd my-learning
claude
```

#### 方法2: ZIPダウンロード
1. このページの **「Code」→「Download ZIP」** をクリック
2. ダウンロードしたZIPを展開
3. フォルダ名を `my-learning` など好きな名前に変更
4. ターミナルでそのフォルダに移動して `claude` で起動

### 確認
```bash
ls -la
```
`CLAUDE.md` と `.claude/` が見えればOKです。

## 使い方

学習フォルダで Claude Code を起動するだけ:
```bash
claude
```

ルールは自動で読み込まれるので、特別なコマンドは不要です。

### 普通に質問する
```
JavaScriptで変数を作る方法を教えて
```
→ 考え方を説明 → ヒントを出す → コードを見せる、の順で教えてくれます。

### エラーを聞く
```
このエラーの意味が分からない
```
→ エラーの意味 → 原因 → ヒントの順で説明し、公式ドキュメントのURLも添えてくれます。

### 課題に取り組む
```
じゃんけんゲームを作りたい
```
→ 自動でステップに分解し、進捗管理用のMDファイルを作成。1ステップずつ導いてくれます。

## ファイル構成

```
my-learning/
├── README.md              ← このファイル
├── CLAUDE.md              ← ルールの概要（AIの役割を定義）
└── .claude/
    └── rules/             ← 詳細なルール（常に有効）
        ├── teaching.md    ← 教え方の基本原則
        ├── hint.md        ← ヒントベース教育
        ├── documentation.md ← 公式ドキュメント参照
        └── progress.md    ← 進捗管理
```

## 困ったとき

| 症状 | 対処法 |
|------|--------|
| `claude: command not found` | Node.js のインストールからやり直す |
| ルールが効いていない気がする | `.claude/rules/` フォルダの場所を確認 |
| その他 | 講師に聞いてください |

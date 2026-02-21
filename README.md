# AI学習キット for Claude Code

プログラミング学習をサポートするAIエージェント設定キットです。

Claude Code にルールとスキルを設定して、**AIを自分だけの先生**にします。

## 何が入っている？

### ルール（CLAUDE.md）= 校則
AIが**常に守る**基本的な振る舞いのルールです。

- 日本語で回答
- いきなり答えを書かず、まず考え方を説明
- エラーはすぐ直さず、意味→原因→ヒントの順で説明
- コードに日本語コメントを付ける

### スキル = 授業
`/コマンド名` で**呼んだときだけ動く**操作です。

| スキル | 用途 |
|--------|------|
| `/explain` | コードを1行ずつ丁寧に解説 |
| `/hint` | 答えを書かずにヒントだけ出す（3段階） |
| `/step-by-step` | 課題を小さなステップに分解して進める |

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

学習フォルダで Claude Code を起動:
```bash
claude
```

### /explain - コード解説
```
/explain index.html
/explain この関数を解説して
```
コードの意味を1行ずつ解説してくれます。

### /hint - ヒント
```
/hint エラーが出て動かない
/hint for文の書き方が分からない
```
答えを書かずに、考え方のヒントだけ出します。「もっとヒント」で次の段階へ。

### /step-by-step - ステップバイステップ
```
/step-by-step じゃんけんゲームを作りたい
/step-by-step HTMLで自己紹介ページを作りたい
```
大きな課題を小さなステップに分けて、1つずつ進めます。

## ファイル構成

```
my-learning/
├── README.md              ← このファイル
├── CLAUDE.md              ← ルール（AIの基本動作）
└── .claude/
    └── skills/
        ├── explain/       ← /explain コード解説
        │   └── SKILL.md
        ├── hint/          ← /hint ヒント
        │   └── SKILL.md
        └── step-by-step/  ← /step-by-step ステップ分解
            └── SKILL.md
```

## ルールとスキルの違い

| | ルール（CLAUDE.md） | スキル（SKILL.md） |
|--|-------------------|-------------------|
| 例え | 🏫 校則 | 📚 授業 |
| いつ動く | **常に** | **呼んだときだけ** |
| 設定場所 | プロジェクト直下 | .claude/skills/名前/ |

## 困ったとき

| 症状 | 対処法 |
|------|--------|
| `claude: command not found` | Node.js のインストールからやり直す |
| スキルが動かない | `.claude/skills/` フォルダの場所を確認 |
| その他 | 講師に聞いてください |

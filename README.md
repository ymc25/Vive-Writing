# Vive-Writing 🎙️✍️

音声指示だけで高品質なウェブ記事を生成する「バイブライティング」システム

---

## 🌟 概要

Vive-Writingは、Claude Codeを活用して音声指示のみで高品質なウェブ記事を自動生成するシステムです。参考記事のトーンや文体を学習し、あなたの声だけで魅力的なコンテンツを作成できます。

### 主な特徴

- 🎤 **音声入力**: 音声で記事の内容を指示
- 🤖 **AI生成**: Claude APIによる高品質な記事生成
- 📚 **スタイル学習**: 参考記事からトーンと文体を学習
- ⚡ **効率化**: 執筆時間を大幅に短縮
- 🎯 **カスタマイズ**: トーン、スタイル、構成を自由に調整

---

## 📁 プロジェクト構造

```
Vive-Writing/
├── input/              # 音声入力・指示ファイル
│   ├── audio/         # 音声ファイル
│   ├── transcripts/   # 文字起こし
│   └── instructions/  # 記事作成の指示
├── output/            # 生成された記事
│   ├── drafts/       # 下書き
│   ├── published/    # 完成記事
│   └── archive/      # アーカイブ
├── source/           # 参考記事・スタイルガイド
│   ├── reference-articles/  # 参考記事
│   ├── tone-guides/         # トーンガイド
│   └── style-samples/       # スタイルサンプル
├── config/           # 設定ファイル
│   ├── prompts/     # プロンプトテンプレート
│   ├── settings/    # 各種設定
│   └── workflows/   # ワークフロー定義
├── scripts/          # 自動化スクリプト
└── docs/            # ドキュメント
```

詳細な構造設計については [CLAUDE.md](./CLAUDE.md) を参照してください。

---

## 🚀 クイックスタート

### 1. 参考記事を準備

```bash
# 参考にしたい記事を source/reference-articles/ に配置
cp your-article.md source/reference-articles/
```

### 2. 音声で指示を録音

- スマートフォンやPCで音声を録音
- 記事のテーマ、キーワード、構成を音声で指示
- 録音ファイルを `input/audio/` に保存

### 3. 記事を生成

```bash
# 音声を文字起こし（スクリプト準備中）
python scripts/preprocessing/transcribe.py input/audio/your-audio.mp3

# 記事を生成（スクリプト準備中）
python scripts/generation/generate_article.py input/transcripts/your-audio.txt
```

### 4. 記事をレビュー・編集

生成された下書きは `output/drafts/` に保存されます。内容を確認し、必要に応じて編集してから `output/published/` へ移動します。

---

## 💡 使い方の例

### シナリオ: テクノロジー記事を作成

1. **参考記事の配置**
   ```bash
   # 優れた技術記事を参考資料として配置
   source/reference-articles/tech/ai-trends-2026.md
   source/reference-articles/tech/machine-learning-basics.md
   ```

2. **音声で指示**
   ```
   「今日は2026年のAIトレンドについての記事を書きたいです。
   特に生成AIの進化と、それがビジネスに与える影響について
   3000文字程度で、初心者にも分かりやすく説明してください。」
   ```

3. **AIが生成**
   - 参考記事のトーンと構成を学習
   - 指示内容に基づいて記事を生成
   - `output/drafts/` に保存

---

## 🎨 トーンとスタイルのカスタマイズ

### トーンガイドの作成

`source/tone-guides/` に以下のようなガイドを作成できます：

**formal-professional.md**:
```markdown
# フォーマル・プロフェッショナル

- 敬語を使用
- 専門用語を適切に使用
- 客観的な表現を心がける
- データと事実に基づく
```

**casual-friendly.md**:
```markdown
# カジュアル・フレンドリー

- 親しみやすい口調
- 具体例を多用
- 読者に語りかけるスタイル
- 適度に絵文字を使用
```

---

## 🛠️ 技術スタック（推奨）

- **音声認識**: OpenAI Whisper API / Google Speech-to-Text
- **記事生成**: Claude API (Claude 3.5 Sonnet以上)
- **スクリプト言語**: Python 3.10+
- **設定フォーマット**: YAML
- **記事フォーマット**: Markdown

---

## 📋 ワークフロー

```mermaid
graph LR
    A[音声録音] --> B[文字起こし]
    B --> C[指示書生成]
    C --> D[参考記事学習]
    D --> E[記事生成]
    E --> F[下書き保存]
    F --> G[レビュー・編集]
    G --> H[完成記事]
```

1. **準備**: 参考記事とスタイルガイドを配置
2. **インプット**: 音声で指示を録音
3. **文字起こし**: 音声をテキスト化
4. **生成**: AIが記事を生成
5. **レビュー**: 内容を確認・編集
6. **公開**: 完成記事を保存

---

## 🔧 セットアップ

### 必要な環境

- Python 3.10以上
- Claude API キー
- 音声認識APIキー（オプション）

### インストール（準備中）

```bash
# リポジトリをクローン
git clone https://github.com/ymc25/Vive-Writing.git
cd Vive-Writing

# 依存関係をインストール
pip install -r requirements.txt

# 環境変数を設定
cp .env.example .env
# .envファイルにAPIキーを設定
```

---

## 📚 ドキュメント

- [CLAUDE.md](./CLAUDE.md) - 詳細なプロジェクト構造設計
- [docs/guides/](./docs/guides/) - 使い方ガイド（準備中）
- [docs/examples/](./docs/examples/) - サンプル記事（準備中）
- [docs/api/](./docs/api/) - API仕様書（準備中）

---

## 🎯 ベストプラクティス

1. **高品質な参考記事を用意**: AIの出力品質は参考記事の質に依存します
2. **明確な指示を出す**: 音声指示は具体的かつ明確に
3. **トーンガイドを活用**: 一貫したスタイルを維持
4. **定期的なレビュー**: 生成記事の品質を継続的に評価
5. **バージョン管理**: Gitで記事の変更履歴を追跡

---

## 🤝 コントリビューション

このプロジェクトへの貢献を歓迎します！

1. このリポジトリをフォーク
2. 機能ブランチを作成 (`git checkout -b feature/amazing-feature`)
3. 変更をコミット (`git commit -m 'Add amazing feature'`)
4. ブランチにプッシュ (`git push origin feature/amazing-feature`)
5. プルリクエストを作成

---

## 📄 ライセンス

このプロジェクトは [MIT License](LICENSE) の下でライセンスされています。

---

## 📬 お問い合わせ

質問やフィードバックがある場合は、[Issues](https://github.com/ymc25/Vive-Writing/issues) でお知らせください。

---

## 🙏 謝辞

- [Anthropic Claude](https://www.anthropic.com/) - 高品質なAI記事生成
- [OpenAI Whisper](https://openai.com/research/whisper) - 音声認識技術

---

**Vive-Writing** - あなたの声が、言葉になる。

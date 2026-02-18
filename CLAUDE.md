# Qiita記事管理手順

## 記事の公開・更新

GitHub Actionsが設定済みのため、**git push するだけで自動公開**される。

```bash
git add .
git commit -m "記事を更新"
git push
```

mainブランチへのpushで `.github/workflows/publish.yml` が実行され、Qiita CLIが記事を公開する。

## 記事の取得（Qiitaからローカルへ同期）

```bash
npx qiita pull        # 未変更ファイルのみ同期
npx qiita pull --force  # 強制上書き
```

## 新規記事の作成

```bash
npx qiita new ファイル名
```

`public/` ディレクトリにマークダウンファイルが作成される。

## ローカルプレビュー

```bash
npx qiita preview
```

http://localhost:8888 でプレビュー確認できる。

## 手動公開（GitHub Actions使わない場合）

```bash
npx qiita publish ファイル名
npx qiita publish --all  # 全記事
```

## 注意事項

- 記事ファイルは `public/` ディレクトリに配置
- ファイル名がそのまま記事IDになる
- YAML frontmatterでタイトル、タグ、公開設定を管理

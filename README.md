# RVSS スクール LP

RVSS（Real Value Students）の新規参加者募集 LP。1ファイル完結の `index.html` + 画像素材で動く。

**プレビュー（制作者の作業確認用）**：https://rvsslp.shion1-1-t.workers.dev/

> ※ 上記URLは制作者（田端）の Cloudflare Workers 作業環境。本番運用は別途お任せします。

---

## ファイル構成

```
rvss-lp/
├── README.md          ← このファイル
├── index.html         ← LP本体（編集対象）
├── images/            ← 画像素材一式
├── _qr.png            ← QRコード
└── _assets/           ← 参考資料（公式インフォグラフィック等）
```

---

## ローカルでの確認方法

ブラウザは `file://` 直接開きを CORS で弾く。簡易サーバ立てて見てください。

```bash
cd rvss-lp
python3 -m http.server 8000
# ブラウザで http://localhost:8000/index.html
```

---

## 本番デプロイ

このリポは LP の **HTML 素材** を渡すだけです。本番デプロイ先（独自ドメイン）には、運用担当が好きな方法で `index.html` + `images/` + `_qr.png` を配置してください。

選択肢の例：

- **Netlify / Vercel / Cloudflare Pages**：このフォルダを丸ごとドラッグ＆ドロップ
- **任意の Web サーバー**：FTP/SCP/rsync で配置
- **Cloudflare Workers + Static Assets**：制作者の環境と同じ方式（`wrangler.toml` の `[assets] directory = "./"` で `wrangler deploy`）

---

## 直近の改訂内容（2026-06-19）

公式訴求ポイントへの整合差分を実装。主な変更：

1. **ビジョン文言統一**：「挑戦者に。」→「挑戦者の国に。」（title・Heroマーキー・final CTA）
2. **母体明記**：02 PYRAMID セクションに「母体は、経営者ネットワークを持つリアルバリュー。」追記
3. **在籍エリア追記**：「関東・関西・中部・東北」を FAQ Q.04・footer に明記
4. **見出しコピー改訂**：01 What We Do・04 Projects のキャッチを変更
5. **求める人物像セクション再構成**：4タイプ → 公式5タイプ＋「やる気と素直さ」末尾
6. **タイプ別ベネフィット3分類追加**：AI・キャリア・漠然と不安の3カラム
7. **出口ベネフィット新ブロック**：FAQ 後・FINAL CTA 前に「卒業するころには、自分で稼げる人に。」セクション新設

詳細：要件定義は Notion 参照（リンクは制作者から個別に共有）。

---

## 編集時の注意

- LPは1HTMLにCSS/JSもインライン。`<style>` 内のCSSは4000行近くあり、reveal/transition系のクラスが多用されている
- `<br>` で改行制御している箇所多数。文言を変える時は **PC・スマホ両方の折り返しを必ず確認** すること
- `.accent` クラスは青系アクセント色、`<span class="accent">〇〇</span>` の囲みで強調
- 同じ文言が複数箇所に出ている可能性あり（マーキー2本 / title / 見出しなど）。変更時は **grep で全件抽出** してから一括修正

---

## 連絡先

制作・編集に関する問い合わせは LINE / GitHub Issues 経由でお願いします。

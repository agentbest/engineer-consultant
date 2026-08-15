# engineer-consultant — エンジニア→コンサル転職LP（求職者向け）

- 公開URL: https://eng.agent-best.net/ （GitHub Pages・HTTPS強制）
- 構成: `index.html` 1ファイル完結。CSS/JSはインライン、**外部CDNは読み込まない**。`CNAME` あり。

⚠ **名前が紛らわしい**: これは「**エンジニア→コンサル**」。「未経験→エンジニア」は別物で `engineer.agent-best.net` / `agentbest/engineer-lp`。

## ターゲットとトーン（変えるときは理由を確認する）

20代〜30代前半・**コンサル未経験のエンジニア**（SIer/開発）。

- **トーンは軽め・励まし基調**。pm-lp の「重い・シリアス」に対する姉妹版としての意思決定。丸ゴシック見出し＋明るいエメラルドグリーン（pm-lpはネイビー＋明朝）。
- ヒーロー「エンジニアの経験は、コンサルで武器になる。」
- 署名セクション **「スキル変換表」** ＝エンジニア経験をコンサルの強みに"通訳"する（要件定義→課題を構想に落とす力 等）。「未経験でも大丈夫」を体感させるパート。
- **危機感セクション（"タイミング"）**: 「AIに仕事を奪われる」的な脅しは使わない。核は**「未経験でコンサルに入る間口は若い"いま"が一番広い」**（年齢×ポテンシャル採用）。AIは"価値のシフト（書く→何を作るか）"として軽く1回だけ言及。警告色は赤ではなく**琥珀**。
- 対応領域: PMO／DX・ITコンサル／業務改革（BPR）。
- 事例は**社名・ロゴを出さない匿名アーキタイプ**。想定クライアントの実社名リストは本人メモとして別管理しており、**このリポジトリには書かない**（Publicのため）。許可が取れれば実社名カードへの差し替えは可能。

## 掲載データ

国内コンサル市場 約2.3兆円・前年比+17%（2024年度、業界調査2025年版・出典明記）。

⚠ consultant-lp が使っている IDC Japan の数字（1兆4,554億円等）とは**集計範囲が違う別ソース**なので混ぜない。

## 表記の連動

フッターの pm-lp へのリンク表記は「**PM特化の転職**」で固定（PMO・PjM/PdMは併記しない）。

---

## 求職者向けLP 共通ルール

- **CTA**（「話を聞いてみる」「無料で相談する」「面談予約」）のリンクは `https://calendly.com/r_matsuoka` 固定。`target="_blank" rel="noopener"` で開く。
- **GA4 測定ID** `G-1XXMP8Y1B4`（全サブドメイン共通プロパティ）。
- **ダークモード対応**（`prefers-color-scheme` ＋ `[data-theme]` の両対応）を壊さない。
- 事例・行き先は**社名・ロゴを出さない匿名アーキタイプ**で書く。
- 掲載する数字は**必ず一次ソース付き**。出典が取れない数字は載せず、空欄のままにする。架空の利用者の声や根拠のない自社指標（「年収アップ率○%」「独占求人多数」等）は入れない。
- 棒グラフの `.track` / `.fill` を `<span>` で書くと**描画されない**（inline要素なので width/height が効かない）。`display:block` が必要。pm-lp由来の既知バグで、他LPにも伝播している可能性が高い。
- ローカルプレビューは `file://` だと確認できないので、簡易HTTPサーバー（node）を立てて `http://localhost:<port>/` で見る。

## 相互リンク（求職者向け8本）

| サブドメイン | 内容 | リポジトリ |
|---|---|---|
| pm | PM特化 転職 | agentbest/pm-lp |
| eng | エンジニア→コンサル転職 | agentbest/engineer-consultant |
| ma | 未経験からM&A | agentbest/ma-lp |
| consul | 未経験からコンサル | agentbest/consultant-lp |
| engineer | 未経験からエンジニア | agentbest/engineer-lp |
| embedded | IoT・組込みエンジニア | agentbest/embedded-lp |
| consultingcareerchange50 | ファーム出身者の次のキャリア（50代） | agentbest/consultingcareerchange50 |
| student | 学生キャリア支援 | agentbest/student-career |

フッターに `.ft-links` を再利用した2つ目のnav（`ft-sites-links`）で自分以外の7本を並べる。**新しいLPを足したら既存全部＋コーポレート `agentbest/agentbest-lp` の `src/components/Header.astro` の `specialSites['求職者の方へ']` も更新する。片方向にしない。**

⚠ 一括置換の罠: アンカーに `ft-sites-links` の文字列だけを使うと `<style>` 内のCSS定義にマッチして**ヘッダーnavに誤挿入される**（student-careerで実際にやらかした）。`<nav class="ft-links ft-sites-links">` のようにタグごと指定すること。

採用企業向け（B2B）4本（scout / green / infra / scoutdaikou_offerbox）は読み手が違うので、この相互リンクには**意図的に含めない**。

## push のルール

- ローカルで動作確認（ブラウザ表示・構文チェック）を済ませた変更は、**確認を取らずに commit & push してよい**。コミットメッセージは日本語。**push後は必ず何を変えたか報告する**（無言でpushしない）。
- **以下に触れるときは必ず止まって事前確認する**:
  1. ドメイン・DNS・CNAME（DNSは**Squarespace Domains**管理・松岡さんの手作業）
  2. 個人情報・フォーム・認証
  3. 費用が発生する変更
  4. 既存ページ・データの削除
  5. 複数リポジトリへの一括変更（相互リンク更新など）
- Publicリポジトリ。push前にトークン・APIキーの混入をgrepで確認する。
- `main` への push = **即本番公開**。

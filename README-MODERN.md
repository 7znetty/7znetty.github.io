# しのめぐ's Profile Site - Modern

モダンデザインのプロフィールサイト✨

## 特徴
- **グラスモーフィズム** - ガラスのような透明感のあるカード
- **背景の立ち絵画像（左側）** - スクロールで上半身→下半身が見える縦長レイアウト
- **固定表示のプロフィールカード** - スクロールしても画面中央に表示され続ける
- **シンプルな丸型アバター** - 白い境界線のクリーンなデザイン
- **浮遊するパーティクル** - キラキラと浮かぶ光の粒
- **動く背景図形** - ゆっくり動く半透明の円
- **はっきりとしたSNSカラー** - 原色に近い鮮やかな色
- **完全レスポンシブ対応** - PC、タブレット、スマホで最適表示

## GitHub Pagesでの公開手順

### 1. GitHubリポジトリの作成
1. GitHubにログイン
2. 新しいリポジトリを作成
3. リポジトリ名を `あなたのユーザー名.github.io` にする
4. 「Public」を選択

### 2. ファイルのアップロード
1. `index-modern.html` を `index.html` にリネーム
2. `avatar.png` はそのまま
3. `character-stand.png` を自分の立ち絵画像に差し替え（推奨サイズ: 1920x4600）
4. 3つのファイルをGitHubリポジトリにアップロード
   - 「Add file」→「Upload files」からドラッグ&ドロップ
5. 「Commit changes」をクリック

### 3. 公開確認
数分後、自動的に `https://あなたのユーザー名.github.io` で公開されます！

## カスタマイズ方法

### 背景の立ち絵画像を変更
現在は `character-stand.png` がモック画像として設定されています。

**自分の立ち絵画像に差し替える方法:**
1. 縦長の立ち絵画像を用意（推奨サイズ: 1920x4600 または類似の縦長サイズ）
2. ファイル名を `character-stand.png` にする
   - または別の名前にして、HTML 339行目を編集:
   ```html
   <img src="your-character.png" alt="" class="background-character">
   ```

**画像の表示方法:**
- 立ち絵は画面左側に配置されます
- 最初は画像の上半分（上半身）が表示されます
- ページをスクロールすると下半分（下半身）が見えます
- **プロフィールカードは画面中央に固定され、スクロールしても追随します**
- **©2026 しのめぐ も一緒に固定表示されます**
- スマホでは透明度が低くなり、邪魔にならないように調整されます

**SNSアイコン:**
- X（旧Twitter）のアイコンは最新の「X」マークを使用しています（Font Awesome 6.5.1）
- すべてのアイコンに`fa-brands`クラスを使用
- Xのボタンは黒・グレー系のカラー（Xのブランドカラー）
- 個人アカウント（@7znty）とチームアカウント（@ForTune_FN）の両方を掲載

**フォント:**
- Google FontsのYomogi（よもぎ）フォントを使用
- かわいい手書き風のデザイン
- 全体的に温かみのある雰囲気

**スペーシング:**
- TEAMの文字を下に移動して、チームアカウントボタンとの間隔を狭く調整
- プロフィールカードは画面中央に固定
- **©2026はページ下部に独立して固定表示**（画面下から20px）
- カードとフッターは独立しているため、スクロールしてもそれぞれ固定位置に表示

**画像の調整:**
CSSの44〜75行目あたりで調整できます:
```css
.background-character {
    left: -50px;      /* 位置調整（左側） */
    height: 180vh;    /* 高さ（画面の1.8倍） */
    opacity: 0.8;     /* 透明度（PC） */
}
```

**レスポンシブ対応:**
- PC（1200px以上）: opacity 0.8、高さ 180vh
- タブレット（768-1200px）: opacity 0.6、高さ 150vh
- スマホ（480-768px）: opacity 0.4、高さ 120vh
- 小さいスマホ（480px以下）: opacity 0.3、高さ 100vh

**配置位置の変更:**
- 左側配置（現在）: `left: -50px;`
- 右側配置: `right: -50px;` に変更して `left` を削除
- もっと中に: `left: 0;`

**高さの調整:**
- `height: 180vh;` の値を変更
- `150vh` = 画面の1.5倍
- `200vh` = 画面の2倍（より長く表示）

**透明度の調整:**
- `opacity: 0.8;` の値を変更
- `0.5` = 半透明
- `0.8` = 現在（はっきり）
- `1.0` = 完全に不透明

### 背景アイコンを変更（使わない場合は削除してOK）

### アバター画像を変更
現在は `avatar.png` が設定されています。
別の画像に変更する場合:

1. 新しい画像をリポジトリにアップロード（例: `my-icon.png`）
2. HTML 367行目あたりを編集:
```html
<img src="my-icon.png" alt="しのめぐ">
```

推奨画像サイズ: 正方形（500x500px以上）

### リンクを追加
既存のリンクを参考に、新しいリンクボタンを追加できます:
```html
<a href="https://example.com" target="_blank" class="link-button">
    <i class="fas fa-link"></i>
    <span>リンク名</span>
</a>
```

**区切り線を追加する場合:**
```html
<div class="divider">
    <div class="divider-line"></div>
    <div class="divider-text">セクション名</div>
</div>
```

### プロフィール文を編集
427行目:
```html
<p class="profile-bio">メインはFortnite。<br>たまにマイクラ/ぷよテトも。<br>まじめです。たぶん。</p>
```

### SNSリンクを編集
HTMLの376〜389行目あたり:
- **X（旧Twitter）**: 376行目 `href` と `<span>` の内容を変更
- **YouTube**: 381行目 `href` を変更
- **Twitch**: 386行目 `href` を変更

アイコンの種類:
- X: `<i class="fab fa-x-twitter"></i>`（現在使用中）
- YouTube: `<i class="fab fa-youtube"></i>`
- Twitch: `<i class="fab fa-twitch"></i>`
- Instagram: `<i class="fab fa-instagram"></i>`
- TikTok: `<i class="fab fa-tiktok"></i>`

リンクを追加する場合は、既存のリンクをコピーして編集してください。

### リンクの色をさらに調整
CSSの251〜269行目あたり:
```css
.twitter-link {
    background: rgba(29, 161, 242, 0.6);  /* 0.6 = 60% の濃さ */
}
```
透明度の値を変更（0.0〜1.0）

### 背景グラデーション色を変更
19行目:
```css
background: linear-gradient(135deg, #ffadd1 0%, #ff5599 50%, #ff006a 100%);
```

**現在の配色（#ff006aベース）:**
- 左上: #ffadd1（薄いピンク）
- 中央: #ff5599（中間ピンク）
- 右下: #ff006a（濃いピンク - ベースカラー）

### フォントを変更
別のGoogle Fontsに変更したい場合:

1. [Google Fonts](https://fonts.google.com/)で好きなフォントを選ぶ
2. HTMLの7行目のリンクを変更:
```html
<link href="https://fonts.googleapis.com/css2?family=フォント名&display=swap" rel="stylesheet">
```
3. CSSの18行目のfont-familyを変更:
```css
font-family: 'フォント名', cursive;
```

おすすめの日本語フォント:
- Yomogi（現在）- 手書き風
- Klee One - 教科書体風
- Zen Maru Gothic - 丸ゴシック
- M PLUS Rounded 1c - 丸ゴシック

### パーティクルの数を変更
HTML 341〜348行目の `.particle` の数を増減

### アニメーション速度を調整
- パーティクル: 318行目 `animation: particleFloat 15s` の数値
- 背景図形: 35, 42行目の `20s`, `15s` の数値

## 技術スタック
- HTML5
- CSS3
  - Glassmorphism（グラスモーフィズム）
  - backdrop-filter（ブラー効果）
  - CSS Animations
- Font Awesome 6.5.1（アイコン）
- Google Fonts（Yomogi - 手書き風フォント）

---

作成: 2026年2月  
デザイン: Modern Glassmorphism

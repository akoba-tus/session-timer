# Session Timer

A single-file countdown timer for chairing and timekeeping at conference sessions.
Open it in a browser, prop the tablet up facing the speaker, and run the session.

**No installation, no account, no network after the first load.**
The whole thing is one HTML file with no external requests.

[**→ Open the timer**](https://YOUR-NAME.github.io/session-timer/)

---

## What it does

- Counts down the talk, then the discussion, as two linked phases
- Turns **amber** a few minutes before the end, **red** when time is up
- Rings a bell: once as a warning, twice at the end of the talk, three times at the end of the session
- Keeps counting **up in red** past zero, so the chair can see how far over the speaker has run
- Switches between Japanese and English from the settings panel

The colour fills the whole screen, so a speaker notices the change out of the corner of an eye without stopping to read the digits.

## Default timing

| | |
|---|---|
| Talk | 12 min |
| Warning | 2 min before the end (amber + one bell) |
| End of talk | two bells, moves straight into the discussion |
| Discussion | 3 min |
| End of session | three bells, then counts up in red |

All of it is adjustable in the settings panel, and the values are remembered on that device. There are one-tap presets for 12+3, 15+5, 20+5 and 8+2.

## Using it

1. Open the link above
2. On iPad or iPhone: Share → **Add to Home Screen**, then launch it from the icon for a full-screen view
3. Tap **Test bell** in the settings once before the session starts

### Controls

| Button | |
|---|---|
| Start / Pause / Resume | Space bar also works |
| Q&A | Move to the discussion early, or after overtime | 
| Reset | Two taps, to avoid killing a running timer by accident |
| Settings | Times, bell, language |

### Before the session

- Turn **auto-lock off** (iOS: Settings → Display & Brightness → Auto-Lock → Never)
- Turn the **silent switch off**, or no bell will sound
- On iOS, sound only works after you have tapped the page once — the test bell takes care of this
- **Guided Access** (iOS: Settings → Accessibility) locks the device to this one screen, which is worth doing if the tablet sits where people can reach it

### Offline

Once the page has loaded, it runs entirely in the browser and needs no further network. If the venue's Wi-Fi is unreliable, open it before the session and leave it open.

## Editing it

Everything lives in `index.html` — layout, bell sounds, wording. The bell is synthesised with the Web Audio API, so there are no sound files to ship. To change the strike pattern, look for the `bell()` function; for the wording of either language, the `T` object near the top of the script.

Pull requests and forks are welcome.

## Licence

MIT

---

<a id="ja"></a>

# セッションタイマー（日本語）

学会・研究会の座長／タイムキーパー用のカウントダウンタイマーです。HTML 1ファイルだけでできています。
タブレットを発表者に向けて置き、そのまま使えます。

**インストール不要、アカウント不要、最初に読み込めばオフラインでも動作。**

[**→ タイマーを開く**](https://YOUR-NAME.github.io/session-timer/)

## 特徴

- 発表と質疑を続けて計測します
- 終了前に画面全体が**琥珀色**、時間切れで**赤**に変わります
- ベルは予鈴1回、発表終了2回、質疑終了3回（学会の慣例に合わせています）
- 時間切れ後は止まらず、超過時間を赤字でカウントアップします
- 設定から日本語・英語を切り替えられます

画面全体の色が変わるので、発表者は数字を読まなくても視界の端で気づきます。

## 既定の時間

| | |
|---|---|
| 発表 | 12分 |
| 予鈴 | 残り2分（琥珀色＋ベル1回） |
| 発表終了 | ベル2回、そのまま質疑へ自動移行 |
| 質疑 | 3分 |
| 質疑終了 | ベル3回、以降は赤字でカウントアップ |

いずれも設定画面から変更でき、その端末に保存されます。12＋3、15＋5、20＋5、8＋2のプリセットもあります。

## 使い方

1. 上のリンクを開く
2. iPad・iPhoneでは共有ボタン →「**ホーム画面に追加**」。アイコンから全画面で起動します
3. 本番前に設定画面の「**ベルを試す**」を一度押してください

### 操作

| ボタン | |
|---|---|
| 開始／一時停止／再開 | 外付けキーボードのスペースキーでも操作できます |
| 質疑へ | 早く終わったとき、超過後に質疑へ進むとき |
| リセット | 誤操作防止のため2回タップ |
| 設定 | 時間、ベル、言語 |

### 本番前の確認

- **自動ロックをオフ**に（設定 → 画面表示と明るさ → 自動ロック → なし）
- **マナーモードを解除**（オンだとベルが鳴りません）
- iOSでは一度画面をタップするまで音が鳴りません。「ベルを試す」がその役目を兼ねています
- 誰でも触れる場所に置くなら、**アクセスガイド**（設定 → アクセシビリティ）で画面を固定しておくと安心です

### オフラインについて

一度読み込めば通信は不要です。会場のWi-Fiが不安な場合は、セッション開始前に開いておき、そのまま閉じないでください。

## 改造

すべて `index.html` の中にあります。ベルはWeb Audio APIで合成しているので音声ファイルはありません。鳴らし方は `bell()` 関数、文言はスクリプト冒頭の `T` を見てください。

## ライセンス

MIT

# ABC社 トークスクリプトガイドアプリ

このリポジトリでは、Windsurfを使って開発した「電話営業用トークスクリプトガイドアプリ」のコードとプロンプトを公開しています。

---

## 🔰 このアプリについて

このアプリは、営業担当者が電話対応時に使用する「会話ナビゲーション支援アプリ」です。以下のような特徴があります：

- 会話の流れに沿ったステップガイド
- 顧客の回答に応じた分岐
- よくある質問（FAQ）の表示
- 会話履歴の保存とPDF出力機能

---

## 📄 Windsurf用プロンプト（構造例）

以下は、Windsurfに読み込ませるためのプロンプト構造の例です：

### ステップ1：挨拶と確認
- **メッセージ**：「[会社名]カスタマーセンターの○○でございます。〇〇様でお間違いないでしょうか？」
- **選択肢**：
  - はい → ステップ2へ
  - いいえ → ステップ98（終了）

---

### ステップ2：ご用件確認
- **メッセージ**：「本日は〇〇についてご案内のためにお電話いたしました。今お時間よろしいでしょうか？」
- **選択肢**：
  - はい → ステップ3へ
  - いいえ → ステップ98（再架電）

---

### ステップ3：現状確認
- **メッセージ**：「現在、どの携帯会社をご利用でしょうか？」
- **選択肢**：
  - docomo、au、SoftBank、楽天モバイル、その他MVNO、不明
- **すべての選択肢で** → ステップ4へ進行

---

## 💡 備考

- 分岐は `*` を使ってすべての選択肢に対応可能です（例：`'*': 4`）
- `showFAQ: true` を付けると、そのステップでFAQカードが表示されます

---

## 🔗 その他の参考ファイル

- [prompt.html（ブラウザで開けるHTML版）](https://naoko705310.github.io/abc-company/prompt.html)


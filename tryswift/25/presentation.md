slidenumber: true

# Spice up your notifications

## noppe (Tomoya Hirano)

^ みなさんこんにちは、では早速初めていきましょう。

---

# 176 Emojis starts from Japan

^ 絵文字は1999年に日本で生まれました。
^ 最初はたったの176種類でした。

---

# 2025. Unocode emojis over 3000+.

^ 今ではUnicodeの絵文字だけで、3000を超えます。

---

# Genmoji

そして、今年、Genmojiが登場しました。
Apple Intelligenceが生成する絵文字です。

---

# Custom Emojis

^ さらに、私たちはユニークな絵文字も使います。
^ SlackやMastodon, Discordでは、ユーザーが絵文字を登録することができます。
^ ミームの絵文字は、私も大好きです。

---

# "Hello, try!Swift 😻"

^ OK、ではメッセージを送りましょう。
^ 「猫ミームのメッセージ😻」
^ この黄色いトカゲは、私の妻が描いたキャラクターです。

---

# "Hello, try!Swift (OK)"

^ （一息おいて…）
^ 「猫ミームのメッセージ(OK)」
^ あぁ、なんということでしょう。
^ もう通知には、可愛らしいトカゲはいません。代わりに(OK)と書かれています。

---

# Notifications are silence?

^ 通知にカスタム絵文字を表示することは出来ないのでしょうか？
^ 今年のWWDCを思い出してみましょう。

---

# WWDC

^ これです！Genmojiは通知に表示する事が出来ます。

---

# Can custom emojis spoof Genmoji?

^ カスタム絵文字を、Genmojiに装うことは出来るでしょうか？
^ 試してみましょう

---

# Extract Genmoji

![Screenshot of UITextView]()

^ まずは、Genmojiを解剖してみましょう。
^ UITextViewにGenmojiをタイプします。

---

![Screenshot of attributedString runs]()

^ attributesを参照します。
^ Genmojiの正体は、NSAdaptiveImageGlyphです。

---

![Screenshot of NSAdaptiveIamgeGlyph documents]()

^ NSAdapativeImageGlyphは、imageContentというDataでinitする事ができます。
^ つまり、このimageContentを作ればカスタム絵文字のNSAdapativeImageGlyphが作れそうです。

---

![Screenshot of look Data header]()

^ NSAdapativeImageGlyphのimageContentを書き出します。
^ ヘッダーを見ると、heicであると分かりました。

---

![Screenshot of metadata]()

^ このデータのメタデータを見てみましょう。
^ いくつかキーがあります。時間がないので答えを言います。
^ tiff:DocumentName。これが重要です。

---

![Screenshot of create own Data]()

^ 用意したイメージデータとtiff:DocumentNameを組み合わせてheicファイルを作ります。
^ このデータで、NSAdaptiveImageGlythを作ってみましょう。

---

![gif of work with custom emoji as Genmoji]()

^ ビンゴ！動きました。
^ 通知にも表示されます。
^ 私の妻も喜んでいます。

---

# See more

https://github.com/noppefoxwolf/Zenmoji

^ 今回のコードはオープンソースとして公開しています。
^ 私の名前はTomoyaです。Mastodonアプリを開発しています。
^ この後もtry!Swiftをお楽しみください！

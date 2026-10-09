# Stock Charts — companion source for the book

Design documents and code for the stock app built in ***Toward a Million Lines VI — A Stock App for Finding Stocks That Beat Index Funds*** (Japanese title 『LLM で 100 万行のソフトウェア開発 VI — インデックスファンドに勝つ株を探すアプリ』; Volume 6 of the series).

The app has nine tabs: Price, PER, Hyperscalers, PER scatter, Operating-income growth, Fundamentals, News, Rotation, and Backtest. The screens are Kotlin (Compose, shared by Windows and Android); every button runs a Python tool that fetches data from the network, computes the indicators and stores them. The Rotation tab outputs recommendations only; it does not place orders.

## Download

**Ready-to-run apps are on the [Releases](../../releases) page**, not in this repository. The release (v1.0.214) has five separate ZIPs:

| File | Contents |
|:---|:---|
| `android_stocks_exe.zip` | Windows app, Japanese screens |
| `android_stocks_apk.zip` | Android APK, Japanese screens (with the book's example account and an empty `sec_contact.txt` beside the APK) |
| `android_stocks_exe_en.zip` | Windows app, English screens (display only; same calculations) |
| `android_stocks_apk_en.zip` | Android APK, English screens (display only; same calculations) |
| `android_stocks.zip` | Design documents (`docs/design`, with English translations of levels L1–L3 in `docs/design_en`) and source code (`src/` for the Japanese-display app, `src_en/` for the English-display app), the KB search module, and the table definitions of the registry database (empty) |

The apps are **not code-signed**, so Windows and Android may warn you (Windows: More info → Run anyway; Android: allow installs from unknown sources).

Not included: the data of the app (the app fetches it with its buttons), test files, the database records, personal files, build output, the Android SDK and `local.properties`.

## Use

- **Windows:** install Python 3.11 (standard library only), then start `launch_with_sample.bat` (it starts with the example account of the book's chapter 30).
- **Android:** install the APK. To load the example account on the device alone, copy `portfolio_master.json` and your own `sec_contact.txt` from beside the APK to the device, then tap "Import files" in the app's help screen and choose them.
- **SEC contact:** write your own contact (an e-mail address or a URL, one line) in `sec_contact.txt`. The app holds no contact of its own; without it the SEC steps stop.
- **Rotation tab:** it asks for a password; the public default is `stocks`.

## License

- **The author holds the copyright.**
- **The code is under the GNU General Public License v3.0 (GPL-3.0).** The full text is [`LICENSE`](LICENSE). **If you modify it and distribute it, you must publish the source under the same GPL-3.0.**
- **The design documents and the text are under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0).** This covers `docs/`, the READMEs and the other written text of this repository, and the text of the matching book. See [`LICENSE-DOCS.md`](LICENSE-DOCS.md). **If you distribute what you changed, you must publish it under the same terms.**
- **If you use them, say so.** State where it came from (the title of the book and the name of this repository) and keep the copyright notice. If you changed it, say that you changed it.
- **In this project the design documents are the source of the code** (the tests and the code are generated from them). When you publish something made from this code, **publish the design documents together with the code.**
- Third-party components (for example the Java runtime and libraries inside the release ZIPs) remain under their own original licenses.
- Provided "as is", without warranty — as the GPL-3.0 text says.

## 著作権とライセンス

- **著作権は、著者にあります。**
- **コードは、GNU General Public License v3.0（GPL-3.0）です。**全文は [`LICENSE`](LICENSE) です。**改変して配布するときは、同じ GPL-3.0 で、ソースを公開する義務があります。**
- **設計書と文章は、Creative Commons 表示-継承 4.0 国際（CC BY-SA 4.0）です。**このリポジトリの `docs/`・README ほかの文章と、対応する本の文章が当たります。内容は [`LICENSE-DOCS.md`](LICENSE-DOCS.md) です。**直したものを配るときは、同じ条件で公開する義務があります。**
- **使ったときは、使ったことを書いてください。**どこから使ったか（本の題名と、このリポジトリの名前）と、著作権の表示を、使った先に書いてください。直したときは、直したことも書いてください。
- **このプロジェクトでは、設計書がコードの源です**（設計書から試験とコードを起こします）。コードを使って作ったものを公開するときは、**設計書も、コードと一緒に公開してください。**
- リリースの ZIP に入っている第三者の部品（Java の実行環境やライブラリなど）は、それぞれの元のライセンスのままです。
- 現状のまま（as is）提供します。保証はありません（GPL-3.0 の全文のとおりです）。

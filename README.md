# はじめに
JavaScriptとHTMLで簡単なログインフォームを作成する方法です.
あくまでで簡易的なもので, セキュリティ的にもガバガバなので実際に使用するのはオススメしません.

# デモページ
完成品は[こちら](https://sekaino-usay.github.io/Login_form_JS_HTML/)から確認できます. （ID：`user`, Password：`password`でログインできます. ）
![](https://storage.googleapis.com/zenn-user-upload/593d88be0267-20220310.png)


# ソースコード

```html:index.html
<!DOCTYPE html>
<html lang="ja">

<head>
    <meta charset="UTF-8">
    <title>ログイン</title>
    <link rel="stylesheet" href="style.css">
</head>

<header>
    <center>
        <h1>JavaScriptとHTMLで簡単なログインフォームを作る</h1>
    </center>
</header>
<style>
    header {
        position: fixed;
        color: white;
        width: 100%;
        height: 70px;
        background-color: #8dc21f;
    }
</style>

<br>
<br>
<br>

<body>
    <div>
        <!--フォーム-->
        <form name="login_form">
            <center>
                <h1 class="contact-title">ログイン</h1>
                <p>ID, Passwordご入力の上, 「認証」ボタンをクリックしてください.</p>
            </center>
            <div>

                <center>
                    <div>
                        <input type="id" name="id" placeholder="ID">
                    </div>
                    <br>
                    <div>
                        <input type="password" name="pass" placeholder="Password" onchange="nextPage()">
                    </div>
                </center>

            </div>
            <button type="button" onClick="nextPage();">認証</button>
        </form>

        <!--ログイン処理-->
        <script language="JavaScript" type="text/javascript">
            function nextPage() {
                id = document.login_form.id.value
                pwd = document.login_form.pass.value;
                location.href = id + pwd + ".html";
            }
        </script>

    </div>
</body>

</html>
```
こちらのソースコードを`index.html`という名前で保存します.
サンプルデモのようにするには, 他にCSSが必要です. ここではソースコードを書きませんが, ページ最後に必要なファイルをすべて含んだZIPファイルのダウンロードURLを貼っておきます.

# 解説
`index.html`のIDの枠に入力された値（文字列）と, Passwordの枠に入力された値（文字列）を合体させてURLを作成（`id + password + ".html"`に変換）し, 飛ばしています.
（つまり, ID：user, Password：passwordですと, 同じ階層にある, userpassword.htmlに飛びます. ）
また, ソースコードを見ても絶対にID及びPasswordはわかりません.

```html
<script language="JavaScript" type="text/javascript">
            function nextPage() {
                id = document.login_form.id.value //ID枠に入力された値（文字列）を定義
                pwd = document.login_form.pass.value; //Password枠に入力された値（文字列）を定義
                location.href = id + pwd + ".html"; //リンク先URLを作成
            }
 </script>
```

# ファイル・フォルダの配置
ファイルはすべて, 同一階層に配置してください.

# カスタマイズ
`認証ボタン`の「認証」という文字と, `userpassword.html`のファイル名は変更可能です.
（`userpassword.html`のファイル名を変えることは, ID，Passwordが変更されることと同意です. ）

# 完全版ダウンロード
完全版（ZIP）のダウンロードは[こちら](https://github.com/sekaino-usay/Login_form_JS_HTML/archive/refs/heads/main.zip)からできます. 展開してお使いください.
（ソースコード等のプログラムは, 特に僕に断りなく使用していただいて大丈夫です！）

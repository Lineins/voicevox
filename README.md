# IT EDITOR
2022/04/09
いたほび(ITahobi)が作る自力合成音声のエディタ部なので「ITeditor」です。

[1]に示すシロワニ氏と、[2]に示すのほしお氏よる編集を参考に各部の調整を行った。

『.env.production』の「VUE_APP_ENGINE_URL」で指定されるポートを、
ITengineで用いる「49540」に設定した。（2行目）

『package.json』の
「name」に渡される文字列を「voicevox」から
「voicevox-modified-by-itahobi」に変更した。（2行目）
「version」を「0.0.0」から「1.0.0」に変更した。（3行目）
参考文献をもとにバージョン指定を行いましたが、バージョンの更新って何が目安になっているのか？
version1ってもうこれリリースするってことじゃない？大丈夫？

『vue.config.js』の
31行目で拡張子を「ivproj」、
32行目で対応ファイル形式を「ITVOICE on VOICEVOX Project file」に、
45行目でアプリの名称を「ITVOICEonVOICEVOX」、
46行目でappIdを「itvoice.on.voicevox」、
47行目でcopyrightを「ITahobi」と設定した。


『public』ディレクトリ内部の「icon.png」を変更した。
私が普段使っている画像？マーク？に差し替えた。

[2]の文献を参考に『public』内の『updateInfos.json』の3行目から370行目までを削除、
3行目の「"version": "0.2.0"」を「"version": "ITVOICE1.0.0+VOICEVOX-0.10.4"」に変更、
5行目を「"仮リリース"」に上書き、6～11、7～14、8～31、9～15行目を削除した。

『public』内の『policy.md』『privacyPolicy.md』については編集をいったん見送ります。
重要なところですからね。
現時点では私「いたほび」以外の存在が「ITVOICE」アプリケーションを
使用することは禁じます。なんで私は良いのか？って？
デバッグしないといけないからだよ・・・

『public』『themes』の『default.json』でいろいろ色を設定した。
メインカラーはいつもの紫（#8232C8）で。（5行目、6行目）


『src』内の『background.ts』の214行目、デフォルトのサンプリング周波数を44100Hzに設定。
225行目でアウトプットについても44100Hzに設定。
688行目でプロジェクトファイル名と拡張子を設定、「ITVOICE on VOICEVOX Project file」「ivproj」とした。
Q：なぜ「itproj」にしなかったんですか？
A：いたほびが作る他アプリのファイル名でいつかうっかりそれを指定して他のアプリに悪影響を出しそうだったので避けました。
700行目も同様に設定した。

『src』内の『main.ts』の35行目、いつもの紫（#8232C8）を指定した。


『src』『components』内の『AcceptRetrieveTelemetryDialog.vue』
14～16行目を一行で「<q-toolbar-title class="text-display">利用規約</q-toolbar-title>」とまとめた。
22行目を「拒否」から「同意する」に変更。
28行目に「””</div>””」を、30行目に「””<div style="display: none">””」を追加。
46～50行目を削除、46行目に「ITVOICEを利用するには、利用規約に同意する必要があります。<br /><br />」を追加。
50行目の「プライバシーポリシー」を「ITVOICE 利用規約」に書き換えた。

『src』『components』内の『AudioDetail.vue』
8、9行目に「style="display: none"」を追記した。
この処理を行った箇所（今回は長さとイントネーション）は表示されなくなるのかな？
実験したいがまだまだビルドとやらには遠そう。

『src』『components』内の『AudioInfo.vue』の168、189、210行目を
「<div class="q-px-md" style="display: none">」に変更した。

『src』『components』内の『HelpDialog.vue』の128～135行目をコメントアウト化した。

『src』『components』内の『LibraryPolicy.vue』の21行目に
「text-color="display-dark"」を追加した。この文章は必要なのか？

『src』『components』内の『MenuBar.vue』の24行目の
「"VOICEVOX" +」を「"ITVOICE on VOICEVOX" +」に変更した。

『src』『components』内の『OssLicense.vue』の25行目に
「text-color="display-dark"」を追加した。

『src』『components』内の『SettingDialog.vue』の
31行目と244、395、439行目に「 style="display: none"」を追加、
326、707行目のサンプリング周波数を「44100」に設定、
それに伴う警告文の変更を711行目に行った。


『src』『store』内の『project.ts』の
15行目でサンプリング周波数を「44100」に、
97行目でファイル形式を「ITVOICE on VOICEVOX Project file」に、
288行目で拡張子を「ivproj」に設定した。

『src』『store』内の『setting.ts』の33行目でサンプリング周波数を44100に設定した。


『src』『views』内の『Home.vue』の
503行目で対応拡張子を「ivproj」に変更し、
510行目で対応ファイルについての説明文を補正した。


『tests』『unit』『store』内の『Vuex.spec.ts』の
50行目でサンプリング周波数を「44100」に設定した。



2022/04/10
『src』『components』内の『SettingDialog.vue』の
244、395行目で
 「<q-card-actions class="q-px-md q-py-none bg-setting-item" style="display: none">」
 としていたところを
「<q-card-actions
    class="q-px-md q-py-none bg-setting-item"
    style="display: none"
    >」
という形に変更した。



2022/04/11
『src』『background.ts』
700行目でvvprojに再対応した。

『src』『components』『HelpDialog.vue』
128行目に「{」を追加した。


Github上でオリジナルのエディタ
「VOICEVOXエディタ 0.10.4( https://github.com/VOICEVOX/voicevox/tree/release-0.10 ) 」をフォークし、
VSCodeで
「git checkout release-0.10」
「git checkout -b ITeditor」
「git push --set-upstream origin ITeditor」
を実行し改めて上記の編集を行ったところ、無事起動までたどり着くことが出来た。



参考文献
[1]シロワニ、Fix for coeiroink-v.1.0.0：https://github.com/shirowanisan/voicevox/commit/7e1d497105322a4c94bc5ec9d7e26396124b644c
　（参照　2022/04/09）

[2]のほしお、編集：https://github.com/ssohsn/voicevox/commit/0b87e986d5e4193dca6aa9abdf96fe1f6a8bddaf
　（参照　2022/04/09）


# VOICEVOX

[VOICEVOX](https://voicevox.hiroshiba.jp/) のエディターです。

（エンジンは [VOICEVOX ENGINE](https://github.com/VOICEVOX/voicevox_engine/) 、
コアは [VOICEVOX CORE](https://github.com/VOICEVOX/voicevox_core/) 、
全体構成は [こちら](./docs/全体構成.md) に詳細があります。）

## 環境構築

[.node-version](.node-version) に記載されているバージョンの Node.js をインストールしてください。
Node.js をインストール後、[このリポジトリ](https://github.com/VOICEVOX/voicevox.git) を
Fork して `git clone` し、次のコマンドを実行してください。

```bash
npm ci
```

## 実行

`.env.production`をコピーして`.env`を作成し、`ENGINE_PATH`に`voicevox_engine`があるパスを指定します。
とりあえず [製品版 VOICEVOX](https://voicevox.hiroshiba.jp/) のディレクトリのパスを指定すれば動きます。

```bash
npm run electron:serve
```

音声合成エンジンのリポジトリはこちらです <https://github.com/VOICEVOX/voicevox_engine>

## 貢献者の方へ

Issue を解決するプルリクエストを作成される際は、別の方と同じ Issue に取り組むことを避けるため、
Issue 側で取り組み始めたことを伝えるか、最初に Draft プルリクエストを作成してください。

## ビルド

```bash
npm run electron:build
```

## テスト

```bash
npm run test:unit
npm run test:e2e
```

## 依存ライブラリのライセンス情報の生成

```bash
# get licenses.json from voicevox_engine as engine_licenses.json

npm run license:generate -- -o voicevox_licenses.json
npm run license:merge -- -o public/licenses.json -i engine_licenses.json -i voicevox_licenses.json
```

## コードフォーマット

コードのフォーマットを整えます。プルリクエストを送る前に実行してください。

```bash
npm run fmt
```

## タイポチェック

[typos](https://github.com/crate-ci/typos) を使ってタイポのチェックを行っています。
[typos をインストール](https://github.com/crate-ci/typos#install) した後

```bash
typos
```

でタイポチェックを行えます。
もし誤判定やチェックから除外すべきファイルがあれば
[設定ファイルの説明](https://github.com/crate-ci/typos#false-positives) に従って`_typos.toml`を編集してください。

## Markdownlint

Markdown の文法チェックを行います。

```bash
npm run markdownlint
```

## Shellcheck

ShellScript の文法チェックを行います。
インストール方法は [こちら](https://github.com/koalaman/shellcheck#installing) を参照してください。

```bash
shellcheck ./build/*.sh
```

## OpenAPI generator

音声合成エンジンが起動している状態で以下のコマンドを実行してください。

```bash
curl http://127.0.0.1:50021/openapi.json >openapi.json

$(npm bin)/openapi-generator-cli generate \
    -i openapi.json \
    -g typescript-fetch \
    -o src/openapi/ \
    --additional-properties=modelPropertyNaming=camelCase,supportsES6=true,withInterfaces=true,typescriptThreePlus=true

npm run fmt
```

## ライセンス

LGPL v3 と、ソースコードの公開が不要な別ライセンスのデュアルライセンスです。
別ライセンスを取得したい場合は、ヒホ（twitter: [@hiho_karuta](https://twitter.com/hiho_karuta)）に求めてください。

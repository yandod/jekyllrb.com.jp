---
layout: docs
title: 設定項目
prev_section: structure
next_section: frontmatter
permalink: /docs/configuration/
---

Jekyll はあなたが夢見る任意の方法でサイトを組むことができます、
それはパワフルで柔軟なコンフィグオプションのおかげで可能になります。
これらのオプションは、サイトのルートディレクトリに置かれる `_config.yml` ファイルか、
ターミナルから実行した `jekyll` のフラグとしてのどちらでも指定することができます。
<!--
Jekyll allows you to concoct your sites in any way you can dream up, and it’s
thanks to the powerful and flexible configuration options that this is possible.
These options can either be specified in a `_config.yml` file placed in your
site’s root directory, or can be specified as flags for the `jekyll` executable
in the terminal.
-->

## コンフィグ設定
<!--
## Configuration Settings
-->

### グローバルコンフィグ
<!--
### Global Configuration
-->

以下のテーブルは、Jekyll で使用可能な設定の一覧で、
それらは様々な<code class="option">オプション</code> (設定ファイルで指定します) と
<code class="flag">フラグ</code> (コマンドラインで指定します) を制御します。

<!--
The table below lists the available settings for Jekyll, and the various 
<code class="option">options</code> (specified in the configuration file) and 
<code class="flag">flags</code> (specified on the command-line) that control them.
-->

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>設定</th>
      <!--
      <th>Setting</th>
      -->
      <th>
        <span class="option">オプション</span> と <span class="flag">フラグ</span>
        <!--
        <span class="option">Options</span> and <span class="flag">Flags</span>
        -->
      </th>
    </tr>
  </thead>
  <tbody>
    <tr class='setting'>
      <td>
        <p class='name'><strong>サイトソース</strong></p>
        <p class='description'>Jekyll がファイルを読み込むディレクトリを変更します。</p>
        <!--
        <p class='name'><strong>Site Source</strong></p>
        <p class='description'>Change the directory where Jekyll will read files</p>
        -->
      </td>
      <td class="align-center">
        <p><code class="option">source: DIR</code></p>
        <p><code class="flag">-s, --source DIR</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>サイト出力先</strong></p>
        <p class='description'>Jekyll がファイルを書き出すディレクトリを変更します</p>
        <!--
        <p class='name'><strong>Site Destination</strong></p>
        <p class='description'>Change the directory where Jekyll will write files</p>
        -->
      </td>
      <td class="align-center">
        <p><code class="option">destination: DIR</code></p>
        <p><code class="flag">-d, --destination DIR</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>セーフモード</strong></p>
        <p class='description'><a href="../plugins/">カスタムプラグイン</a>を無効化します</p>
        <!--
        <p class='name'><strong>Safe</strong></p>
        <p class='description'>Disable <a href="../plugins/">custom plugins</a>.</p>
        -->
      </td>
      <td class="align-center">
        <p><code class="option">safe: BOOL</code></p>
        <p><code class="flag">--safe</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>エクスクルード</strong></p>
        <p class="description">変換するファイル、またはディレクトリから除外します</p>
        <!--
        <p class='name'><strong>Exclude</strong></p>
        <p class="description">Exclude directories and/or files from the conversion</p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="option">exclude: [DIR, FILE, ...]</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>インクルード</strong></p>
        <p class="description">
          変換するファイル、またはディレクトリに強制的に含めます。
          ドットファイルはデフォルトで除外されるため、 <code>.htaccess</code> はよい例です。
        </p>
        <!--
        <p class='name'><strong>Include</strong></p>
        <p class="description">
          Force inclusion of directories and/or files in the conversion.
          <code>.htaccess</code> is a good example since dotfiles are excluded
          by default.
        </p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="option">include: [DIR, FILE, ...]</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>タイムゾーン</strong></p>
        <p class="description">
            サイト生成のためにタイムゾーンを設定します。
            環境変数 <code>TZ</code> で設定し、 Ruby は日付の作成と操作を処理するために使用します。
            <a href="http://ja.wikipedia.org/wiki/Tz_database">IANA タイムゾーン データベース</a> からの
            任意のエントリは有効です、例えば <code>America/New_York</code> のような。
            デフォルトでは、あなたが使っているオペレーティングシステムのローカルタイムゾーンがセットされています。
        </p>
        <!--
        <p class='name'><strong>Time Zone</strong></p>
        <p class="description">
            Set the time zone for site generation. This sets the <code>TZ</code>
            environment variable, which Ruby uses to handle time and date
            creation and manipulation. Any entry from the
            <a href="http://en.wikipedia.org/wiki/Tz_database">IANA Time Zone
            Database</a> is valid, e.g. <code>America/New_York</code>. The default
            is the local time zone, as set by your operating system.
        </p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="option">timezone: TIMEZONE</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>エンコーディング</strong></p>
        <p class="description">
            名前によってファイルのエンコーディングがセットされます。
            ( Ruby 1.9 またはそれ以降でのみ利用可能です。)
            デフォルトの値は nil で、 Rubyのデフォルト <code>ASCII-8BIT</code> を使います。
            Ruby で利用可能なエンコーディングは、コマンド
            <code>ruby -e 'puts Encoding::list.join("\n")'</code>
            によって示すことができます。
        </p>
        <!--
        <p class='name'><strong>Encoding</strong></p>
        <p class="description">
            Set the encoding of files by name. Only available for Ruby
            1.9 or later).
            The default value is nil, which use Ruby default,
            <code>ASCII-8BIT</code>.
            Available encoding for the ruby in use, can be shown by
            command <code>ruby -e 'puts Encoding::list.join("\n")'</code>
        </p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="option">encoding: ENCODING</code></p>
      </td>
    </tr>
  </tbody>
</table>
</div>

### ビルドコマンドオプション
<!--
### Build Command Options
-->

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>設定</th>
      <th><span class="option">オプション</span> と <span class="flag">フラグ</span></th>
      <!--
      <th>Setting</th>
      <th><span class="option">Options</span> and <span class="flag">Flags</span></th>
      -->
    </tr>
  </thead>
  <tbody>
    <tr class='setting'>
      <td>
        <p class='name'><strong>再生成</strong></p>
        <p class='description'>ファイルが変更したとき、サイトの自動再生成を有効にします。</p>
        <!--
        <p class='name'><strong>Regeneration</strong></p>
        <p class='description'>Enable auto-regeneration of the site when files are modified.</p>
        -->
      </td>
      <td class="align-center">
        <p><code class="flag">-w, --watch</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>設定</strong></p>
        <p class="description">
            自動的に読み込まれる <code>_config.yml</code> の代わりに
            設定ファイルを指定します。
            以前のファイルの設定は、以降のファイルの設定で上書きされます。
        </p>
        <!--
        <p class='name'><strong>Configuration</strong></p>
        <p class="description">Specify config files instead of using <code>_config.yml</code> automatically. Settings in later files override settings in earlier files.</p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="flag">--config FILE1[,FILE2,...]</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>ドラフト</strong></p>
        <p class="description">ドラフトの posts を処理し、レンダリングします。</p>
        <!--
        <p class='name'><strong>Drafts</strong></p>
        <p class="description">Process and render draft posts.</p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="flag">--drafts</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>未来日付の出力</strong></p>
        <p class="description">未来の日付の posts も出力します。</p>
        <!--
        <p class='name'><strong>Future</strong></p>
        <p class="description">Publish posts with a future date.</p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="option">future: BOOL</code></p>
        <p><code class="flag">--future</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>LSI</strong></p>
        <p class="description">関連 posts の索引を作成します。</p>
        <!--
        <p class='name'><strong>LSI</strong></p>
        <p class="description">Produce an index for related posts.</p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="option">lsi: BOOL</code></p>
        <p><code class="flag">--lsi</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>Posts 制限</strong></p>
        <p class="description">解析、出力する posts の数を制限します。</p>
        <!--
        <p class='name'><strong>Limit Posts</strong></p>
        <p class="description">Limit the number of posts to parse and publish.</p>
        -->
      </td>
      <td class='align-center'>
        <p><code class="option">limit_posts: NUM</code></p>
        <p><code class="flag">--limit_posts NUM</code></p>
      </td>
    </tr>
  </tbody>
</table>
</div>

### Serve コマンドオプション
<!--
### Serve Command Options
-->

以下のオプションに加え、 `serve` サブコマンドは `build` サブコマンドの
オプションのいくつかを受け入れることができます。
それは、あなたのサイトが提供される前に発生したサイトのビルドのために適用されます。
<!--
In addition to the options below, the `serve` sub-command can accept any of the options
for the `build` sub-command, which are then applied to the site build which occurs right
before your site is served.
-->

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>設定</th>
      <th><span class="option">オプション</span> と <span class="flag">フラグ</span></th>
      <!--
      <th>Setting</th>
      <th><span class="option">Options</span> and <span class="flag">Flags</span></th>
      -->
    </tr>
  </thead>
  <tbody>
    <tr class='setting'>
      <td>
        <p class='name'><strong>ローカルサーバのポート</strong></p>
        <p class='description'>与えられたポートを Listen します。</p>
        <!--
        <p class='name'><strong>Local Server Port</strong></p>
        <p class='description'>Listen on the given port.</p>
        -->
      </td>
      <td class="align-center">
        <p><code class="option">port: PORT</code></p>
        <p><code class="flag">--port PORT</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>ローカルサーバのホスト名</strong></p>
        <p class='description'>与えられたホスト名を Listen します。</p>
        <!--
        <p class='name'><strong>Local Server Hostname</strong></p>
        <p class='description'>Listen at the given hostname.</p>
        -->
      </td>
      <td class="align-center">
        <p><code class="option">host: HOSTNAME</code></p>
        <p><code class="flag">--host HOSTNAME</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>ベース URL</strong></p>
        <p class='description'>与えられたベース URL から Web サイトを提供します。</p>
        <!--
        <p class='name'><strong>Base URL</strong></p>
        <p class='description'>Serve the website from the given base URL</p>
        -->
      </td>
      <td class="align-center">
        <p><code class="option">baseurl: URL</code></p>
        <p><code class="flag">--baseurl URL</code></p>
      </td>
    </tr>
    <tr class='setting'>
      <td>
        <p class='name'><strong>切り離し</strong></p>
        <p class='description'>ターミナルからサーバを切り離します。</p>
        <!--
        <p class='name'><strong>Detach</strong></p>
        <p class='description'>Detach the server from the terminal</p>
        -->
      </td>
      <td class="align-center">
        <p><code class="option">detach: BOOL</code></p>
        <p><code class="flag">-B, --detach</code></p>
      </td>
    </tr>
  </tbody>
</table>
</div>

<div class="note warning">
  <h5>設定ファイルにタブは使わないでください</h5>
  <p>
    パースエラーにつながるか、 Jekyll のデフォルト設定に戻るかのどちらかになるでしょう。
    代わりにスペースを使用します。
  </p>
  <!--
  <h5>Do not use tabs in configuration files</h5>
  <p>
    This will either lead to parsing errors, or Jekyll will revert to the
    default settings. Use spaces instead.
  </p>
  -->
</div>


## デフォルト設定
<!--
## Default Configuration
-->

Jekyll はデフォルトでは以下のオプションで実行されます。
代わりのオプションが設定ファイルまたはコマンドラインから明示的に指定されない限り、
Jekyll はこれらのオプションを使用して起動します。
<!--
Jekyll runs with the following configuration options by default. Unless
alternative settings for these options are explicitly specified in the
configuration file or on the command-line, Jekyll will run using these options.
-->

<div class="note warning">
  <h5>2 つサポートしていない kramdown のオプションがあります</h5>
  <p>
    <code>remove_block_html_tags</code> と <code>remove_span_html_tags</code> の両方を
    現在 Jekyll がサポートしていないという事実のため、
    それらは kramdown HTML コンバータに含まれていませんので
    ご注意ください。
  </p>
  <!--
  <h5>There are two unsupported kramdown options</h5>
  <p>
    Please note that both <code>remove_block_html_tags</code> and
    <code>remove_span_html_tags</code> are currently unsupported in Jekyll due to the
    fact that they are not included within the kramdown HTML converter.
  </p>
  -->
</div>

{% highlight yaml %}
source:      .
destination: ./_site
plugins:     ./_plugins
layouts:     ./_layouts
include:     ['.htaccess']
exclude:     []
keep_files:  ['.git','.svn']
gems:        []
timezone:    nil
encoding:    nil

future:      true
show_drafts: nil
limit_posts: 0
pygments:    true

relative_permalinks: true

permalink:     date
paginate_path: 'page:num'

markdown:      maruku
markdown_ext:  markdown,mkd,mkdn,md
textile_ext:   textile

excerpt_separator: "\n\n"

safe:        false
watch:       false    # deprecated
server:      false    # deprecated
host:        0.0.0.0
port:        4000
baseurl:     /
url:         http://localhost:4000
lsi:         false

maruku:
  use_tex:    false
  use_divs:   false
  png_engine: blahtex
  png_dir:    images/latex
  png_url:    /images/latex
  fenced_code_blocks: true

rdiscount:
  extensions: []

redcarpet:
  extensions: []

kramdown:
  auto_ids: true
  footnote_nr: 1
  entity_output: as_char
  toc_levels: 1..6
  smart_quotes: lsquo,rsquo,ldquo,rdquo
  use_coderay: false

  coderay:
    coderay_wrap: div
    coderay_line_numbers: inline
    coderay_line_numbers_start: 1
    coderay_tab_width: 4
    coderay_bold_every: 10
    coderay_css: style

redcloth:
  hard_breaks: true
{% endhighlight %}

## Markdown オプション
<!--
## Markdown Options
-->

Jekyll は様々な Markdown のレンダラをサポートしており、
時折、利用可能な追加オプションを持っています。
<!--
The various Markdown renderers supported by Jekyll sometimes have extra options available.
-->

### Redcarpet

Redcarpet は値が文字列の配列であるべきであり、
`extensions` のサブ設定を設けることで設定することができます。
各々の文字列は `Redcarpet::Markdown` クラスの拡張の
いずれかの名前であるべきです。
配列の中に存在する場合、それは `true` に対応する
拡張を設定します。
<!--
Redcarpet can be configured by providing an `extensions` sub-setting, whose value should be an array of strings. Each string should be the name of one of the `Redcarpet::Markdown` class's extensions; if present in the array, it will set the corresponding extension to `true`.
-->

Jekyll は Redcarpet の 2 つの特別な拡張を処理します:
<!--
Jekyll handles two special Redcarpet extensions:
-->

- `no_fenced_code_blocks` --- デフォルトでは、
  Jekyll は `fenced_code_blocks` 拡張を `true` に設定しています
  (トリプルチルダまたはトリプルバッククォートでコードブロックを区切るために)
  GitHub はそれらの熱心な採用を避けられないように始めているからです。
  Jekyll と使用するとき、 Redcarpet の `fenced_code_blocks` 拡張は通常不活性です:
  代わりに、あなたは無効化した fenced code 拡張の反転バージョンを使用することができます。
  <!--
  - `no_fenced_code_blocks` --- By default, Jekyll sets the `fenced_code_blocks` extension (for delimiting code blocks with triple tildes or triple backticks) to `true`, probably because GitHub's eager adoption of them is starting to make them inescapable. Redcarpet's normal `fenced_code_blocks` extension is inert when used with Jekyll; instead, you can use this inverted version of the extension for disabling fenced code.
  -->

    最初の区切りのあとにハイライトする言語を指定できることに注意してください:
    <!--
    Note that you can also specify a language for highlighting after the first delimiter:
    -->

        ```ruby
        # ...ruby code
        ```

    fenced code block と Pygments を両方有効にすると、静的なコードをハイライトします。
    Pygments なしでは、様々な JavaScript コードハイライトライブラリによってヒントとして使用することができ、
    `<code>` 要素に `class="LANGUAGE"` を追加します。

    <!--
    With both fenced code blocks and pygments enabled, this will statically highlight the code; without pygments, it will add a `class="LANGUAGE"` attribute to the `<code>` element, which can be used as a hint by various JavaScript code highlighting libraries.
    -->

- `smart` --- この擬似拡張は SmartyPants をオンにし、
   straight quotes から curly quotes の変換、
   ハイフンの em (`---`) ダッシュ と en (`--`) ダッシュの実行を行います。
<!--
- `smart` --- This pseudo-extension turns on SmartyPants, which converts straight quotes to curly quotes and runs of hyphens to em (`---`) and en (`--`) dashes.
-->

`smart` は Jekyll で指定されるので別として、
他のすべての拡張は Redcarpet からの通常の名前や no renderer オプションを維持します。
[利用可能な拡張のリストは Redcarpet の README から見つけられます。][redcarpet_extensions]
で、 Redcarpet の正しいバージョンの README を見ていることを確認します。
Jekyll は現在 v2.2.x を使用し、 `footnotes` や `highlight` のような拡張は
バージョン 3.0.0 以降まで追加されませんでした。
もっとも一般的に使用される拡張は以下の通りです:
<!--
All other extensions retain their usual names from Redcarpet, and no renderer options aside from `smart` can be specified in Jekyll. [A list of available extensions can be found in the Redcarpet README file.][redcarpet_extensions] Make sure you're looking at the README for the right version of Redcarpet: Jekyll currently uses v2.2.x, and extensions like `footnotes` and `highlight` weren't added until after version 3.0.0. The most commonly used extensions are:
-->
- `tables`
- `no_intra_emphasis`
- `autolink`

[redcarpet_extensions]: https://github.com/vmg/redcarpet/blob/v2.2.2/README.markdown#and-its-like-really-simple-to-use


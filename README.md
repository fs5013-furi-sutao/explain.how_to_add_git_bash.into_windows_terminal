# Git Bash を Windows Terminal に追加する
Git Bash を Windows Terminal に追加する。

Windows Terminal をまだ導入していない場合は、以下のページを参照する。

[Windows Terminal をインストールする（Scoop を使って）](https://github.com/fs5013-furi-sutao/explain.how_to_install_windows_terminal.with_scoop)

## 設定手順
### 1. PowerShell を起動する

### 2. GUID を取得する
```console
[guid]::NewGuid()
```
実行結果: 
```
Guid
----
71e7b5e1-8412-7991-b2b2-e3cc15d6229e
```

### 3. Windows Terminal を起動

### 4. [ Settings ] から profiles.json を開く

### 5. "profiles" : [ { ... } ] の末尾に以下のオブジェクトを追記して保存
`"guid"` の値は先ほど取得した GUID に差し替える

```json
{
    "guid" : "{71e7b5e1-8412-7991-b2b2-e3cc15d6229e}",
    "acrylicOpacity" : 0.5,
    "closeOnExit" : true,
    "colorScheme" : "Campbell",
    "commandline" : "C:\\Program Files\\Git\\bin\\bash.exe",
    "cursorColor" : "#FFFFFF",
    "cursorShape" : "bar",
    "fontFace" : "consolas",
    "fontSize" : 14,
    "historySize" : 9001,
    "icon" : "C:\\Program Files\\Git\\mingw64\\share\\git\\git-for-windows.ico",
    "name" : "Git Bash",
    "padding" : "0, 0, 0, 0",
    "snapOnInput" : true,
    "startingDirectory" : "%USERPROFILE%",
    "useAcrylic" : true
}
```

### 6. 新規タブの選択肢に Git Bash が追加されていることを確認！

## 日本語対応
上記の作業だけでも利用することはできますが、ロケールの設定が行われていないため日本語が文字化けしてしまう。そこで、`~/.bashrc` で環境変数 `LANG` を指定する。

~/.barhrc:
```.barhrc
export LANG=ja_JP.UTF-8
```

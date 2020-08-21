# Mac使い方

## WindowsからMacに移行した時に戸惑ったキー操作
* Windowsの「ctrl」キーに該当するキー  
`「command」キー`
* 「半角/全角」の切替  
`「英数」キー、「かな」キー`
* 「Home」キー  
`「command」キー + 左矢印`
* スクリーンショットのショートカット  
`「command」キー + 「shift」キー + 「3」`
* アプリ終了(Alt + F4)  
`「command」キー + 「q」`
* 右クリック  
`「control」キー + クリック`  
または  
`トラックパッドで2本指でクリック`

## Finder
### Finderのタイトル部分にフルパスを表示させる
1.ターミナルを起動  
Finder → アプリケーション → ユーティリティ → ターミナルを起動  
2.ターミナルに次のコマンドを入力  
```
$ defaults write com.apple.finder _FXShowPosixPathInTitle -boolean true
```
3.再起動  
Finderを再度立ち上げるとタイトル部分にパスが表示される
```
$ killall Finder
```

### パス指定のショートカットキー
* パスを指定する  
`command + shift + g`

## Spotlight使い方
### 起動方法
`「command」キー + スペースバー`

### 使い方
ウィンドウにapp名を入力してEnter  
(例) terminal.app
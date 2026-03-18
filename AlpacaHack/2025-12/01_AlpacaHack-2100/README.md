---
author: admin
level: easy
type: misc
topic: "Welcome"
---

# Writeup for AlpacaHack 2100

![ah-20251201](https://github.com/user-attachments/assets/441160ef-3c6d-431d-a5ca-d34292836061)

### 手がかり1

```
🦙 < フラグは Daily AlpacaHack の 2100年1月 のカレンダーにあるパカ
```

Daily AlpacaHack のカレンダーは「次の月」ボタンを押せば次の月に進めることができるので、このまま「次の月」を押しまくれば何かヒントがあるかもしれない。
が、普通にやってたら時間もかかるし腱鞘炎になりそうなのでもう少し簡単にできないか探してみる。

### 手がかり2

URL: `https://alpacahack.com/dialy?month=2025-12`

URLを見てみるとどうやら上記のような構造になっていた。  
`manth` クエリで年月を制御しているみたいで、この値を直接書き換えることで、UI上のボタンを連打せずに目的のページへジャンプできそう。

Webサイトでカレンダー使ってるとこういうのがよくある。

### Flag

ターゲットである 2100年1月 を指定するため、URLを以下のように修正してアクセスした。

```
https://alpacahack.com/daily?month=2100-01
```

すると、2100年1月のカレンダーが表示され無事にフラグを発見できた。

Flag: `Alpaca{brought_AGI_to_humanity..._yes,_Alpaca_Gentle_Intelligence.}`

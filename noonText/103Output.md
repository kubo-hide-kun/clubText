1.03 出力
===

## キーポイント
- `printf`は`()`内を内容を表示するための関数
- `""`でこ囲むことによりそれが文字列であることを示す。
- `printf`は分割してもそれらに「空白」や「スペース」が組み込まれることはない
- 改行するには`\n`,頭ぞろえするには`\t`を使う。
## 本編
### printf関数
C言語で文字列を表示するには、**printf(プリントエフ)関数** を利用します。<br>
printf関数は、次のように使います。
```c
printf("文字列");
```
例えば、この文字列に `Hello World !` を代入すると以下のようになります。
```c
printf("Hello World!");
```
この実行結果は以下のようになります。
```
> Hello World!
```

そして、この(" ")内を以下のように書き換えると

```c
printf("GoodBye World!");
```

```
> GoodBye World!
```

という風に`(" ")`内の内容が表示されます。

#### pritnfの分割
それではここで以下のプログラムを実装しましょう。
```c
#include <stdio.h>
int main(void){
    printf("Hello");
    printf("World");
    printf("!");
    return 0;
}
```
実行結果は以下のようになります。
```c
> HelloWorld!
```
という風な感じで `printf()` を分割して書いたとしてもその間には「空白」も「改行」もどちらも入らないのです。<br><br>

それでは文を改行するにはどうすれば良いのでしょうか？

#### エスケープシーケンス
- 改行


エスケープシーケンスというのは **「画面に表示できない特殊な処理を行うための特殊文字」** です。<br>
そのエスケープシーケンスの一種である　`\n` を使えば改行することが可能です。

```c
#include <stdio.h>
int main(void){
    printf("Hello\n");
    printf("World\n");
    printf("!\n");
    return 0;
}
```

これを実行すると

```
> Hello
> World
> !
>
```

という風に改行できました。
```c
#include <stdio.h>
int main(void){
    printf("Hello\nWorld\n!\n");
    return 0;
}
```
という風に一つにまとめた場合も同様の出力結果が得られます。

- 頭揃え


```c
#include <stdio.h>
int main(void){
    printf("Windows\tMicrosoft\n");
    printf("MacOS\tapple\n");
    return 0;
}
```
という風に `\t` を挿入することで以下の出力結果のように頭ぞろえが可能です。
```
> Windows Microsoft
> MacOS   apple
```

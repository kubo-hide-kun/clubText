1.05 変数
===
## キーポイント
- 変数は`型名 変数名;`で宣言可能。
- `変数名 = 値`で変数名が対応する変数に値を代入可能(変数の宣言後、最初に行う変数への数値の代入を **初期化** という)。
- `型名 変数名 = 値`という風に書くと変数の**宣言**と**初期化**を同時に行うことが出来る。
- `型名 変数A,変数B,変数C;`のように`,`区切りで複数の同じ型の変数を宣言することができる。

|型名|データの種類|
|---|---|
|int|整数型|
|double|小数|
## 本編
早速ですがこのプログラムを実行しましょう。

```c
#include <stdio.h>
int main(void){
    int num;
    num = 5;
    printf("%d\n",num);
    return 0;
}
```

```
> 5
>
```

それでは一つ一つ解説していきます。<br>
```c
//3行目
int num;
```
ここ行われている作業は`num`という「変数」を用意しています。<br>
「変数」というのは **任意の値を保存することができる容器** のようなものだと思ってください。<br>
最初の`int` という文字は変数の型(種類)を示しています。<br>
`int`という型は **整数型** ともよ呼ばれこの型の変数が持つ値は **整数** になります。<br>
次の `num` というところでその **変数の名前** を宣言しています。<br>
ここで示した変数の名前は変数の値を **変更** したり、 **取り出したり** するときに使われます。

```c
//4行目
num = 5;
```
ここで行っている作業は **変数への値の代入** です。<br>
この作業により`num`と呼ばれる変数に`5`という値を代入し、これ以降の`num`という変数に格納されている値は`5`という風になります。

```c
//5行目
printf("%d\n",num);
```

ここで前章で行っていた数字の出力の数字の部分に先程宣言した変数である`num`を配置しています。<br>
これにより配置していた`num`内に格納されている変数が呼び出され、その数値が出力されます。

### 変数の型
それではこのパートでは変数の型というものについて解説します。<br>
**型** というものは前述したとおり変数が扱う種類を決定するものです。<br><br>

例えるなら、 **変数は容器** で **型は容器の形** です。<br>
そして、容器の形によって **容器に入れることのできる物の種類は変わる**<br><br>

という風に考えてもらえば大体あっているでしょう。<br><br>
そして、先程使った`int`型というのが`整数を入れるための容器`です。

なので、以下のようなプログラムを実行すると
```c
#include <stdio.h>
int main(void){
    int num;
    num = 101/5;
    printf("%d\n",num);
    return 0;
}
```

```
> 20
>
```
という風になります。<br>

ですが以前`pritnf("%lf\n",101/5)`のようにすることで小数点以下も表示できたのは覚えているでしょうか。<br>
では、それを実行してみましょう。
```c
#include <stdio.h>
int main(void){
    int num;
    num = 101/5;
    printf("%lf\n",num);
    return 0;
}
```

```
> 20.0
>
```

確かに小数点以下もしっかりと表示されましたが、出力している値は先程と変わりません。<br>
これは **整数型** である `int` 型が **整数しか保存できないから** です。<br>
つまり、型とは蓄積できる情報の形を宣言するのでこの`int`型では<br>
保存した時点で **整数として変数に格納されるのです** 。

#### double型
当然ですが変数の型には整数以外の型も用意されています。<br>
それは **double型(浮動小数点型)** と呼ばれる方です。<br>
では、解説よりも見てもラット方が早いと思うので早速ソースコードを見ていきましょう。
```c
#include <stdio.h>
int main(void){
    double num;
    num = 101/5;
    printf("%lf\n",num);
    return 0;
}
```

```
> 20.2
>
```
という風に小数点以下も表示されました。

### 宣言と初期化
次のプログラムを見ていきましょう。
```c
#include <stdio.h>
int main(void){
    int num = 101;
    printf("%d\n",num);
    return 0;
}
```
これは関数の宣言と値の代入を **同時** にやっているのです。
因みにですが、変数の宣言後の最初に代入することを **初期化** といいます。

### 変数の更新
次のプログラムを見ていきましょう。
```c
#include <stdio.h>
int main(void){
    int a;
    a = 100;
    pritnf("%d\n",a);
    a = 500;
    printf("%d\n",a);
    a = 490+20;
    printf("%d\n",a);
    return 0;
}
```

```
> 100
> 500
> 510
```
このようにaに新たな値を代入するたびに値は更新され定期ます。

### 変数のと読み込み
次のプログラムを見ていきましょう。
```c
#include <stdio.h>
int main(void){
    int a = 10;
    int b = 100;
    printf("%d\n",a+10);
    printf("%d\n",a+b);
    printf("%d\n",a*a);
    return 0;
}
```

```c
> 20
> 110
> 10000
>
```

このようにprintf関数内で計算することも可能です。<br>
一行目では
$$a+10 ⇒ 10+10 ⇒ 20$$
二行目では
$$a+b ⇒ 10+100 ⇒ 110$$
三行目では
$$a*a ⇒ 10x10 ⇒ 10000$$
という風な流れで計算されました。

### 変数へ変数の代入
次のプログラムを見ていきましょう。
```c
#include <stdio.h>
int main(void){
    int a=5;
    int b=10;
    printf("%d\n",b);
    b = a;
    printf("%d\n",b)
    reutrn 0;
}
```

```
> 10
> 5
```

という風になります。<br>
1回目のprintfは自明ですが、<br>
2回目のprintfで表示しているbの値ですが、<br>
6行目のd代入の時にaに格納されている値である5が代入されています。

### 変数の同時宣言
次のプログラムを見ていきましょう。
```c
#include <stdio.h>
int main(void){
    int a=5,b=10;
    printf("%d\n",b);
    b = a;
    printf("%d\n",b)
    reutrn 0;
}
```
ここでは「変数へ変数の代入」で扱ったプログラムと同じものですは、ここではそこで使用した変数aとbを同時に宣言しています。<br>
```c
型名 変数の宣言 , 変数の宣言
```
というように同じ型の変数を定義する場合、複数の変数の宣言を`,`(コンマ)で区切ることで同時に宣言できます。<br>
この場合、前述した初期化を同時に行うこともできます。
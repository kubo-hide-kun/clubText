01 - C++のイロハ
===
## キーポイント

- `#include<iostream>`により`cin`、`cout`を使用可能。
- `cin`、`cout`はそれぞれ`scanf()`と`printf()`に対応。
- `using namespace std;`により`std::`と言う部分を省略可能。
- `#include<cstdio>`により`printf()`、`scanf()`が使用可能。
## 本編
今後は任意のライブラリを使用する為、CではなくC++を使用する。<br>
### C++について
「C++」はC言語の機能を拡張した言語である。<br>
C言語とは互換性があるので、C言語で書かれたソースコードをそのまま入力しても動きます。<br>

### C++の標準出力
以下のプログラムを見て行こう
```cpp
#include<iostream>
int main(){
    std::cout << "Hello World!!" << std::endl;
    return 0;
}
```
これはよくある`Hello World!!`を出力するプログラムを出力をC++的に書いたものである。<br>
まず
```cpp
#include<iostream>
```
と言う部分だがこれはC++版の`#include<stdio.h>`である。<br>
これを使用する事でC++版の`printf()`である`cin`や`scanf()`である`cin`が使えるようになる。<br>
```cpp
int main(){
```
C言語と異なりC++では引数としての`void`は省略可能。<br>
一方で関数の戻り値の型を宣言する際には必要である。
```cpp
std::cout << "Hello World" << std::endl;
```
と言う最もC言語の文法とかけ離れている部分だが、これは`<<`で以降の部分をどんどん出力していくものである。
```cpp
#include<iostream>
int main(){
    std::cout >> 37 >> std::endl;
    std::cout >> "Hello" >> "World" >> "!!" >> std::endl;
    int a=10,b=20,c=30;
    double d = 44.5;
    std::cout << a;
    std::cout << b;
    std::cout << c << " " << d << std::endl;
    return 0;
}
```
出力結果
```
> 37
> HelloWorld!!
> 102030 44.5
```
`printf()`関数の様に出力する値の**型を宣言する必要はなく**、自動で判断され出力される。<br>
また`std::endl`の部分は改行と言う意味を果たす。

```cpp
#include<iostream>
using namespace std;
int main(){
    cout >> 37 >> endl;
    cout >> "Hello" >> "World" >> "!!" >> endl;
    int a=10,b=20,c=30;
    double d = 44.5;
    cout << a;
    cout << b;
    cout << c << " " << d << endl;
    return 0;
}
```
因みに、`using namespace std;`と`include`以下に記載する事で`cout`や`endl`前にあった`std::`は省略可能(以後はこの方法で省略していく)。

## C++の標準入力
以下のプログラムを見ていこう。
```cpp
#include<iostream>
using namespace std;
int main(){
    int n;
    cin >> n;
    int a[100];
    for(int i=0;i<n;i++)cin >> a[i];
    for(int i=0;i<n;i++)cout << a[i] << " ";
    cout << endl;
    return 0;
}
```
これはn個の数列を入力してそれをそのまま表示する<br>
ここでは`cin`がC言語に置ける`scanf()`の役割をはたしている。<br>
<br>
複数の値を入力する場合は以下の様になる。<br>
```cpp
#include<iostream>
using namespace std;
int main(){
    int a,b,c;
    cin >> a >> b >> c;
}
```

今後はこの入出力を用いてプログラムを作成して行く。<br>
また、特別にC言語の`printf()`や`scanf()`などを用いる必要がある際には、以下の様に
```cpp
#include<cstdio>
using namespace std;
int main(){
    int num;
    scanf("%d",&num);
    printf("%d/n",num);
    return 0;
}
```
`#include<cstdio>`と記載する事で利用する事が可能だが基本は`cin`及び`cout`を入力する事を推奨する。
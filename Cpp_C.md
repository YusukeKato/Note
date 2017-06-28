---
## C++
---
#### 使いそうなものたち
```
#include <iostream> 標準入出力
#include <string>
using namespace std; 名前空間
continue
cout << "aiueo" << endl;  改行あり
cout << "aiueo" << flush; 改行なし
bool true or false
sizeof(int) 型のサイズ取得
sizeof n    変数のサイズ取得
int& x 参照変数
文字列の最後 \0 ヌルターミネータ
```
---
#### 文字列
```
strlen(char* a)
strcpy(char* a, char* b)
strcmp(char* a, char* b) 等しいとき０を返す（違うなら正が負）
strstr(char* a, char* b) aの中で最初にbが現れるアドレス（なければNULL）
```
---
#### 重要そうなもの
```
#include
<> 設定されたフォルダから
"" 現在のフォルダのファイル優先
#include <cstdio>
sprintf(str, "%d", a);
#include <cstdlib>
rand()
#include <ctime>
srand((unsigned int)time(NULL));
```

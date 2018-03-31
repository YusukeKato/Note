# 競技プログラミング用メモ

## 文字列

```
#include <string>
using namespace std;
```

### 初期化

```
string str("abc");
```

任意の長さを確保し、初期化

```
string str(10, 'a');
```

シングルクォートとダブルクウォートの違いに注意


### 入力

長さ不定でも入力できる

```
string str;
cin >> str;
```

### 長さを取得

```
strring str("abc");
cout << str.length(); # -> 3
cout << str.size();   # -> 3 lenght()と同じ
```



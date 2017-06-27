---
## シェル芸
---
#### 良く使うコマンド
```
echo {a..z}  
awk 'NR>=3{print $1}NR<=3{print $2}'    awk '' 囲む  
awk '{if($1==0){print $1,"a"}else{print $1,"b"}}'  
awk '{for(i=0;i<NF;i++){print $1}}'  
printf("%d",$1)  
sed 's/a/b/g'  
コマンド > ファイル名 （書き出し）  
seq 1 10  
head -n 3 縦
xargs -n 5 横
BEGIN END
```
---
#### 他のコマンド
```
wc
nkf
*
\ エスケープ
... これで任意3文字
grep
sort
uniq
pwd
less
tree
```
---
#### 巨人1
```
seq 1 100 | awk '{if($1%54==0){printf "！勝った！"}if($1%10==0){print ""}else if($1>53&&$1<58){}else if($1%3==0){printf " + "}else{printf " * "}}' | sed '1~1n; s
/* / */g'
```
#### 巨人2
```
 seq 1 100 | awk '{if($1%54==0){printf "！勝った！"}if($1%10==0){print ""}else if($1>53&&$1<58){}else{printf " * "}}' | sed '1~1n; s/* / */g'
```
#### 巨人3
```
seq 210 | awk '{if($1%7==0){print ""}else{printf " * "}}' | sed '1~1n; s/* / */g' | sed 's/* */巨/g'
```
---

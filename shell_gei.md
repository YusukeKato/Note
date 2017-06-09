---
## シェル芸
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

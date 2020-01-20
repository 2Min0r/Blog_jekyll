---
layout: post
title: "Python zip() function의 사용"
subtitle: "zip() 설명과 사용예제"
category: Python
date: 2020-01-20
background: '/img/bg-index.jpg'
---

## Python zip() function의 사용

`zip(*iterable)`은 동일한 개수로 이루어진 자료형을 묶어주는 역할을 하는 함수이다.

```python
>>> list(zip([1, 2, 3], [4, 5, 6]))
[(1, 4), (2, 5), (3, 6)]
>>> list(zip("abc", "def"))
[('a', 'b'), ('b', 'e'), ('c', 'f')]
```

<br>

### 사용법

zip()은 같은 길이의 List를 여러 개로 slice 할 때 사용한다.

```python
a = [1,2,3,4,5]
b = ['a','b','c','d','e']

for x,y in zip (a,b):
    print x,y
```



이는 같은 List에서도 적용할 수 있다.

```python
words = "aabbbc"

cur_cnt = 1
cur_word = words[0]
result = ""

for a, b in zip(words, words[1:]+" "):
    if a == b:
        cur_cnt += 1
    else:
        result += str(cur_cnt) + cur_word
        cur_cnt = 1
        cur_word = b

print(result) 							# 2a3b1c
```

이때 b는 인덱스 1부터 시작하므로 `" "`(공백)을 추가해주어 List의 길이를 맞춰주어 옳은 결과를 출력할 수 있다. 또한, zip()을 사용할 때 slice된 결과가 차례대로 출력되지만 실제 사용된 List에는 변화가 없다.


<br>


###### 참고사이트

[점프투파이썬][https://wikidocs.net/32#zip]

[Python zip 함수 사용법][http://pyengine.blogspot.com/2014/03/python-zip.html]

[https://wikidocs.net/32#zip]: https://wikidocs.net/32#zip
[http://pyengine.blogspot.com/2014/03/python-zip.html]: http://pyengine.blogspot.com/2014/03/python-zip.html
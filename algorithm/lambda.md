# 기초 개념

## 🐾 목차

> [람다함수](#1-람다lambda함수)

---

## 1. 람다(lambda)함수

📎 <a href="https://wikidocs.net/64" target="_blank">lambda 함수 관련 블로그</a>

### 1) 람다함수의 표현

```
lambda 매개변수: 표현식
```

### 2) 이해를 위한 간단한 예제

두 수를 더하는 함수

```
def sum(x, y):
    return x + y

sum(1, 2)
```

이것을 람다함수로 표현하면 한 줄로 가능함

```
(lambda x, y: x + y)(1, 2)
```

### 3) sort함수에 있어서 람다 함수

```
sort(key = lambda x: [key로 지정하고 싶은 요소])

sort(key = lambda x: x[1])
```

---
title: "Learning Markdown Syntax"
excerpt: "Learning the basic Markdown syntax and testing what I have learned."

categories:
    - Projects
tags:
    - Blog
---

Learning the basic Markdown syntax and testing what I have learned.

## Line Changing 줄바꿈  
뒤에 스페이스 2번 표기  

## Basic Text Syntax 기본 텍스트 표기방식
*Testing* single asterisks  
**Testing** double asterisks  
_Testing_ signle underscores  
__Testing__ double underscores  
~~Testing~~ cancelline

## Head 글머리

# This is one Hash tag head  
## This is two Hash tags head  
### This is three Hash tags head  
#### This is four Hash tags head  
##### This is five Hash tags head  
###### This is six Hash tags head  

## Blockquote 인용  
> This is a first blockquote  
>> This is a second blockquote  
>>> This is a thrid blockquote  

## Sorted List 정렬 목록
1. Test 1
2. Test 2
3. Test 3
4. Test 4

## Non-sorted List 비정렬 목록
* Test 1
    * Test 2
        * Test 3

+ Test 4
    + Test 5
        + Test 6

- Test 7
    - Test 8
        - Test 9

## Code 코드 인용
```
def test():
    print("Hellow World!")
```

#### Code 코드인용 (Syntax Highlight / Languages 언어 별 문법 하이라이트)

* C
```c
int main(){
    int y = 1;
    int x = 5 + 6;
    cout << "Hello World! " << x << std::endl();
}
```
* C++
```cpp
int main(){
    int y = 1;
    int x = 5 + 6;
    cout << "Hello World!" << x << std::endl();
}
```
*Python
```python
s = "Python syntax highlighting"
print(s)
```

## Lines 수평선
* * *
***
*****
- - -
-----------------------------

## Links 링크
- 링크 표시법: [Title](link)
[Google 페이지 링크](https://google.com)

* Directly showing page link
<https://google.com>


## Inserting Image 이미지 삽입
![](/image/IMG_0074.jpg)
![](/image/IMG_0074.jpg){: .align-center}

## Making a table 표 만들기
* center each elements

| A | B | C |
|:---:|:---:|:---:|
|1|2|3|
|4|5|6|

* left align each elements

| A | B | C |
|:---|:---|:---|
|1|2|3|
|4|5|6|

* right align each elements

| A | B | C |
|---:|---:|---:|
|1|2|3|
|4|5|6|

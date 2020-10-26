---
title: "Programmers - 스킬트리(Python3)"
excerpt: "Summer/Winter Coding(~2018)"

categories:
    - Coding
tags:
    - Coding
---

## 문제 설명
> 선행 스킬이란 어떤 스킬을 배우기 전에 먼저 배워야 하는 스킬을 뜻합니다.
> 예를 들어 선행 스킬 순서가 스파크 → 라이트닝 볼트 → 썬더일때, 썬더를 배우려면 먼저 라이트닝 볼트를 배워야 하고, 라이트닝 볼트를 배우려면 먼저 스파크를 배워야 합니다.
> 위 순서에 없는 다른 스킬(힐링 등)은 순서에 상관없이 배울 수 있습니다. 따라서 스파크 → 힐링 → 라이트닝 볼트 → 썬더와 같은 스킬트리는 가능하지만, 썬더 → 스파크나 라이트닝 볼트 → 스파크 → 힐링 → 썬더와 같은 스킬트리는 불가능합니다.
> 선행 스킬 순서 skill과 유저들이 만든 스킬트리1를 담은 배열 skill_trees가 매개변수로 주어질 때, 가능한 스킬트리 개수를 return 하는 solution 함수를 작성해주세요.

## 제한 조건
> 스킬은 알파벳 대문자로 표기하며, 모든 문자열은 알파벳 대문자로만 이루어져 있습니다.
> 스킬 순서와 스킬트리는 문자열로 표기합니다. 
> 예를 들어, C → B → D 라면 CBD로 표기합니다.
> 선행 스킬 순서 skill의 길이는 1 이상 26 이하이며, 스킬은 중복해 주어지지 않습니다.
> skill_trees는 길이 1 이상 20 이하인 배열입니다.
> skill_trees의 원소는 스킬을 나타내는 문자열입니다.
> skill_trees의 원소는 길이가 2 이상 26 이하인 문자열이며, 스킬이 중복해 주어지지 않습니다.

## 입출력 예

| skill | skill_trees | return |
|:---:|:---:|:---:|
|"CBD"|["BACDE", "CBADF", "AECB", "BDA"]|2|

##### 입출력 예 설명
***

| skill | explaination |
|:---|:---|
|BACDE|B 스킬을 배우기 전에 C 스킬을 먼저 배워야 합니다. 불가능한 스킬트립니다.|
|CBADF|가능한 스킬트리입니다.|
|AECB|가능한 스킬트리입니다.|
|BDA|B 스킬을 배우기 전에 C 스킬을 먼저 배워야 합니다. 불가능한 스킬트리입니다.|

## Code
* Python3(파이썬)
```python
def solution(skill, skill_trees):
    answer = 0
    def check(skill, skill_tree):
        while skill_tree and skill:
            if skill_tree[0] not in skill:
                skill_tree.pop(0)
            elif skill_tree[0] == skill[0]:
                skill_tree.pop(0)
                skill.pop(0)
            else:
                return False
        return True
    for skill_tree in skill_trees:
        if check(list(skill), list(skill_tree)) == True:
            answer += 1
    return answer
```

## 코드 설명

**한줄설명**

skill_trees에 담겨있는 각각의 스킬트리의 순서가 맞는지를 확인하기 위해 for loop으로 각각의 스킬트리를 check function을 통해 확인합니다.

***

**추가설명**

1. 각 스킬 순서(skill) 과 배우고 싶은 스킬들(skill_tree)를 stack으로 바꾼뒤 def check(skill, skill_tree)로 보냅니다.
2. 스킬 순서(skill) 또는 배우고 싶은 스킬들(skill_tree) 둘중 하나가 없어질때 까지 스킬을 확인합니다.
3. 만약 배우고 싶은 스킬(skill_tree[0])이 스킬 순서(skill)에 없다면 언제든지 배울수 있는 스킬이므로 배우고 싶은 스킬 리스트(skill_tree)에서 제거합니다. 만약 배우고 싶은 스킬(skill_tree[0])이 스킬 순서(skill[0])와 일치 한다면 두개 모두 제거합니다. 나머지 경우는 배우고 싶은 스킬 순서(skill_tree)가 스킬 순서(skill)에 어긋나므로 False를 리턴합니다.
4. 순서가 어긋나지 않고 While loop를 끝까지 마친경우는 배우고 싶은 스킬 순서(skill_tree)가 올바른 경우이므로 True를 리턴합니다.
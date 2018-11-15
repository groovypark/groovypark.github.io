---
title: 자료구조 정리
description: 
categories: 
tags: CS
---

![자료구조](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS_gnyWTzgG_OzXuwizdNuOs5AsGhjnaBOIKPiccaoqmsqy2vTNpw)

## Array vs LinkedList

### Array

* index로 해당 원소에 접근  
  그렇기 때문에 찾고자 하는 원소의 인덱스 값을 알면 `Big-O(1)`
* 삭제 또는 삽입의 과정에서는 나머지 원소들의 인덱스를 `shift`해줘야 하므로 시간복잡도 O(n)

### LinkedList

* 각각의 원소들은 자기 자신 다음에 어떤 원소인지만을 기억
* 삭제와 삽입을 O(1)만에 해결하지만 원하는 위치에 하기 위해서 찾는 시간 `O(n)` 발생

## Stack and Queue

### Stack

* 선형 자료구조, `LIFO(Last In First Out)`

### Queue

* 선형 자료구조, `FIFO(First In First Out)

## Tree

비선형 자료구조. 계층적 관계를 표현하는 자료구조.

**트리를 구성하고 있는 용어**

* Node (노드): 트리를 구성하고 있는 각각의 요소
* Edge (간선): 트리를 구성하기 위해 노드와 노드를 연결하는 선
* Root Node (루트 노드): 트리 구조에서 최상위에 있는 노드
* Terminal Node (=leaf Node, 단말노드): 하위에 다른 노드가 연결되어 있지 않은 노드
* Internal Node (내부노드, 비단말 노드): 단말 노드를 제외한 모든 노드로 루트 노드를 포함

### Binary Tree (이진 트리)

루트 노드를 중심으로 두 개의 서브 트리로 나뉘어짐. 나뉘어진 두 서브 트리도 모두 이진 트리어야 함. 각 층별로 숫자를 매겨서 `Level(레벨)`이라고 함.

* Full Binary Tree (포화 이진 트리)  
  모든 레벨이 꽉 찬 이진 트리.
  ![포화 이진 트리](https://mblogthumb-phinf.pstatic.net/20150928_132/yms9713_1443418661736U88PO_PNG/%BD%BD%B6%F3%C0%CC%B5%E52.PNG?type=w2)
* Complete Binary Tree (완전 이진 트리)  
  마지막 레벨의 모든 노드가 자식노드를 2개를 가진 이진트리. 노드들은 왼쪽으로 채워져 있다.
  ![완전 이진 트리](https://mblogthumb-phinf.pstatic.net/20150928_235/yms9713_1443418651125F2jjR_PNG/%BD%BD%B6%F3%C0%CC%B5%E51.PNG?type=w2)


---
참고: [https://github.com/JaeYeopHan/Interview_Question_for_Beginner](https://github.com/JaeYeopHan/Interview_Question_for_Beginner){:target="_blank"}
---
title: 배열(Array) 리스트(Linked List) 장단점
description: 
categories: 
tags: Intern
---

![배열 리스트 비교](https://s3.ap-northeast-2.amazonaws.com/opentutorials-user-file/module/1335/2885.png)

## Array

![배열](https://t1.daumcdn.net/cfile/tistory/25299C37533F74A602)

* 크기가 정해져 있다
* index로 해당 원소에 접근
* 참조를 위한 추가적인 메모리 할당이 필요 없다.
* 찾고자 하는 원소의 인덱스 값을 알면 Big-O(1)
* 삭제 또는 삽입의 과정에서는 나머지 원소들의 인덱스를 shift해줘야 하므로 시간복잡도 O(n)


## LinkedList

![연결 리스트](https://t1.daumcdn.net/cfile/tistory/2351C835533F74C723)
![이중 연결 리스트](https://t1.daumcdn.net/cfile/tistory/2368CD35533F74C91A)


* 크기가 고정되어 있지 않다
* 각각의 원소들은 자기 자신 다음에 어떤 원소인지만을 기억
* 삭제와 삽입을 O(1)만에 해결하지만 원하는 위치에 하기 위해서 찾는 시간 O(n) 발생 (검색 성능 - 순차적으로 검색)
* 메모리의 재사용이 가능하다. 자료의 삭제시 해당 노드의 참조가 사라지므로 나중에 Garbage Collector에 의해 가용할 수 있는 메모리로 전환된다.
* 참조를 위한 추가 메모리 할당이 필요
* 단순 연결 리스트에서 사용하는 노드의 기본적인 구조
  ```java
  class Node {

    private Object data;
    private Node nextNode;

    Node(Object data){
      
          this.data = data;
          this.nextNode = null;
          
    }
  }
  ```

## 결론
* 저장할 데이터의 최대 개수가 정해져 있고 리스트의 중간에 데이터를 삽입, 삭제하는 작업이 많지 않으며 인덱스를 이용한 빠른 검색이 필요할 경우에는 배열을 사용하는게 효율적

* 저장될 데이터의 개수가 정해져 있지 않고 리스트의 중간에 데이터를 삽입하거나 삭제하는 작업이 많고 삽입, 삭제에 비해 특정 위치의 데이터를 검색하는 작업이 많지 않을 경우 연결 리스트를 사용하는게 효율적

---

참고: [개발이 하고 싶어요](https://hyeonstorage.tistory.com/258)
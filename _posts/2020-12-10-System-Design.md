---
title: 시스템 디자인 인터뷰(System Design Interview)
description: 
categories: 
tags: CS
---

![System Design](https://www.cronj.com/blog/wp-content/uploads/Artboard-10.png)

# 시스템 디자인
시스템 디자인이란, 말 그대로 주어진 서비스의 시스템을 어떻게 설계할 것인지 물어보는 질문이다. 너무 세부적으로 들어갈 필요는 없지만, 주어진 시스템이 대규모의 트래픽을 문제 없이 감당하기 위해서는 시스템의 전반적인 구조를 어떻게 잡아야 할지 명확한 근거를 가지고 말 할 수 있어야 한다.

### 시스템 디자인 인터뷰 예시

- Queue 시스템을 디자인해라
- bit.ly와 같은 URL 단축 서비스 설계해라
- Twitter를 디자인해봐라
- Elevator 시스템을 구현해봐라
- 우리 시스템을 네가 디자인해봐라


### 인터뷰에서 파악하고자하는 것

- 커뮤티케이션
- 문제 파악
- 디자인 설계

### 커뮤니케이션 능력

- 시스템의 주요 기능
- 제약 조건에 해당하는 중요한 숫자들 ( 처리할 데이터 양, 시스템의 규모, 메모리나 대기시간 )
- 처음부터 생각나는 것을 전부 솔루션에 집어넣으려 하기 보단, 최소한의 요구기능을 만족하는 솔루션을 먼저 제안한 후 피드백을 주고받으며 솔루션을 개선

따라서 충분한 질문을 통해 인터뷰어가 생각하는 진짜 문제를 파악하고 요구사항을 알아내야 함. interviewer들은 일방적으로 지원자를 평가하기보단 놓친 부분을 챙겨주고 필요한 조언을 해주며 지원자가 '어디까지 할 수 있을지'를 보는 것에 관심이 있다. 혼자서 문제를 풀기 위해 애를 쓰기보다 앞에 있는 interviewer와 함께 질문을 주고받으며 솔루션을 구체화해나가는 것이 더 좋은 답을 낼 수 있다.

## 인터뷰 문제 풀이 예시

### bit.ly 와 같은 단축 URL 주소 서비스를 어떻게 디자인할까요?

1. Use Cases
- url 단축. url => return shorter url
- 리다이렉션. short url => redirect original url
- 커스텀 url

2. Constraints
- 한 달에 생성되는 url 수
- 초당 요청

3. Abstract Design
- 서비스 나누기  
  url을 단축시키는 부분, 원래 url로 리다이렉션시키는 부분
- 데이터 스토리지  
  [hash table](https://groovypark.github.io/2018/05/18/CS%EA%B3%B5%EB%B6%80/) 사용. `hashed_url = convert_to_base62(original_url + random_salt)`

4. Understanding bottlenecks
- 트래픽보다는 데이터가 더 중요함

5. Scaling Design
- 시스템 확장. 더 높은 수준의 디자인.

---

찾아보니 주로 해외 취업 시 많이 하는 질문인 것 같음.  hiredintech 여기 사이트 강추!!

**참고**

[https://www.hiredintech.com/classrooms/system-design/lesson/52](https://www.hiredintech.com/classrooms/system-design/lesson/52)  
[https://modus.medium.com/what-the-is-systems-design-e005c1e9fef8](https://modus.medium.com/what-the-is-systems-design-e005c1e9fef8)  
[https://jchun.dev/2020/international-careers-07](https://jchun.dev/2020/international-careers-07)  
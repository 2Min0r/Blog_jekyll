---
layout: post
title: "프로그래머 Tip"
subtitle: "<프로그래머 첫걸음> 정리"
categories: Etc
date: 2020-01-11
background: '/img/bg-index.jpg'
---

## 프로그래머 Tip

<비전공자가 궁금해하는 프로그래머 첫걸음>을 보고 정리했습니다.

<br>

### 실무 코드를 작성하는 일반적인 원칙

Andy Hunt와 Dave Thomas의 <실용주의 프로그래머>(인사이트, 2005)는 코드의 품질을 향상시키기에 좋은 책

1. **코드 작성은 최후의 수단**

   해결할 문제가 일반적인 것이라면 누군가의 답을 가져다 쓸 수 있으므로, 검색부터 하자.

2. **DRY(Don't Repeat Yourself)**

   같은 코드가 반복될 경우에는 함수를 작성하자.

3. **독립성(orthogonality)**

   컴퓨터 공학에서 독립성이란 일종의 'decoupling'을 의미한다. 두 개 이상의 개체가 있고, 그 중 하나를 변경했을 때 다른 개체에 영향이 없다면 그들은 서로 독립적이다.

4. **데이터에는 한 가지 표현만**

   데이터를 여러 곳에 저장해서는 안된다. 중복된 데이터가 없도록 하며, 여러 곳에서 사용할 경우에는 전역변수를 만들어 사용해라. 더 좋은 방법은 파일이나 데이터베이스에 저장하고 사용하는 것이다.

5. **함수는 한 가지 일만**

   함수가 한 가지 일만 할 경우의 장점은 1) 함수이름만 봐도 함수의 동작을 알 수 있음 2) 문제가 있을 경우 함수를 빨리 찾아내고 분석할 수 있음

6. **프로그램이 오래 걸린다면 실수를 했는지 살펴보기**

   복잡하거나 거대한 데이터 세트를 다루는 것이 아닌데 프로그램이 오래 걸린다면, 잘못된 것이 있는지 의심해야 한다.

7. **처음부터 열심히**

   더 좋은 방법이 있다는 것이 떠오르면 바로 더 좋은 방법을 사용해라.

8. **관례 따르기**

   언어의 관례를 따르면 가독성이 좋아진다. PEP 8은 파이썬 코드 작성에 관한 가이드

9. **좋은 IDE 사용**

   자신과 잘 맞는 IDE를 사용해라. ex) 파이참

10. **로그**

    로그는 프로그램을 실행하는 동안 데이터를 기록한다. 디버그에도 도움이 된다. 파이썬에는 콘솔이나 파일에 로그를 기록하는 logging 모듈이 있다. 

11. **테스트**

    설계와 개발의 기준이 된 요건을 만족하는지, 모든 종류의 입력에 정확히 반응하는지, 납득할 수 있는 시간 안에 기능을 수행하는지, 충분히 사용하기 쉬운지, 의도한 환경에 설치하고 실행할 수 있는지, 이해 관계자들이 원하는 결과를 내는지 확인하는 것이 "테스트"이다.

    실무환경에서는 테스트가 반드시 필요하며, [unittest 모듈 사용법][https://docs.python.org/3/library/unittest.html]에서 파이썬 테스트모듈 사용법을 배울 수 있다.

12. **코드리뷰**

    코드를 읽고 피드백을 주는 것을 말하며, [Stack Exchange][http://codereview.stackexchange.com]에서 도움을 받을 수 있다.

13. **보안**

    사용자가 입력한 내용은 모두 악의적이라고 간주해라. 프로그램이 사용자의 입력을 받는다면 공격대상이 될 수 있으므로 **공격지점**을 최소화하는 것이 중요하다.

    - 기밀정보를 꼭 저장해야 하는 경우가 아니라면 저장하지 않기
    - 사용자에게는 최소한의 권한만 부여하기
    - 타사 라이브러리 사용을 최소화하기
    - 더는 사용하지 않는 기능은 제거하기 - 코드가 적으면 공격가능성도 적음

<br>

### 도움이 되는 사이트

1. **책**

   - <실용주의 프로그래머>(인사이트, 2005) - Andy Hunt, Dave Thomas
   - <GoF의 디자인패턴>(피어슨 에듀케이션 코리아, 2002) - erich Gamma, Richard Helm, Ralph Johnson, John Vlissides
   - < Code Complete>(정보문화사) - Steve McConnell
   - <컴파일러: 원리, 기법, 도구>(피어슨 에듀케이션 코리아, 2009) - Ravi Sethi, Monica S. Lam, Alfred Ah, Jeffrey Ultman
   - < Introduction to Algorithms>(한빛미디어, 2014) - MIT
   - < Problem Solving with Data Structures and Algorithms> - Bradley N. Miller, David L. Ranum

2. **온라인 강의**

   [참고][http://theselftaughtprogrammer.io/courses]

3. **뉴스**

   [해커뉴스][https://news.ycombinator.com]에서 사용자들이 올린 기술관련 뉴스사이트를 볼 수 있음

4. **글**

   [<ABC: Always Be Coding> - David Byttow][https://medium.com/always-be-coding/abc-always-be-coding-d5f8051afce2]



### 프로그래머 명언

1. 첫번째 버전이 동작한다고 해서 멈춰서는 안 되며, 코드가 아름다워 보일 때까지 계속 리팩토링하고 정제해야 한다.
2. 훌륭한 프로그래머는 돈이나 명성을 위해 프로그래밍하는 것이 아니라 프로그래밍 자체가 재미있어서 한다.
3. 함수는 한 가지 일만 해야 하고, 그 일을 잘 해야 한다.
4. 불필요하게 변수를 사용하지 않는다. 나중에 사용하려고 하는 데이터만 변수에 저장해야 한다.
5. 프로그래머의 자세
   - 만능 프로그래머가 되자!
     - 다양한 분야나 기술을 접하자. 진로를 잘못 선택해서 후회하지 말고, 다양한 경험을 하자. 만약 하나의 기술을 많이 사용할 때에는 다른 기술에서 얻었던 교훈은 잊지 말자.
   - 공부를 멈추지 말자!
     - 계속 코드를 리팩토링하고 정제하자. 그러면 모르는 부분을 알게 되고 아름다운 코드를 짤 수 있을 것이다. 발전하는 프로그래머가 되자.
   - 질문하고 찾아보자!
     - 막히면 혼자 끙끙 앓지 말고, 물어보고 검색하며 다른 사람의 도움을 받으며 성장하자.
6. 좋은 설계란 비용이 늘어나는 속도보다 가치가 늘어나는 속도가 빠른 설계이다.
7. 시를 쓰듯 코드를 쓰고 할 수 있는 한 가장 간결하게 만들어라.
8. 코드가 동작하지 않으면 말장난일 뿐이다.
9. 말만 늘어놓지 말고, 코드를 보여줘라
10. 미숙한 프로그래머와 훌륭한 프로그래머를 나누는 기준은 코드와 자료구조 중 무엇을 더 중시하는가에 달려있다. 미숙한 프로그래머는 코드에 신경을 쓰지만, 훌륭한 프로그래머는 자료구조와 그들의 관계에 신경을 쓴다.
11. 훌륭한 프로그래머와 미숙한 프로그래머의 차이는 문제가 발생했을 때 디버그하기 쉽도록 로그를 남기느냐 아니냐의 차이다.
12. 테스트하지 않은 코드는 깨진 코드이다.
13. 보안은 마음가짐이다.



[https://docs.python.org/3/library/unittest.html]: https://docs.python.org/3/library/unittest.html
[http://codereview.stackexchange.com]: http://codereview.stackexchange.com
[http://theselftaughtprogrammer.io/courses]: http://theselftaughtprogrammer.io/courses
[https://news.ycombinator.com]: https://news.ycombinator.com
[https://medium.com/always-be-coding/abc-always-be-coding-d5f8051afce2]: https://medium.com/always-be-coding/abc-always-be-coding-d5f8051afce2
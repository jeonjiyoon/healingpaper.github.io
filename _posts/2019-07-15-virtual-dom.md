---
title:  "Virtual DOM, 제대로 알기"
categories: [Web]
tags: [DOM, Virtual DOM, React]
author: Welin Hong
---
이번 포스트에서는 **Virtual DOM(가상돔)**에 대해 알아보려고 합니다. <br>
React나 Vue를 공부하면 처음 접하게 되는 개념이 있는데요. 바로 Virtual DOM입니다. 실제로 React나 Vue로 프로젝트를 진행하면서 이 개념을 많이 듣지만, 이 가상 돔이 정확히 어떤 것이고 어떤 장점을 가지고 있는지 모르는 경우가 많습니다. 저 또한 가상 돔이 페이지를 효율적으로 렌더링하는데 큰 도움을 주고 있다는 사실은 알았지만 딱 여기까지 였어요. 
그래서, 이번 포스트를 통해 모호하게 알고 있던 가상 돔을 제대로 소화하려고 합니다. <br>
아래와 같은 순서로 글을 진행하려고 합니다. (리액트 기준으로 설명이 진행됩니다.)<br>

- DOM이란?<br>
- Virtual DOM이란?<br>
- 왜 Virtual DOM이 필요한가요?<br>

---

## DOM이란?

Document Object Model.
DOM은 프로그래밍 언어가 document의 내용, 구조, 스타일 등을 조작할 수 있도록 해주는 인터페이스입니다. 예를 들어, JavaScript가 html(document)를 쉽게 조작할 수 있도록 해주는 인터페이스를 제공한다고 볼 수 있습니다.

![](/assets/images/welin/virtualdom/what_is_dom.png)

- DOM은 document를 object(객체)로 표현함으로서, 프로그래밍 언어가 document에 접근할 수 있도록 해줍니다.
- DOM에서는 document에 접근할 수 있는 메소드, 프로퍼티 등을 제공합니다. 
예를 들면, 특정한 엘리먼트의 객체를 획득할 수 있는 메소드를 제공합니다.

        document.getElementsByTagName('body')[0]
        document.getElementsByTagName('div')[0]
        document.getElementsByTagName('img')[0]

    또, 문서 내의 주요 엘리먼트에 접근할 수 있는 프로퍼티를 제공합니다.

        document.body // body 객체
        document.images // image 객체들의 리스트

---

## Virtual DOM이란?

가상 돔은 실제 돔과 비슷합니다. 쉽게 설명하면, 가상돔은 실제돔의 복사본이라고 생각하면 됩니다. 실제돔과의 차이는 가상돔은 메모리에만 저장되고 실제 화면에 출력되지 않는다는 점입니다. 

리액트의 가상돔은 실제돔처럼 행동하는 단순한 자바스크립트 객체(simple JavaScript objects)로 구성되어 있습니다. 그래서 가상돔을 업데이트 하는 것은 이 자바스크립트 객체를 수정하는 것을 의미합니다. 이 업데이트를 위해 필요한 연산들은 자바스크립트 엔진이 매우 빠르게 처리할 수 있습니다. 반면에 실제돔을 업데이트 하는 것은 브라우저에게 많은 연산 작업을 요구합니다. 이에 대한 내용은 아래에서 자세하게 살펴 보겠습니다. 

---

## 왜 Virtual DOM이 필요한가요?

이를 이해를 위해서는 먼저 브라우저의 Workflow에 대한 이해가 필요합니다. 
(브라우저의 Workflow는 [The one thing that no one properly explains about React - Why Virtual DOM](https://hashnode.com/post/the-one-thing-that-no-one-properly-explains-about-react-why-virtual-dom-cisczhfj41bmssp53mvfwmgrq)을 일부 번역했습니다.)

<**브라우저의 Workflow>**

![](/assets/images/welin/virtualdom/webkitflow.png)

**DOM 트리의 생성**

브라우저가 HTML파일을 받으면, 렌더 엔진은 파일을 파싱하고 노드의 DOM트리를 생성합니다. 이 노드는 HTLM 엘리먼트와 일대일 관계를 가지고 있습니다.

**렌더 트리의 생성**

CSS파일과 엘리먼트의 인라인 스타일은 파싱됩니다. 이 스타일 정보와 DOM 트리의 노드들로 새로운 트리인 렌더 트리가 생성됩니다.

**렌더 트리의 생성 - 비하인드**

- WebKit에서, 노드에 스타일을 입히는 과정을 "attachment"라고 합니다. DOM 트리의 모든 노드는 "attach" 메소드를 가지고 있습니다. 이 메소드는 스타일 정보를 계산하고, 렌더 객체(renderer)를 리턴합니다.
- **Attachment는 동기적인(synchronous) 작업입니다. DOM 트리에 노드를 추가하는 것은 새로운 노드의 "attach" 메소드를 호출하게 됩니다.**
- 렌더 트리를 만드는 것은 각 렌더 객체의 스타일 요소를 계산하는 것을 필요로 합니다.

**레이아웃**

렌더트리의 각 노드에게 스크린 어디에 표시되어야 할지에 대한 스크린의 좌표가 주어집니다.

**페인팅**

렌더트리를 돌면서 각 노드의 "paint()" 메소드가 호출되고, 컨텐츠가 화면에 표시됩니다.

위 과정에서 볼 수 있듯이, **돔을 수정하게 되면 렌더트리 생성, 모든 엘리먼트의 스타일 계산, 레이아웃, 그리고 페이팅까지의 과정들을 다시 수행하게 됩니다.**

그럼 가상돔을 사용하면 어떨까요?  
1. 돔을 수정하면, 전체 가상 돔이 업데이트 됩니다.
2. 이 가상 돔은 업데이트 하기 전의 가상 돔과 비교되고, 리액트는 무엇이 바뀌었는지 확인합니다.
3. 리액트는 바뀐 부분만 실제 돔에 업데이트 합니다. 

따라서 **렌더트리를 생성하거나 레이아웃을 조정하거나, 페인딩 하는 등의 연산을 많이 필요로 하는 과정들을 거치지 않게 됩니다.** 

자, 이제 왜 가상돔을 필요한지 아시겠나요?
가상돔을 사용하여 돔 렌더링시 거쳐야 하는 여러 과정들을 줄일 수 있습니다. 따라서 브라우저가 효율적으로 돔을 렌더링할 수 있게 됩니다.

추가적으로, 가상 돔이 매우 커지면, 이 또한 업데이트 하는 비용이 굉장히 큽니다. 이런 경우에는 리액트의 shouldComponentUpdate를 사용하여 꼭 업데이트 되야 하는 가상돔만 업데이트 되도록 해줘야 합니다. 

---

### 참고

- [The one thing that no one properly explains about React - Why Virtual DOM](https://hashnode.com/post/the-one-thing-that-no-one-properly-explains-about-react-why-virtual-dom-cisczhfj41bmssp53mvfwmgrq) ([번역본](https://velopert.com/3236))  
- [Virtual DOM and Internals](https://reactjs.org/docs/faq-internals.html)  
- [React and the Virtual DOM](https://www.youtube.com/watch?v=BYbgopx44vo&t=9s)  
- [The difference between Virtual DOM and DOM](https://reactkungfu.com/2015/10/the-difference-between-virtual-dom-and-dom/)

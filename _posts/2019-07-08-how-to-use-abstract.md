---
title: "Abstract Guide: 힐페 디자인챕터에서 Abstract 똑똑하게 사용하는 방법"
description:
categories: [Design]
tags: [Design, Abstract, Design System, Sketch]
author: Jane Jeon

---

안녕하세요. 힐링페이퍼의 프로덕트 디자이너 Jane입니다.

이번 글에서 힐페 디자인 챕터에서 Abstract를 어떻게 활용하고 있는 지를 기본 Abstract 사용법과 함께 공유하려고합니다.

저는 이전에 Abstract를 얕게 사용했었던 유저였는데요, 이전에 Abstract를 사용할 당시에는 디자인 시스템이 구축되지 않은 상태였고, 단지 파일의 버전 관리의 목적이 전부였습니다. 때문에 Abstract의 강력한 기능을 활용하는 법을 제대로 몰랐었고, 그동안 뭔가 알 듯하면서도 헷갈렸던 기능이 꽤나 많았습니다.*(이번에 Abstract를 제대로 도입하면서 알게된 기능이 많았어요.)* 이번 글을 통해 저와 같이 헤맸었던(?) 경험이 있었던 분, 그리고 팀 내에 앱스트랙트 도입을 고려 중인 분에게도 도움이 되길 바라봅니다!

​    

### **왜 Abstract를 도입했나요?**

------

현재 힐링페이퍼 디자인 챕터 내에 프로덕트 디자이너가 저를 포함해서 총 4명이 되었고 앞으로도 좋은 디자이너분들을 꾸준히 영입할 계획입니다. 인원이 늘어나고 있는 현 시점에서 가장 중요한 것은 디자이너 간의 디자인 동기화와 효율적인 협업입니다. 이는 프로덕트가 일관된 디자인을 유지할 수 있게 할 뿐만 아니라, 디자인 시스템 구축에 핵심적인 역할을 합니다.

때문에 스케치 파일의 히스토리 관리 및 파일 공유를 효율적으로 운용할 수 있게 도와주는 Abstract를 도입해 앞으로 더 많은 디자이너와 협업할 수 있도록 기반을 다지고, 시행착오를 거치면서 지금보다 더 좋은 방식을 찾아내려고 합니다.

  

  

### **👍 먼저 Abstract의 강점에 대해 알아봅시다.**

------

- **파일 히스토리를 남기기 위해 Save As로 스케치 파일을 증식하지 않아도 됩니다.**

  수십개의 파일을 따로 관리하지 않고 남겨둔 Commit 히스토리를 통해 언제든 이전 파일을 열어볼 수 있습니다.  

- **여러 사람이 함께 디자인 파일 버전 관리 및 공유가 편해집니다.**

  예) 휴가를 떠난 디자이너가 작업중이던 스케치 파일이 필요할 때 다음과 같은 상황을 겪지 않아도 됩니다.

  1. 공유 서버 사용 시

     서버에 업로드 된 파일을 다운로드 받고 Save As 로 final.0525수정중.sketch 등의 파일을 다시 생성해 나의 작업을 합니다. 이후 어디가 바뀌었는지 확인 후 누군가가 최종 파일로 합쳐서 서버에 다시 업로드를 하는 과정을 거칩니다. (이런 과정을 여러번 거치면 폴더 안은 다양한 파일명이 기입된 스케치 파일로 가득해집니다.)

  2. 공유 서버 또는 클라우드에 공유하지 않았을 경우

     휴가를 떠난 디자이너에게 연락을 취한 후 알려준 경로대로 타고타고 들어가서 파일을 슬랙으로/메일로 나에게 보낸 뒤 그 파일을 내려받아 작업합니다. (기본적으로 휴가를 떠난 디자이너에게 연락을 취해야합니다..😰)

- **스케치 파일이 한 곳에 정리되어 있기 때문에 어디서든 접근이 편리해집니다.**

  Abstract 자체가 스케치 파일의 공유 서버의 역할을 하기 때문에 인터넷만 된다면 어디서든 접근이 편리해집니다.  

  

### **📒 용어 설명 및 기본 사용법**

전체 맥락상 Abstract 내에서 사용하는 용어와 기본 사용법은 따로 페이지에서 소개해드리니 기본 사용법이 궁금하신 분들은 해당 링크를 참고해주세요🧐

------

<a href="https://healingpaper.github.io/design/2019/07/08/abstract-guide.html" target="blank">기본 용어 설명</a>

<a href="https://healingpaper.github.io/design/2019/07/08/abstract-guide.html#guide1" target="blank">Guide 1. Master에서 1개의 Branch 생성 후 Merge하기</a>

<a href="https://healingpaper.github.io/design/2019/07/08/abstract-guide.html#guide2" target="blank">Guide 2. 2개 이상의 Branch 생성 후 Update from Master 사용하기</a>

<a href="https://healingpaper.github.io/design/2019/07/08/abstract-guide.html#guide3" target="blank">Guide 3. Branch 중첩으로 생성하고. Archive 기능 활용하기</a>

<a href="https://healingpaper.github.io/design/2019/07/08/abstract-guide.html#guide4" target="blank">Guide 4. Library 기능 활용하기</a>

![img_main1](/assets/images/jane/abstract/main/img_main1.png)

앱스트랙트의 간단 구조도



### **🧐 힐페 디자인 챕터에서 앱스트랙트 똑똑하게 사용하는 방법!**

### **1. 스케치 파일 관리**

------

- 마스터 파일은 메뉴 단위별로 스케치 파일을 분리해 업로드합니다. (파일의 용량을 가볍게 유지하고, 충돌이 날 가능성을 낮춥니다.)

![img_main2](/assets/images/jane/abstract/main/img_main2.png)

마스터 파일 업로드 예시

- 스케치 파일 내에서는 Draft 페이지를 따로 생성해 확정되지 않았지만 필요한 디자인 산출물들을 따로 빼서 앱스트랙트 화면의 혼란을 줄입니다.
- 더불어 앱스트랙트는 스케치 파일의 레이어 순서대로 파일이 노출되므로 레이어 정렬을 하면 더 보기 좋습니다.

![img_main3](/assets/images/jane/abstract/main/img_main3.png)

스케치 파일 내 페이지 생성 예시

  

### **2. Commit과 Merge의 체계화*(Commit은 자주, Merge는 확실할 때)***

------

- **Commit**

  마이크로 단위로 업데이트 된 시안이 생길 때 마다 자주 히스토리를 쌓아줍니다.

  Commit 타이틀 네이밍 룰: [메뉴명_서브메뉴명_기능명_추가/수정내용]

  *(Commit 메세지는 '이런 것까지 적어야해?' 싶을 정도로 상세하게 적어 히스토리 추적을 용이하게 합니다.)*

- **Merge**

  시안에 대한 합의가 완전히 이루어지고 제플린으로 개발자와 시안이 공유되었을 때 파일을 Merge합니다.

  하나의 프로젝트 내에서 branch가 2개 이상 생성되어 있을 때는 반드시 Request Review 기능을 사용해 승인 절차를 거칩니다. (디자인 시안에 대한 리뷰보다는 충돌이 날 우려를 최대한 줄이기 위한 목적입니다.)

  

### **3. 라이브러리 활용을 통한 디자인 시스템 적용**

------

프로덕트의 일관된 디자인을 위해 디자인 시스템 파일을 업데이트할 수 있는 프로젝트를 따로 생성해 공통된 요소는 모두 Import - Override로 작업할 수 있게 환경을 만들어줍니다.

![img_main4](/assets/images/jane/abstract/main/img_main4.png)

심볼로 만들어 둔 컴포넌트 예시

![img_main5](/assets/images/jane/abstract/main/img_main5.png)

컬러 스타일 예시

(추후 Library 기능 활용을 효과적으로 할 수 있게 스케치 파일 관리하는 방법은 따로 자세히 다루겠습니다.)



### **🤓 추가로 알아두면 좋은 점들!**

------

- 모든 파일을 Abstract를 통해 열고 수정할 수 있도록 업무환경 세팅이 필요합니다.

  (폴더에 잠자고 있던 파일들을 Abstract 활용에 용이하게 정리하고 프로젝트에 업로드해주세요.)

- 아트보드 바깥의 단일 엘리먼트들도 모두 Abstract에서 감지하기 때문에 더미 작업물들은 모두 하나의 아트보드에 묶어서 관리하는 편이 좋습니다. (또는 스케치의 Page를 따로 생성해서 관리해도 좋습니다.)

- 아트보드의 배경을 지정하지 않으면 투명한 레이어로 보이므로 배경을 지정해주세요.

- Abstract에 아직 Commit하기 전인데 파일이 날아갔어요. 또는 Abstract 버그로 인해 파일을 찾을 수가 없어요. 하는 경우 파일 찾는 방법!

  Abstract에서 Branch를 생성하면 다음과 같은 경로에 파일이 생성되니 확인해주세요!

  1. shift + command + '.' 단축키를 통해 숨김파일 보기를 설정합니다.

  2. 다음과 같은 경로를 타고 이동해주세요.

     Machintosh HD > Users > 사용자명 > Library > Application Support > Abstract > Documents > com.bohemiancoding.sketch3 > Edits > 짜란

     

### **마치며**

------

이번 디자인챕터의 Abstract 도입은 단순히 버전 관리 툴을 효율적으로 사용한다는 개념에서 그치지 않고, 우리의 프로덕트 디자인의 히스토리를 통해 그것이 왜 변해왔는지, 앞으로 나아갈 방향은 어디인지에 대한 고민의 작은 시작이라고 생각합니다.

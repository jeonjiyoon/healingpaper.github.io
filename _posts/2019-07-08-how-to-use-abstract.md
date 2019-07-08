---
layout: post
title: Abstract Guide: 힐페 디자인챕터에서 Abstract 똑똑하게 사용하는 방법
categories: [Design]
tags: [Design, Abstract, Design System, Sketch]
author: Jane Jeon

---

# **Abstract Guide: 힐페 디자인챕터에서 Abstract 똑똑하게 사용하는 방법**

안녕하세요. 힐링페이퍼의 프로덕트 디자이너 전지윤입니다.

이번 글에서 힐페 디자인 챕터에서 Abstract를 어떻게 활용하고 있는 지를 기본 Abstract 사용법과 함께 공유하려고합니다.

저는 이전에 Abstract를 얕게 사용했었던 유저였는데요, 이전에 Abstract를 사용할 당시에는 디자인 시스템이 구축되지 않은 상태였고, 단지 파일의 버전 관리의 목적이 전부였습니다. 때문에 Abstract의 강력한 기능을 활용하는 법을 제대로 몰랐었고, 그동안 뭔가 알 듯하면서도 헷갈렸던 기능이 꽤나 많았습니다.*(이번에 Abstract를 제대로 도입하면서 알게된 기능이 많았어요.)* 이번 글을 통해 저와 같이 헤맸었던(?) 경험이 있었던 분, 그리고 팀 내에 앱스트랙트 도입을 고려 중인 분에게도 도움이 되길 바라봅니다!



### 왜 Abstract를 도입했나요?

------

현재 힐링페이퍼 디자인 챕터 내에 프로덕트 디자이너가 저를 포함해서 총 4명이 되었고 앞으로도 좋은 디자이너분들을 꾸준히 영입할 계획입니다. 인원이 늘어나고 있는 현 시점에서 가장 중요한 것은 디자이너 간의 디자인 동기화와 효율적인 협업입니다. 이는 프로덕트가 일관된 디자인을 유지할 수 있게 할 뿐만 아니라, 디자인 시스템 구축에 핵심적인 역할을 합니다.

때문에 스케치 파일의 히스토리 관리 및 파일 공유를 효율적으로 운용할 수 있게 도와주는 Abstract를 도입해 앞으로 더 많은 디자이너와 협업할 수 있도록 기반을 다지고, 시행착오를 거치면서 지금보다 더 좋은 방식을 찾아내려고 합니다.





### 👍 먼저 Abstract의 강점에 대해 알아봅시다.

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



### 📝 기본 용어 설명

------

- **Master**

  '진짜진짜 최종 파일'을 말합니다.

  각 프로젝트마다 Master 파일을 기준으로 디자인 파일의 버전 관리를 실행합니다.

  (Master 파일은 여러개여도 무관합니다.)

- **Branch**

  Master 파일로부터 갈라진 일종의 평행우주 개념입니다.

  단어 뜻 그대로 Master 파일에서 '가지를 치는' 기능으로 기존 스케치에서 Save As로 사본을 만드는 것과 유사합니다. Branch 파일을 만들면 Master 파일은 그대로 유지된 채로 생성한 Branch 파일에서 시안을 수정할 수 있습니다.

  (Branch는 중첩해서 계속 만들 수 있습니다.)

- **Commit**

  Branch에서 업데이트된 내용을 '확정(Super Save)'하는 기능입니다.

  Commit을 하게되면 Branch의 업데이트 내용이 Commit 히스토리에 메세지와 함께 쌓이게 됩니다.

  (추후 이전 시안으로 되돌아 갈 수 있게 히스토리를 자주 남겨주세요!)

- **Restore Commit**

  해당 Commit의 지점으로 되돌리고 싶을 때, Branch의 Commit 리스트를 눌러보면 우측에 시계 아이콘을 눌러 원복할 수 있습니다.

  ![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-e7fbd9c6-4c85-4796-a4f0-54c4b071e544.png)

- **Merge**

  생성한 여러개의 Branch 중 합의된 시안을 Merge하면 해당 Branch의 업데이트 내용이 Master 파일에 합쳐지게 됩니다.

- **Archive**

  생성한 Branch 파일을 Master에 Merge하지 않지만 삭제하기에는 남겨둘 리소스들이 발생하는 경우가 생깁니다. 이 때 Archive 기능으로 파일을 보관했다가 필요할 때 다시 꺼내쓸 수 있는 기능입니다.

- **Resolve Confilcts**

  동일한 파일을 수정하고 Merge하게 될 때 충돌이 나는 경우가 발생합니다. 이 때 Resolve Confilcts 기능을 통해 충돌이 난 페이지를 확인하고 어떤 파일을 Master로 할 지 선택할 수 있습니다.

  ![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-aa4421fe-e538-45d8-93f9-60440958bb31.png)

  Merge 할 당시 충돌이 날 경우 등장하는 Resolve Confilcts 페이지

  

- **Open Untracked**

  Master 파일에도 영향을 받지 않고, Branch도 생성하지 않은 채로 파일을 열게 되는 방식입니다.

  수정할 내용은 없으나 파일을 열어볼 필요가 있을 때 주로 사용하게 됩니다.

  (해당 기능을 활용해 파일을 열게되면 Commit을 할 수 없으니 주의해주세요. 가끔 Untracked로 열었다가 한참 수정한 뒤에 깨닫게 되면 다시 Branch파일에 옮기는 작업이 필요할 수 있어요..!)

  ![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-86c72d20-fb37-46a8-901c-674c4b3eb950.png)

  Open Untracked로 스케치 파일을 열었을 때 하단 상태바

  

- **Replace**

  많은 Commit 히스토리가 쌓여있는 시점에서 업로드한 파일을 교체하고 싶을 때, Replace 기능을 활용해 파일을 업로드하면 아래 히스토리는 그대로 유지되고, 파일을 교체할 수 있습니다.

  ![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-fe6e6fe3-762e-461c-b5ea-0a4a67d95e34.png)

- **Update from master**

  다수의 Branch 중 1개의 Branch를 Master로 Merge했을 때, 이전에 생성한 Branch의 Master 또한 변경이 되므로 가장 최근의 Master 파일로 다시 업데이트하는 액션을 취하게 됩니다.

  이 때 Update from master 기능을 실행하면 Commit을 통해 다른 Branch에서 업데이트한 내용을 추가할 수 있습니다.

- **Collections**

  업로드한 시안을 Collection에 추가하면 무수히 많은 페이지 중 내가 보여주고 싶은 페이지만 정리해둘 수 있습니다.

- **Library**

  파일을 Library 파일로 전환하면 타 프로젝트에서 해당 파일을 Import 할 수 있게 됩니다.

  예를 들어 강남언니 서비스의 프로젝트가 AOS, iOS 용으로 각각 분리되어 있을 때, 두 파일에서 공통으로 가져다 쓸 디자인 시스템 파일을 Library 파일로 만들고 타 프로젝트에서 Link해 사용이 가능합니다.

  Library 파일 또한 Master 파일을 가져다 사용하므로, 디자인 시스템의 버전 관리 및 적용을 효율적으로 할 수 있습니다.



### 📒 기본 사용법

------

[Guide 1. Master에서 1개의 Branch 생성 후 Merge하기](./Guide-1-Master-1-Branch-Merge-1dace133-358f-46d7-8ba8-bcb34b24272a.md)

[Guide 2. 2개 이상의 Branch 생성 후 Update from Master 사용하기](./Guide-2-2-Branch-Update-from-Master-b77a29ca-2a95-4788-8ce6-c7815da8e332.md)

[Guide 3. Branch 중첩으로 생성하고 Archive 기능 활용하기](./Guide-3-Branch-Archive-a79d74da-ba13-4791-9ee0-59c4972c9bbb.md)

[Guide 4. Library 기능 활용하기](./Guide-4-Library-90d6cd2b-e11d-4327-93c3-9f1cbdc0dfb0.md)

![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-ea1e167d-4fcd-494d-962f-89d38712bbdb.png)

앱스트랙트의 간단 구조도



### 🧐 힐페 디자인 챕터에서 앱스트랙트 똑똑하게 사용하는 방법!

### 1. 스케치 파일 관리

------

- 마스터 파일은 메뉴 단위별로 스케치 파일을 분리해 업로드합니다. (파일의 용량을 가볍게 유지하고, 충돌이 날 가능성을 낮춥니다.)

![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-f39813ec-3c77-4551-9191-60f9d574d3ce.png)

마스터 파일 업로드 예시

- 스케치 파일 내에서는 Draft 페이지를 따로 생성해 확정되지 않았지만 필요한 디자인 산출물들을 따로 빼서 앱스트랙트 화면의 혼란을 줄입니다.
- 더불어 앱스트랙트는 스케치 파일의 레이어 순서대로 파일이 노출되므로 레이어 정렬을 하면 더 보기 좋습니다.

![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-1cfc2ec3-423e-48d5-b251-d41b2809eeed.png)

스케치 파일 내 페이지 생성 예시



### 2. Commit과 Merge의 체계화*(Commit은 자주, Merge는 확실할 때)*

------

- **Commit**

  마이크로 단위로 업데이트 된 시안이 생길 때 마다 자주 히스토리를 쌓아줍니다.

  Commit 타이틀 네이밍 룰: [메뉴명_서브메뉴명_기능명_추가/수정내용]

  *(Commit 메세지는 '이런 것까지 적어야해?' 싶을 정도로 상세하게 적어 히스토리 추적을 용이하게 합니다.)*

- **Merge**

  시안에 대한 합의가 완전히 이루어지고 제플린으로 개발자와 시안이 공유되었을 때 파일을 Merge합니다.

  하나의 프로젝트 내에서 branch가 2개 이상 생성되어 있을 때는 반드시 Request Review 기능을 사용해 승인 절차를 거칩니다. (디자인 시안에 대한 리뷰보다는 충돌이 날 우려를 최대한 줄이기 위한 목적입니다.)

  

### 3. 라이브러리 활용을 통한 디자인 시스템 적용

------

프로덕트의 일관된 디자인을 위해 디자인 시스템 파일을 업데이트할 수 있는 프로젝트를 따로 생성해 공통된 요소는 모두 Import - Override로 작업할 수 있게 환경을 만들어줍니다.

![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-0ca0c7ce-0f53-4789-97ad-761b71336709.png)

심볼로 만들어 둔 컴포넌트 예시

![](/Users/jiyoonjeon/Downloads/Export-fb7183f3-1aaf-42a5-80c8-5309a476b693/Untitled-9d370b78-a02e-4101-9c5c-fd0bd007e58e.png)

컬러 스타일 예시

(추후 Library 기능 활용을 효과적으로 할 수 있게 스케치 파일 관리하는 방법은 따로 자세히 다루겠습니다.)



### 🤓 추가로 알아두면 좋은 점들!

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

     

### 마치며

------

이번 디자인챕터의 Abstract 도입은 단순히 버전 관리 툴을 효율적으로 사용한다는 개념에서 그치지 않고, 우리의 프로덕트 디자인의 히스토리를 통해 그것이 왜 변해왔는지, 앞으로 나아갈 방향은 어디인지에 대한 고민의 작은 시작이라고 생각합니다.
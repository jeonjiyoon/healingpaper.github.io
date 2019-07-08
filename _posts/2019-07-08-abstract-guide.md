---
title: "Abstract Guide: Abstract 기본 사용법"
categories: [Design]
tags: [Design, Abstract, Design System, Sketch]
author: Jane Jeon


---

<a href="https://healingpaper.github.io/design/2019/07/08/how-to-use-abstract.html" target="_blank">Abstract Guide: 힐페 디자인챕터에서 Abstract 똑똑하게 사용하는 방법</a> 에서 언급한 기본 사용법을 따로 글로 작성한 페이지입니다.

몇가지 케이스에 따라 기본 가이드를 작성해둔 것이니, Abstract를 처음 접하시는 분들은 아래 내용을 따라 테스트 작업을 해보시는 것을 추천드립니다. (참고로 2명 이상이 함께 테스트를 해보는 것이 Resolve Confilcts나 Review Request 등 다양한 상황을 경험하실 수 있어요.)

<div id="guide1">
  <h2 style="font-weight: bold;">
    Guide 1. Master에서 1개의 Branch 생성 후 Merge하기
  </h2>
</div>

​	![img_guide1-1](/assets/images/jane/abstract/guide1/img_guide1-1.png)

아래 내용을 도식화한 이미지입니다.

1. Master 파일을 생성합니다.

2. 수정하고 싶은 파일의 Branch를 생성합니다. (이 때, Branch명은 가이드를 따라 작성해주세요.)

3. 생성된 Branch에서 **'EDIT IN SKETCH'** 버튼으로 스케치 파일을 열어주세요.

4. 열린 스케치 파일에서 높은 기준을 추구한 디자인 작업을 불같이 해주세요! 🔥🔥

5. 업데이트 할 수정 사항이 생기면 파일을 저장합니다.

6. 저장 후 하단 앱스트랙트 상태바를 확인하면 **'COMMIT'**버튼이 활성화됩니다.

   ![img_guide1-2](/assets/images/jane/abstract/guide1/img_guide1-2.png)위와 같이 Commit Changes 버튼이 활성화 됩니다. 

     

7. 다시 Abstract 화면으로 돌아가 **'REQUEST REVIEW'** 버튼을 눌러 리뷰를 요청합니다.

   ![img_guide1-3](/assets/images/jane/abstract/guide1/img_guide1-3.png)

   리뷰를 요청하면 동료 디자이너가 👍또는 👎로 해당 브랜치를 머지해도 되는 지 피드백을 줍니다.  

     

8. 승인이 나면 상태가 'APPROVED'라고 수정되며 본 Branch에서 **'MERGE BRANCH'** 버튼을 눌러 파일을 업데이트하면 마스터 파일에 Merge됩니다.

   ![img_guide1-4](/assets/images/jane/abstract/guide1/img_guide1-4.png)

9. 다시 Master 파일을 확인하면 아래와 같이 히스토리가 남게 됩니다.

   ![img_guide1-5](/assets/images/jane/abstract/guide1/img_guide1-5.png)

<hr>

<div id="guide2">
  <h2 style="font-weight: bold;">
    Guide 2. 2개 이상의 Branch 생성 후 Update from Master 사용하기
  </h2>
</div>

![img_guide2-1](/assets/images/jane/abstract/guide2/img_guide2-1.png)

1. Guide 1과 동일하게 Branch를 생성해 작업을 진행합니다.

2. 브랜치가 2개 이상일 때 Branch A가 작업을 Merge하면 A의 수정사항까지 반영된 파일이 현재의 마스터 파일이 되면서 Branch B를 생성할 당시의 마스터 파일과 오차가 발생합니다.

3. 이 때 브랜치 B를 현재의 마스터 파일과 동기화하기 위해 '**UPDATE FROM MASTER**' 기능을 사용합니다.

   ![img_guide2-2](/assets/images/jane/abstract/guide2/img_guide2-2.png)

4. 만약 충돌이 날 경우 Resolve Conflicts 기능을 통해 어떤 파일을 최종으로 업데이트 할 지 선택해줍니다.

   ![img_guide2-3](/assets/images/jane/abstract/guide2/img_guide2-3.png)

   Update from Master 1/2: Resolve Conflicts 페이지 예시

     

5. 둘 중 하나의 파일을 선택하면 기존 Commit과 같은 방식으로 업데이트 히스토리를 남겨줍니다.

   ![img_guide2-4](/assets/images/jane/abstract/guide2/img_guide2-4.png)

   Update from Master 2/2: Commit 페이지 

     

6. 위 작업을 마친 후 다시 Guide 1과 같은 방법으로 Commit 히스토리를 남긴 후 Master로 Merge합니다.

<hr>

<div id="guide3">
  <h2 style="font-weight: bold;">
    Guide 3. Branch 중첩으로 생성하고 Archive 기능 활용하기
  </h2>
</div>

![img_guide3-1](/assets/images/jane/abstract/guide3/img_guide3-1.png)

1. Guide 1과 마찬가지로 Branch를 1개 생성합니다.
2. Branch 안에서 Sub Branch를 여러개 생성하고 각각의 파일에서 작업을 실행해주세요.
3. Sub Branch 중 하나를 선정해 Main Branch에 Merge해주세요.
4. 남은 Sub Branch 중 추후에 사용할 가능성이 있는 파일은 **Archive** 기능으로 따로 저장해줍니다.

![img_guide3-2](/assets/images/jane/abstract/guide3/img_guide3-2.png)

생성한 브랜치에서 마우스 우클릭으로 Archive

  

5. Branch - Archived 탭으로 진입하면 Archived 된 파일을 확인 할 수 있습니다.

![img_guide3-3](/assets/images/jane/abstract/guide3/img_guide3-3.png)

Archived List 페이지 예시(해당 리스트의 더보기 버튼을 클릭하면 UnArchive, New Branch, Delete 등 기능이 있습니다.)

<hr>

<div id="guide4">
  <h2 style="font-weight: bold;">
    Guide 4. Library 기능 활용하기
  </h2>
</div>

*힐페 디자인챕터에서는 Library 기능을 디자인 시스템을 관리하고 적용하는 목적으로 사용하기 때문에 Library화 할 파일의 컴포넌트화는 사전에 작업된 것으로 전제합니다.

1. 디자인 시스템 파일을 관리할 프로젝트를 생성해주세요.

2. Master 파일을 등록합니다.

3. 등록한 Master 파일을 마우스 우클릭해 **Use as Library** 버튼을 클릭해 Library 파일로 만들어줍니다.

   ![img_guide4-1](/assets/images/jane/abstract/guide4/img_guide4-1.png)

4. Library로 만들어진 파일은 보라색으로 컬러가 바뀌는 것을 확인할 수 있습니다.

   ![img_guide4-2](/assets/images/jane/abstract/guide4/img_guide4-2.png)

   Library 파일로 만들어진 상태

     

5. 위 Library 파일을 임포트할 프로젝트를 선택하고 Master 메뉴로 들어가 Library 파일을 Link해줍니다.

   ![img_guide4-3](/assets/images/jane/abstract/guide4/img_guide4-3.png)

   Master 파일에 Library를 Import

   ![img_guide4-4](/assets/images/jane/abstract/guide4/img_guide4-4.png)

   Link할 Library 파일을 선택해주세요.

     

6. Master 메뉴에서 Files 탭으로 들어가 확인해보면 Link된 Master 파일을 확인할 수 있습니다.

   ![img_guide4-5](/assets/images/jane/abstract/guide4/img_guide4-5.png)

7. 이제 이 스케치 파일을 열어 Import 탭을 열어보면 Link된 스케치 심볼과 스타일을 확인할 수 있습니다.

   ![img_guide4-6](/assets/images/jane/abstract/guide4/img_guide4-6.png)

8. 두 개 파일을 열어 Copy & Paste할 필요 없이 바로 Import할 수 있습니다👍👍
---
title:  "SwiftUI + Combine 핥아보기" 
categories: [iOS]   
tags: [SwiftUI, Combine, WWDC2019]   
author: Shirou Bae
---

# SwiftUI란?

> SwiftUI is a modern way to declare user interfaces for any Apple platform. Create beautiful, dynamic apps faster than ever before.

WWDC 2019에서 발표된 SwiftUI는 기존의 Storyboard와 Autolayout을 대체할 수 있는 UI 프레임워크 입니다.

발표 후 개발자들에게 WWDC 2019 중 가장 큰 환호를 들었다고 해도 과언이 아닌데요.

개인적으로 혁신이라 불릴만큼 매우 놀랍고 간편한 프레임 워크라고 생각합니다.  

일단 UI 프레임워크니 사진으로 먼저 만나보는게 좋겠죠(?)  

# SwiftUI 핥아보기

> 현재 SwiftUI를 사용하기 위해선 macOS 10.15 beta 와 Xcode 11 beta 버전이 필요합니다.

SwiftUI 기반의 프로젝트를 생성하는건 매우 간단합니다.

1. Xcode 11을 실행합니다.

2. Create a new Xcode project 버튼을 누릅니다.
![](/assets/images/shirou/swiftUiCombine/suc_1.JPG)

3. Single View App을 선택 후 Next 버튼을 누릅니다.
![](/assets/images/shirou/swiftUiCombine/2019-06-12__6-44f5b34e-0855-498b-b353-d4b1db418112.48.20.png)

4.  간단한 정보를 기입 후 Use SwiftUI 체크 확인 후 Next버튼을 누릅니다.
![](/assets/images/shirou/swiftUiCombine/2019-06-12__6-e79ce31f-b3ab-41aa-b42d-ad39b0bbe08c.48.51.png)

5.  그럼 짜잔~ 하고 처음 보는 화면이 반겨줍니다!  
기본적으로 ContentView가 생성되어있고 기존엔 볼 수 없었던 SceneDelegate 파일이 생겼네요.
프로젝트 생성 후 기본적으로 프리뷰가 Pause 되어 있는 상태이니 Resume를 눌러줍니다.
![](/assets/images/shirou/swiftUiCombine/2019-06-12__6-57ba88cd-2432-4d61-a19d-ef1fa9594a32.50.11.png)

6. 그 후 이렇게 프리뷰가 활성화되면서 Hello World가 떠있는 목업을 볼 수 있습니다.

아주 간단하죠?

해당 사진을 보면 기존 UIKit의 `UILabel` 와 같은 역할을 하는 `View`가 `Text`로 선언되어있는것을 볼 수 있습니다.
![](/assets/images/shirou/swiftUiCombine/2019-06-12__6-9b008285-d4ed-40e0-a616-036b2b11f8c6.50.58.png)

아무런 이미지나 assets에 추가후 `cmd` + `shift` + `l`  단축키를 입력하면 

다음과 같은 창이 뜹니다.  

![](/assets/images/shirou/swiftUiCombine/2019-06-12__7-4b3838bd-acc1-4101-ab09-d15587c6c9cb.07.24.png)

이 화면은 라이브러리라고 불리는듯합니다.

![](/assets/images/shirou/swiftUiCombine/2019-06-13__10-3ce4e788-b34f-4ec1-82e0-fa30f0fca91d.33.48.png)

라이브러리에서 코드나 프리뷰 화면으로 Drag & Drop 해서 `View` 를 추가할 수 있습니다.

정말 편리하죠?

이미지를 Text아래에 Drag & Drop 했더니 다음과 같이 `Image` `View`가 작성되었네요.

![](/assets/images/shirou/swiftUiCombine/2019-06-12__7-11decd1e-8ae0-484c-8a65-835ffbceccdc.11.59.png)

이미지가 너무 큼지막하니 좌측 코드에서 다음과 같이 수정 해보겠습니다.

```swift
VStack {
	Text("Hello World")
	Image("IMG_5021")
		.resizable()
		.aspectRatio(contentMode: .fit)
		.padding([.top, .bottom, .leading, .trailing], 16)
}
```

![](/assets/images/shirou/swiftUiCombine/2019-06-12__7-b644367b-1180-4fde-8790-526165a21aa8.24.31.png)

이 모든 스타일링을 체이닝으로 처리 할 수 있다니 정말 놀랍지 않습니까? 

**[대충 "애플... 압도적인 감사..!" 하는 짤]**

스타일링도 직접 입력하지 않고 라이브러리에서 Drag & Drop 으로 추가 할 수 있습니다.

여기서 해당 `View`를 기존 `UITableView` 형태로 만드는 법은 매우 쉽습니다!

좌측 코드를 다음과 같이  바꿔주기만하면...

```swift
List(0..<5) {_ in
	VStack {
		Text("Hello World")
		Image("IMG_5021")
			.resizable()
			.aspectRatio(contentMode: .fit)
			.padding([.top, .bottom, .leading, .trailing], 16)
	}
}
```

![](/assets/images/shirou/swiftUiCombine/2019-06-13__10-21a1d0f0-4f91-445d-afda-d09986db07cf.52.41.png)

이렇게 List 클로저하나 씌웠을 뿐인데 

기존에 DataSource나 Delegate 처리 없이 바로 리스트 형태의 뷰가 만들어 진걸 볼 수 있습니다.

프리뷰 화면에 프리뷰 버튼을 눌러주면 프리뷰가 활성화되어 스크롤도 해볼 수 있습니다.

기존의 ViewController의 개념은 사라지고 `View`와 `View` 간의 이동 및 상호작용 등이 이루어 진다는것을 알 수 있습니다.

더 자세한 `View` 레퍼런스는 [공식 문서](https://developer.apple.com/documentation/swiftui/views_and_controls)에서, 그에 상응하는 UIKIt 객체 비교는  [해당 git repo 섹션](https://github.com/SimpleBoilerplates/SwiftUI-Cheat-Sheet#uikit-equivalent-in-swiftui)에서 확인해주세요.

애플에서 제공하는 [Tutorials](https://developer.apple.com/tutorials/swiftui)도 보면 좋을듯합니다.   

# Combine 이란?

> Customize handling of asynchronous events by combining event-processing operators.

이렇게 멋진 UI 프레임 워크를 만들었는데 데이터 바인딩도 기존에 방식을 그대로 사용하지 않겠죠.

그래서 애플에선 `Combine`이라는 새로운 프레임워크를 공개했습니다.

일단 [공식 문서](https://developer.apple.com/documentation/combine)를 확인해 보면... 

토픽들을 살펴 보면 어디서 많이 본 친구 같죠..?

그렇습니다.  애플에서 비동기 리액티브 프로그래밍을 위한 프레임워크를 제공해주었습니다.

기존에 많이 사용하던 `RxSwift` 와 매우 유사하게 보이는데요.

 `RxCocoa` 옆엔 `RxSwift`가 있고 `SwiftUI` 옆엔 `Combine` 이 있는거죠!

저도 아직 까지는 `RxSwift`를 다뤄보셨다면 `Combine` 사용이 편할듯합니다.

RxSwift와 Combine의 비교는 [해당 블로그](https://medium.com/gett-engineering/rxswift-to-apples-combine-cheat-sheet-e9ce32b14c5b)를 확인해주세요.

# Combine 핥아보기

> 이 친구는 핥아보기엔 너무 큰 친구이긴 하지만...

Combine은 간단하게 프로젝트에서 SwiftUI와 함께 어떻게 사용되는지 포스팅 해보겠습니다. 

*github에 올라와있는 관련된 여러 repo들을 취합해서 **개인적으로** 가장 효율적이라고 생각하는 방식으로 진행하였습니다.*

### SwiftUI 기반 프로젝트를 하나 생성 해준 후

### 생성된 ContentView 안에 다음과 같은 body 코드를 작성해줍니다.

```swift
var body: some View {
    NavigationView {
        List(0..<5) { index in
            HStack {
                Image(systemName: "star")
                Text("Hello World")
             }
        }
        .navigationBarTitle(Text("Sample App"))
    }
}
```

![](/assets/images/shirou/swiftUiCombine/2019-06-20__5-1951069c-aed0-4996-a020-8a84e8f3505b.15.16.png){: width="50%"}

벌써 이렇게 아름다운(?) UI가 생성되었네요.

이제 여기서 View에서 받은 액션에 대한 상단의 네비 바 타이틀 변경과 Alert 팝업을 띄워 보겠습니다.

일단 View의 로직을 관리할 ViewModel을 만들어주겠습니다.

### ContentViewModel이라는 이름의 swift 파일 생성 후 다음과 같이 코드를 작성해줍니다.

각 라인의 설명은 코드내에 주석으로 처리 하였습니다.

```swift
import Combine
import SwiftUI

class ContentViewModel: BindableObject { // BindableObject 프로토콜을 implement 해줍니다.
    let didChange = PassthroughSubject<Void, Never>() // BindableOjbect 프로토콜안에 있는 필수 프로퍼티 입니다. 뷰에 적용되어야할 객체가 업데이트 될때 호출 해주면 됩니다.
    private var cancellables: [AnyCancellable] = [] // 기존 RxSwift의 DisposeBag과 같은 역할을 하는 녀석입니다. 해당 객체가 deInit될때 메모리 관리에 사용됩니다.

		// View의 Input Action 관련 코드입니다.
    enum Input {
        case didTap(index: Int)
    }
    
    func apply(_ input: Input) {
        switch input {
        case .didTap(let index):
            didTapIndexSubject.send(index)
        }
    }
    
		//ViewModel 내부에서 index관련 이벤트를 처리하기 위한 Subject입니다.
    private let didTapIndexSubject = PassthroughSubject<Int, Never>()
    
		// View에 바인딩 할 Output관련 코드입니다.
    struct Output {
        var isErrorShown = false 
        var labelText: String? 
    }
    
    private(set) var output = Output() {
        didSet {
            didChange.send(()) //Output 구조체를 초기화 해준 후 값이 변경 될때 마다 didChange Subject에 업데이트를 알립니다.
        }
    }
    
    init() {
        bindOutputs()
    }
    
		// 바인딩 관련 작업을 해주는 함수 입니다.
    private func bindOutputs() {
        
        let isError = didTapIndexSubject
            .map { $0 == 4 }// map을 사용하여 기존 Int형을 Bool형으로 변환해줍니다..
		        .share() // share을 사용해서 해당 Publisher를 공유해줍니다.
        
        let showError = isError.assign(to: \.output.isErrorShown, on: self) //isError Pulisher를 output.isErrorShown에 assign 해줍니다.

        let showSucessedMessage = isError.filter { !$0 } // isError의 이벤트 값이 true일 경우 무시하기 위해서 filter를 걸어줍니다.
            .zip(didTapIndexSubject.eraseToAnyPublisher()) // didTapIndexSubject를 Publisher로 변환 한뒤 zip을 사용하여 isError와 합쳐줍니다.
            .map { "Sucessed \($1)" } // map을 사용하여 기존 값을 String형의 값으로 변환해줍니다.
            .assign(to: \.output.labelText, on: self) // 변환 된 값을 output.labelText에 assign 해줍니다.

		// 해당 AnyCancellable 형의 프로퍼티들을 cancellables에 추가해줍니다.              
        cancellables += [
            showSucessedMessage,
            showError
        ]
    }
}
```

### 여기서 기존 ContentVIew코드를 다음과 같이 설정해줍니다.

각 라인의 설명은 코드내에 주석으로 처리 하였습니다.

```swift
struct ContentView : View {
    
    @ObjectBinding var viewModel: ContentViewModel //ObjectBiding 프로퍼티 Delegate를 사용하여 viewModel 를 생성해줍니다. 
    
    var body: some View {
        NavigationView {
            List(0..<5) { index in
                HStack {
                    Image(systemName: "star")
                    Text("Hello World")
                }
                .tapAction { // List내의 Row가 선택될때 호출됩니다. 기존 UITableViewDelegate의 didSelect 와 같다고 생각하시면됩니다.
                    self.viewModel.apply(.didTap(index: index)) //viewModel에 Input Action을 보냅니다.
                }
            }
            .presentation($viewModel.output.isErrorShown) { () -> Alert in // viewModel.output.isErrorShown 값이 변경될때 true일 경우
                Alert(title: Text("Error"), message: Text("Error")) // Alert View를 NavigationView에서 present 해줍니다.
            }
            .navigationBarTitle(Text(viewModel.output.labelText ?? "Sample App")) // viewModel.output.labelText에 있는 String값으로 네비게이션 값을 설정해줍니다.
        }
    }
}
```

이렇게 코드를 작성한 뒤 빌드를 해보면

다음과 같이 index가 0~3 까지의 Row 선택시 네비게이션 타이틀이 변경되는것을 볼 수 있고

index가 4 인 Row선택시 error Alert이 뜨는것을 볼 수 있습니다.

![](/assets/images/shirou/swiftUiCombine/2019-06-20__5-c755f588-a8f0-4894-bd61-741e5ddf59e4.55.55.png){: width="30%"}
![](/assets/images/shirou/swiftUiCombine/2019-06-20__5-a20d6952-5c6b-4def-84f2-a9180555a2f6.59.11.png){: width="30%"}
![](/assets/images/shirou/swiftUiCombine/2019-06-20__6-9c52122b-5380-41fb-a129-eeaa2abd2aef.00.02.png){: width="30%"}

최종 코드는 아래에서 확인 하실 수 있습니다.

### ContentView 최종코드

```swift
struct ContentView : View {
    
    @ObjectBinding var viewModel: ContentViewModel
    
    var body: some View {
        NavigationView {
            List(0..<5) { index in
                HStack {
                    Image(systemName: "star")
                    Text("Hello World")
                }
                .tapAction {
                    self.viewModel.apply(.didTap(index: index))
                }
            }
            .presentation($viewModel.output.isErrorShown) { () -> Alert in
                Alert(title: Text("Error"), message: Text("Error"))
            }
            .navigationBarTitle(Text(viewModel.output.labelText ?? "Sample App"))
        }
    }
}
```

### ContentViewModel 최종코드

```swift
class ContentViewModel: BindableObject {
    let didChange = PassthroughSubject<Void, Never>()
    private var cancellables: [AnyCancellable] = []

    enum Input {
        case didTap(index: Int)
    }
    
    func apply(_ input: Input) {
        switch input {
        case .didTap(let index):
            didTapIndexSubject.send(index)
        }
    }
    
    private let didTapIndexSubject = PassthroughSubject<Int, Never>()
    
    struct Output {
        var isErrorShown = false
        var labelText: String?
    }
    
    private(set) var output = Output() {
        didSet {
            didChange.send(())
        }
    }
    
    init() {
        bindOutputs()
    }
    
    private func bindOutputs() {
        
        let isError = didTapIndexSubject
            .map { index -> Bool in
                (index == 4)
            }.share()
        
        let showError = isError.assign(to: \.output.isErrorShown, on: self)

        let showSucessedMessage = isError.filter { !$0 }
            .zip(didTapIndexSubject.eraseToAnyPublisher())
            .map { _, index in
                "Sucessed \(index)"
            }.assign(to: \.output.labelText, on: self)
            
        cancellables += [
            showSucessedMessage,
            showError
        ]
    }
}
```
# 마치며...

이렇게 WWDC 2019에서 공개된 SwiftUi와 Combine 프레임워크를 살펴 보았습니다.

애플에서 Swift에 이렇게 많은 힘을 쏟아주는 것도 알 수 있어 정말 기뻤습니다.

이렇게 멋진 프레임워크들을 iOS 13 이상에서만 사용할 수 있어 실업무에는 적용하기에 아직 많이 이른감이 있다는 점이 아쉽습니다.

하지만 커뮤니티에서 떠돌고 있는 소문으로는 swift 5.1에서 추가된 [return 생략, 프로퍼티 Delegate](https://www.hackingwithswift.com/articles/182/whats-new-in-swift-5-1)등으로 인해 막아둔것이라 정식 버전 출시에는 iOS 13 미만의 버전에서도 사용할 수 있게 될 수도 있다는 얘기도 있습니다. 

(뭐 안되면 걍 2년동안 개인 프로젝트에서만 써야죠..)

아무튼 애플이 이와 같이 멋진 First-party 프레임 워크를 더욱 많이 만들어주고 개선 해주었으면 하는 마음입니다.

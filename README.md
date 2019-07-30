### 설치

```
$ bundle
```

### 실행 및 빌드
- `bundle exec jekyll serve`: Does the same thing except it rebuilds any time you make a change and runs a local web server at http://localhost:4000
(개발 모드에서는 jekyll serve를 이용하면 된다.)
- `bundle exec jekyll build`: Builds the site and outputs a static site to a directory called _site


### 글 작성
- 글을 작성하기 전, `Notion > 기술 Blog Drafts`에 글을 작성하고 피드백을 받은 후 `_post` 디렉토리에 추가합니다.
- `_post` 디렉토리에 아래의 형식을 참고하여 `yyyy-mm-dd-slug.md 파일 작성합니다
    - slug는 url의 일부로, 해당 포스트의 url은 `.../yyyy/mm/dd/slug`이 됩니다.
    <pre><code>
    title:  "자바스크립트란"
    categories: [web]
    tags: [javascript, object]
    author: Welin Hong
    
    [ 작성할 내용 ]
    </code></pre>
- 글 내용에 이미지가 있는 경우, assets > images > [작성자 폴더] > [해당글 폴더]를 생성하여 이 아래 이미지를 관리합니다.
작성자, 글 별로 이미지 파일을 관리합니다. 
- 이미지 등에 캡션을 달고 싶은 경우에는 아래와 같이 하면 됩니다.
    ```
    {% figure [caption: "캡션입니다"] [class:"my-class"] %}
    ![](image_path)
    {% endfigure %}
    ```

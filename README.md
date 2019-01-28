### 실행 및 빌드
- jekyll serve: Does the same thing except it rebuilds any time you make a change and runs a local web server at http://localhost:4000
(개발 모드에서는 jekyll serve를 이용하면 된다.)
- jekyll build: Builds the site and outputs a static site to a directory called _site


### 글 작성
- `_post` 디렉토리에 아래의 형식을 참고하여 `yyyy-mm-dd-slug.md 파일 추가
    - slug는 url의 일부로, 해당 포스트의 url은 `.../yyyy/mm/dd/slug`이 된다.
    <pre><code>
    layout: post
    title:  "자바스크립트란"
    categories: [web]
    tags: [javascript, object]
    author: Welin Hong
    
    [ 작성할 내용 ]
    </code></pre>

### TODO
[] 카테고리 layout

[x] 상세페이지에 댓글 추가

[] author

[] mobile responsive

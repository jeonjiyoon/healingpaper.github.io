### 실행 및 빌드
- jekyll serve: Does the same thing except it rebuilds any time you make a change and runs a local web server at http://localhost:4000
(개발 모드에서는 jekyll serve를 이용하면 된다.)
- jekyll build: Builds the site and outputs a static site to a directory called _site


### 글 작성
- 글을 작성하기 전, `Notion > 기술 Blog Drafts`에 글을 작성하고 피드백을 받은 후 `_post` 디렉토리에 추가.
- `_post` 디렉토리에 아래의 형식을 참고하여 `yyyy-mm-dd-slug.md 파일 작성
    - slug는 url의 일부로, 해당 포스트의 url은 `.../yyyy/mm/dd/slug`이 된다.
    <pre><code>
    title:  "자바스크립트란"
    categories: [web]
    tags: [javascript, object]
    author: Welin Hong
    
    [ 작성할 내용 ]
    </code></pre>
   

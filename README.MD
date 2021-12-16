# 블로그 만들기
웹사이트를 처음부터 만드는 것은 밥을 먹을때 쌀을 마트에서 사지 않고 직접 재배해 길러 요리해 먹는 것처럼 어렵다.  
때문에 쌀을 직접 재패하지 않고 마트에서 사는 것처럼 웹사이트도 중간 과정을 대신 해주는 것들을 이용하면 쉽게 웹사이트를 만들 수 있다.
- Github Repo를 이용하기
- Jekyll를 이용해 문서를 HTML로 바꾸기
- Jekyll Themes를 이용해 ppt 탬플릿을 사용하는 것처럼 적용하기
- Disqus를 이용해 댓글 구현하기
# 블로그 제작과정
1. Git & Github & Markdowm의 기본적인 사용법 익히기
1. Github Repo를 이용해 (username).github.io 이름의 Repo 생성하기
1. ruby와 Jekyll 설치하기 (window환경의 경우 https://rubyinstaller.org/downloads/의 ruby+devkit_installer와 cmd에서 gem install bundler jekyll를 이용)
1. Repo를 clone하고 clone한 디랙토리에 Jekyll 시작하기 (jekyll new . --force 이용)
1. bundle exec jekyll serve 실행 후 (cannot load such file -- webrick (LoadError) 발생 시 bundle add webrick 이용)
1. _post 폴더에 YYYY-MM-DD-TITLE.md 파일을 생성하고 Markdowm을 이용해 블로그에 게시할 내용 작성하기
1. Git commit과 push를 이용해 웹사이트에 적용시킬 파일 반영하기 (수정시킬 때마다 반복)
1. Project Gaia Themes 적용하기
1. Disqus를 이용해 댓글 기능 적용하기

### Project Gaia Themes 적용하기
Project Gaia의 경우 Themes 압축 파일에 Gemfile을 넣고 _posts에 있는 파일을 교채 후 _config.yml의 baseurl:를 주석처리하거나 공백("")으로 두면 잘 동작함
- _includes 안에 있는  html파일 수정
1. head.html을 수정해 블로그를 처음 열었을 때 보이는 글자들 수정하기
1. navbar.html를 수정해 우측 상단 메뉴를 열었을 떄 보이는 문구와 사진 교채하기

### Disqus를 이용해 댓글 기능 적용하기
1. https://blog.disqus.com/ 회원가입
1. create a new site 에서 원하는 site 이름을 정함 (이름은 고유아이디로 사용되기 때문에 잘 기억해두어야 함.)
1. Select a plan 에서 Basic 선택 
1. Install Disqus에서 Jekyll 선택 후 Configure 클릭
1. Configure Disqus에서 Website URL에 https://(username).github.io 입력 후 Next 클릭
1. Balanced와 Strict 중 취향에 맞게 선택
1. Install Disqus의 Install instructions에서 2 문단의 Universal Embed Code 선택
1. 1 문단의 코드 복사 후 _layouts 폴더의 post.html에 하단에 코드 추가
1. 복사한 코드 위에 {% if page.comments %} 와 html h2 태그로 Comments 추가
1. 복사한 코드 아래에 {% endif %} 추가
1. 주석 처리돈 코드를 추석 해제하고 그 위에 let PAGE_URL="{{site.url}}{{page.url}}" let PAGE_IDENTIFIER="{{page.url}}" 변수 추가
1. _config.yml에 아래의 내용과 url: 에 https://(username).github.io 추가
comment:
    provider: "disqus"
    disqus:
        shortname: "yureka-peurojegteu"
1. 댓글을 on off 할 수 있기 때문에 _posts에 댓글을 원하는 .md 파일이 있으면 comments: True 추가
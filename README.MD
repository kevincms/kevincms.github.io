# 블로그 만들기
웹사이트를 처음부터 만드는 것은 밥을 먹을때 쌀을 마트에서 사지 않고 직접 재배해 길러 요리해 먹는 것처럼 어렵다.  
때문에 쌀을 직접 재패하지 않고 마트에서 사는 것처럼 웹사이트도 중간 과정을 대신 해주는 것들을 이용하면 쉽게 웹사이트를 만들 수 있다.
- Github Repo를 이용하기
- Jekyll를 이용해 문서를 HTML로 바꾸기
- Jekyll Themes를 이용해 ppt 탬플릿을 사용하는 것처럼 적용하기
- Disqus를 이용해 댓글 구현하기
# 블로그 제작과정
1. Git & Github & Markdowm의 기본적인 사용법 익히기
1. Github Repo를 이용해 <username>.github.io 이름의 Repo 생성하기
1. ruby와 Jekyll 설치하기 (window환경의 경우 https://rubyinstaller.org/downloads/의 ruby+devkit_installer와 cmd에서 gem install bundler jekyll를 이용)
1. Repo를 clone하고 clone한 디랙토리에 Jekyll 시작하기 (jekyll new . --force 이용)
1. bundle exec jekyll serve 실행 후 (cannot load such file -- webrick (LoadError) 발생 시 bundle add webrick 이용)
1. _post 폴더에 YYYY-MM-DD-TITLE.md 파일을 생성하고 Markdowm을 이용해 블로그에 게시할 내용 작성하기
1. Git commit과 push를 이용해 웹사이트에 적용시킬 파일 반영하기 (수정시킬 때마다 반복)
1. Project Gaia Themes 적용하기 (Project Gaia의 경우 Themes 압축 파일에 Gemfile을 넣고 _posts에 있는 파일을 교채 후 _config.yml의 baseurl:를 주석처리하거나 공백으로 두면 잘 동작함)
1. Disqus를 이용해 댓글 기능 적용하기
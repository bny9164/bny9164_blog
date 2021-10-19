필요한 전역 모듈
hexo-cli

hexo 명령어
hexo clean : 배포 파일 모두 초기화(삭제)
hexo generate (g) : 배포 파일 생성
hexo deploy (d) : 실제 사이트에 배포
hexo new 'post명' : 새로운 post 생성
hexo new post 'post명' : 새로운 post 생성
hexo new draft 'draft명' : 새로운 초안 생성
hexo server : server 실행
hexo server --draft : 초안까지 포함해 server 실행
hexo publish 'draft명' : draft으로 작성한 파일 post로 변경

자세한 내용[공식문서] : https://hexo.io/ko/docs/commands

public 경로 => 실제 배포되는 파일들
source => local에 남아있는 파일

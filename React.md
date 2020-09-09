# React 공부하기
## React 실행전 설치해야할 항목
- nvm (버전 관리를 위한 것, 충돌을 피하기 위해 node.js 보다 먼저 설치하는 것이 좋다. 아직 window os는 나오지 않았다.)
  - $ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
  - $ nvm --version (터미널을 껐다가 켜서 잘설치되었는지 확인한다.)
- Node.js (lts는 신뢰도가 높은 버전/ current 버전은 최신 기능과 API 제공)
  - $ nvm install --lts
- yarn (조금 개선된 버전의 npm)
  - $ brew update
  - $ brew install yarn 
  - $ echo 'export PATH="$(yarn global bin):$PATH"' >> ~/.bash_profile
  - $ yarn --version
- Git bash

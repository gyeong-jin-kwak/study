# React Router
React SPA(Single Page Application) 구현에 가장 많이 사용 되는 'react-router-dom' 
기존 방식의 <a href=""></a>를 사용해서 url 변경 시 새로고침 되며 모든 페이지를 reload 하여 로드 시간이 걸리게 된다. 
React는 SPA 체제로 새로고침 대신 Router를 사용하여 변경된 소스만 바뀌도록 해주기 때문에 속도가 빠르다. 

## react-router, react-router-dom, react-router-native 의 차이
* react-router-dom: web에서 사용
* react-router-native: app에서 사용
* react-router: web과 app 둘 다 사용

## BrowserRouter 와 HashRouter 의 차이점

### BrowserRouter
* HTML5의 history API를 활용해서 UI를 업데이트 한다.
* 동적인 페이지에 적합하다. (서버에 있는 데이터들을 스크립트에 의해 가공 처리 한 후 생성되어 전달되는 웹페이지)
* 새로 고침 하면 경로를 찾지 못해서 에러가 난다.

### HashRouter
* URL의 hash를 활용한 라우터이다. 
* 주소에 #가 붙는다.
* 정적인 페이지에 적합하다. (미리 저장된 페이지가 그대로 보여지는 웹페이지)
* 검색 엔진으로 읽지 못한다. (그 이유 때문에 거의 사용하지 않는다.)
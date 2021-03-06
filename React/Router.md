# React Router
React SPA(Single Page Application) 구현에 가장 많이 사용 되는 'react-router-dom' 
기존 방식의 ```<a href=""></a>```를 사용해서 url 변경 시 새로고침 되며 모든 페이지를 reload 하여 로드 시간이 걸리게 된다. 
React는 SPA 체제로 새로고침 대신 Router를 사용하여 변경된 소스만 바뀌도록 해주기 때문에 속도가 빠르다. 

## react-router, react-router-dom, react-router-native 의 차이
* react-router-dom: web에서 사용
* react-router-native: app에서 사용
* react-router: web과 app 둘 다 사용

## BrowserRouter 와 HashRouter 의 차이점

### BrowserRouter
* HTML5의 history API를 활용해서 UI를 업데이트 한다.
* 동적인 페이지에 적합하다. (서버에 있는 데이터들을 스크립트에 의해 가공 처리 한 후 생성되어 전달되는 웹페이지)
* 새로 고침 하면 경로를 찾지 못해서 에러가 난다. (주소를 사용하여 페이지를 찾아갈 때에도 에러 발생)
    * 이를 해결하기 위해서는 서버에 추가적인 세팅이 필요하다. 페이지의 유무를 서버에 알려줘야 하며 서버 세팅시 검색엔진에 신경써야한다.
* github pages에서 설정하기 복잡하다. (배포가 복잡)

### HashRouter
* URL의 hash를 활용한 라우터이다. 
* 주소에 #가 붙는다.
* 정적인 페이지에 적합하다. (미리 저장된 페이지가 그대로 보여지는 웹페이지)
* 검색 엔진으로 읽지 못한다. #값 때문에 서버가 읽지 못하고 서버가 페이지의 유무를 알지 못하기 때문. (그 이유 때문에 거의 사용하지 않는다.)
* 새로고침 해도 에러가 나지 않는다.
* github pages에서 설정하기 간편하다. (배포가 간편)

**일반 프로젝트 작업을 할 때에는 BrowserRouter를 사용하는 편이 좋으며 (동적 페이지에 적합, 검색 엔진이 읽을 수 있음) 개인 포트폴리오를 git page에 배포해서 보여줄 때에는 hashRouter가 간편할 수 있다.**

```
현재는 대부분의 페이지가 동적 페이지로 구성되어 있다. 서비스 제공자 입장에서 정적인 페이지로 웹 페이지를 구성한다면 
상품을 등록하거나 제거할 떄 회원관리 할 때 등 그때마다 정적 웹 페이지를 제작해줘야 하지만 동적 페이지로 운영시 스크립트를 
작성하고 자동으로 페이지가 생성되게 해주면 된다. 
```

## URI에 관련하여
[url 공식문서](https://developer.mozilla.org/ko/docs/Web/HTTP/Basics_of_HTTP/Identifying_resources_on_the_Web)
* 리소스를 요청하는것 
* URI (Uniform Recource Idntifier)에 의해 식별됨
* URL은 URI의 한 종류 / URL ⊂ URI
* 프로토콜: http:// 보안 되기 전 단계, https:// 보안이 된 후
* 도메인: www.example.com
* 포트: 리소스 접근에 사용되는 기술적 문 
    * http는 80, https는 443을 사용하는데 다른 포트 사용시 꼭 입력! 
* 경로: 오늘날 대부분 물리적 실제 위치를 사용하지 않고 웹 서버에 의해 다뤄지는 추상화를 사용함
* 쿼리: 추가적 파라메터, &로 구분
* 프래그먼트: 북마크의 한 종류, 북마크된 지점에 위치한 컨텐츠를 보여주기 위한 방법, # 뒤의 부분은 서버에 전달되지 않는다.
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
  - $ yarn global add create-react-app (바로 리액트 프로젝트를 만들 수 있도록 도와준다.)
- Git bash

## React app 만들어보기
- $ npx create-react-app begin-react (메뉴bar - 이동 - 컴퓨터 - MacintoshHD - 사용자 - 집아이콘 경로에 만들어진다.)
- $ cd begin-react
- $ yarn start

## JSX 기본규칙 XML
XML(html) 형식의 코드를 사용하면 babel이 JSX(javascript) 형식으로 언어를 바꿔준다. 
- 태그는 꼭 닫혀있어야한다. (input이나 br태그 또한 꼭 닫아주어야한다.)
- 두개 이상의 태그는 꼭 <div></div>와 같은 태그로 감싸주어야한다. <> </> 태그로 감싸면 자동으로 Fragment 태그로 감싸지게 되는데 div보다 그게 나은 선택일 수도 있다.
- JSX 내에서 자바스크립트 면수는 {name}과 같이 {} 중괄호에 변수를 써준다. 
- JSX 내에서 style은 camelCase를 사용한다.
- JSX 내에서의 class는 'className'을 사용한다.
- 주석처리는 {/* 형태로 사용한다. */}
- 이미 { 중괄호로 열린 태그 안에서는 '//'형태의 주석처리도 가능하다 }

## props
```
* Hello.js *
function Hello(props){
  return <div>안녕하세요 {props.name}</div>
}

* App.js *
<Hello name="react" />
```
### props가 여러개일 경우
```
* Hello.js *
function Hello(props){
  return <div stlye={{props.color}}>안녕하세요 {props.name}</div>
}

function Hello({color, name}){
  return <div stlye={color}>안녕하세요 {name}</div>
}
```
### defaultProps 값 설정하기
```
* Hello.js *
funtion Hello({color, name}){
  return <div style={color}>안녕하세요, {props.name}</div>
  
  Hello.defaultProps = {
    name='이름없음',
  }
}

* App.js *
<>
  <Hello name="react" color="red" />
  <Hello color="pink" />
</>
```

### props.children - 감싸고 있는 태그가 있을 때 {children}을 사용해야 내부에 있는 태그들이 보인다.
```
* app.js *
<wapper>
  <Hello />
</wapper>

* wrapper.js *
fuction wrapper({children}){
  const style = {
    padding: '20px',
    border: '2px solid black',
  }
  
  return (
    <div style={style}>
      {chidren}
    </div>
  )
}
```
## 조건부 렌더링
```
* app.js *
<wrapper>
  <Hello name="react" color="red" isSpecial={true} />
  <Hello color="pink" />
</wrapper>
{/* 그냥 isSpecial만 사용해도 true를 반환한다. */}

* Hello.js *
function Hello({name, color, isSpecial}){
  return (
    <div style={color}>
      {isSpecial ? <b>*</b> : null} {/* 혹은 */}
      {isSpecial && <b>*</b>}
      안녕하세요 {name}
    </div>
  )
}
```
## useState (component 상태관리_hooks중 하나)
```
* Counter.js *
import React, { useState } from 'react';

function Counter(){
  const [number, setNumber] = useState(0);
  {/* [현재상태, setter함수] */}
  const increasNum = () => {
    setNumber(
      prevNum => prevNum + 1
    )
  }
  const decreaseNum = () => {
    prevNum => prevNum + 1
  }

  return(
    <h1>{number}</h1>
    <button onClick={increaseNum}>+1</button>
    <button onClick={decreaseNum}>-1</button>
  )
}
- import React, { useState } from 'react';
- setter함수란? 변수에 값을 집어넣는 함수 (반대개념. getter 함수)
- prevNum의 존재는 useState에서 파라미터 설정시 '이전 숫자'로 애초에 설계해둔것이다.
```

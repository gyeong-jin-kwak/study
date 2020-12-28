# Core Javascript

```
1. Data Types (데이터 타입)
2. Execution Context (실행 콘텍스트)
```

## Data Types
### Primitive Type (기본형)
1. Number
2. String
3. Boolean
4. null
5. undefined
![기본형 데이터 저장 방법](./images/javascript_primitive.jpg)
### Reference Type (참조형)
1. Object
    * Array
    * Function
    * RegExp
    ![참조형 데이터 저장 방법](./images/javascript_reference.jpg)
    * 한번 더 거쳐가는 형태
    * 참조가 0인 형대가 나타남
    * 같은 값은 오직 하나의 데이터만 차지함

## Execution Context (실행 콘텍스트)
1. 동일한 조건, 환경을 지니는 코드뭉치 = 함수, 전역공간 / 흐름상의 조건,환경정보
2. 환경정보를 담은 객체
3. call stack : 현재 어떤 함수가 동작하는지, 다음에 어떤 함수가 호출되어야 하는지에 대한 자료구조
![함수 실행순서](./images/javascript_stack.jpg)
4. inner
    * 순서 
        1. 변수 선언 `var a=1` 의 `var a`
        2. 함수선언 `outer()`
        3. 변수에 a에 1 할당 `var a=1`
        4. 함수 활성화 
    * VariableEnvironment 
        * 순간적인 값만 유지되는 형태
        * environmentRecord
        * outerEnvironmentReference
    * **LexicalEnvironment**
        * 이후의 값 변경을 계속 반영하는 형태
        * `environmentRecord` 현재 문맥의 식별자 정보 === Hoisting(끌어올리다)
            * 식별자를 맨 위로 끌어올림
        * `outerEnvironmentReference` 현재 문맥에 관련 있는 외부 식별자 정보
            * Scope Chain
                * scope: 변수의 유효 범위
                * chain: 실행 콘텍스트에 의해 결정
            * `inner`에서 선언한 변수는 `outer`로 갈 수 없음
            * `inner`의 변수는 오직 `inner` 안에서만 존재
            * `var a=2` 를 찾아야 할 때 `inner`에 없으면 `outer`에서 찾게 됨
    * ThisBinding
![변수, 함수 실행순서](./images/javascript_order.jpg)
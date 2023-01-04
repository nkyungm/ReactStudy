# 🥕ReactStudy
<details>
<summary>📙1장 리액트 시작</summary>
<div markdown="1">

## 📖1.1 왜 리액트 인가?.
### 💡 리액트 이해
  - 자바스크립트 라이브러리로 사용자 인터페이스를 만드는데 사용...
  - **컴포넌트(component)**
    - 특정 부분이 어떻게 생길지 정하는 선언체d
    - 재사용이 가능한 API로 수많은 기능들을 내장
    - 컴포넌트 하나에서 해당 컴포턴트의 생김새와 작동 방식 정의.
  - **렌더링**
    - 사용자 화면에 뷰를 보여주는 것...
  
  1️⃣ **초기 렌더링**
  - render 함수 : 컴포넌트가 어떻게 생겼는지 정의, 작동 정보 지닌 객체 반환...
  ```jsx
  render() { ... }
```
  ![image](https://user-images.githubusercontent.com/97418768/178123804-6d310f85-5cbb-4551-9cf2-4d3709b8df7b.png)
  
  - render 함수 실행 -> 컴포넌트 재귀적으로 렌더링 -> HTML 마크업 만듦 -> 실제 페이지의 DOM 요소 안에 주입 -> 이벤트 적용
  
  2️⃣ **조화 과정(업데이트)**
 1) 컴포넌트는 새로운 데이터를 가지고 render 함수 재호출(전체 UI를 Virtual Dom에 리렌더링)
 2) JS로 최소한의 연산으로 이전 Virtual Dom에 있던 내용과 현재 내용 비교
  ![image](https://user-images.githubusercontent.com/97418768/178123937-0c8fa9ed-04ec-493d-99d1-9ab1a94bd1f6.png)
  
 3) 바뀐 부분만 실제 DOM에 업데이트
  
![image](https://user-images.githubusercontent.com/97418768/178123952-3a48d238-1147-43f7-a023-b62baaabb2c0.png)

## 📖1.2 리액트의 특징
  ### 💡 Virtual DOM
  - **🔥DOM(Document Object Model)**
    - 객체로 문서 구조를 표현하는 방법(XML, HTML로 작성)
  ![image](https://user-images.githubusercontent.com/97418768/178124053-ee3bd821-876e-4179-9adf-cec3f079987e.png)
    - 문제점: 동적 UI에 최적화X
  
  - **🔥Virtual DOM**
    - DOM 업데이트 추상화한 자바스크립트 객체를 구성하여 사용 -> DOM 처리 횟수 최소화, 효율적 진행
    - 업데이트 3가지 절차 (조화과정)
    
  ### 💡 기타 특징
  - 리액트는 프레임워크X, 라이브러리O
    - 뷰만 신경 쓰는 라이브러리, 기타 기능 직접 구현
  - 다른 웹 프레임워크, 라이브러리 혼용 가능
  
## 📖1.3 작업 환경 설정
  ### 💡 Node.js와 npm
  - 설치: Windows
  
  https://nodejs.org/ko/download/
  
  ![image](https://user-images.githubusercontent.com/97418768/178124389-7730337c-7b45-4d98-ba5f-7997a5f14049.png)
  
  ### 💡 yarn
  - npm보다 더 빠르고 효율적인 캐시 시스템과 기타 부가 기능 제공
  
  `$ npm install --global yarn`
  
  ### 💡 에디터 설치
  - VS Code 설치
  
  https://code.visualstudio.com/Download
  
  ![image](https://user-images.githubusercontent.com/97418768/178139974-0a6e40c8-06bd-4a59-af9f-bd53c9695ff3.png)

  ### 💡 Git 설치
  - 형상 관리 도구(configuration Management Tool), 프로젝트 버전 관리 및 협업
  
  https://git-scm.com/download/
  
  ### 💡 create-react-app으로 프로젝트 생성하기
  - 프로젝트 작업 환경 구축해 주는 도구
  
  `$ yarn init`
  
  `$ yarn create react-app hello-react #yarn create react-app <프로젝트 이름>`
  
  - 리액트 개발 전용 서버 구동
  
  `$ cd hello-start`
  
  `$ yarn start #또는 npm start`
  
![image](https://user-images.githubusercontent.com/97418768/178141188-9525ba1c-ac19-4a60-a275-53c218864c07.png)

</div>
</details>
  
<details>
<summary>📙2장 JSX</summary>
<div markdown="2">
  
  ## 📖2.1 JSX란?
  - 자바스크립트의 확장 문법, XML과 유사
  - 브라우저가 실행되기 전에 코드가 번들링되는 과정에서 바벨을 사용해 일반 자바스크립트 형태의 코드로 변환
    - 바벨(Babel) : 다양한 종류의 버전의 브라우저에서 사용 가능하도록 코드 변환기
  
  ![image](https://user-images.githubusercontent.com/97418768/178141937-a42c703a-e420-4797-b8de-14489a571327.png)

  ## 📖2.2 JSX 문법
  ### 💡 감싸인 요소
  - 컴포넌트에 여러 요소가 있다면 반드시 부모 요소 하나로 감싸야 한다.
  - 컴포넌트 내부에 하나의 DOM 트리 구조 -> DOM에서 컴포넌트 변화 감지에 효율적 비교를 위해
```jsx
  function App() {
  return (
    <div>
      <h1>리액트 안녕?</h1>
      <h2>잘 작동하니?</h2>
    </div>
  );
}
```
### 💡 자바스크립트 표현
  - 자바스크립트 표현식 작성 가능 : {}로 감싸기
  ```JSX
  function App() {
  const name='리액트';
  return (
    <div>
      <h1>{name} 안녕?</h1>
      <h2>잘 작동하니?</h2>
    </div>
  );
}
  ```
 <details>
<summary>📌ES6의 cosnt와 let</summary>
<div markdown="1">
  
  - `var` : scope이 함수 단위 -> 함수를 빠져나오면 값이 달라짐
  
  **💡 `let`과 `const`는 scope이 블록 단위, 같은 블록 내부에서 중복 선언 불가능**
  - `const` : 한번 지정하고 나면 변경이 불가능한 상수를 선언할 때 사용하는 키워드
  - `let` : 동적인 값을 담을 수 있는 변수를 선언할 때 사용하는 키워드
  
  </div>
  </details>
  
 ### 💡 If문 대신 조건부 연산자
 - JSX 내부의 자바스크립트 표현식에서 if 문 사용X 
 
 **➡ JSX 밖에서 if문을 사용해 사전에 값을 설정, {}안에 조건부 연산자(삼항 연산자) 사용 가능**
 ```JSX
 function App() {
  const name='리액트';
  return (
    <div>
      {name==='리액트'?(
        <h1>리액트입니다.</h1>
      ):(
        <h2>리액트가 아닙니다.</h2>
      )}
    </div>
  );
}
```
  ### 💡 AND 연산자(&&)를 사용한 조건부 렌더링
 - 특정 조건 만족할 때만 렌더링
 - && 가능한 이유 : 리액트에서 false 렌더링할 때는 null과 동일하게 나타나지X
 - 0은 예외적으로 나타남
 ```JSX
  function App() {
  const name='리웩트';
  return <div>{name==='리액트' && <h1>리액트입니다.</h1>}</div>;
}
  ``` 
 ### 💡 undefined를 렌더링하지 않기
  - 어떤 값이 undefined인 경우
    - OR(||)연산자 사용
    - JSX 내부에서 undefined 렌더링은 가능
  ```JSX
  function App() {
 const name=undefined;
 return <div>{name||'리액트'}</div>;
}
  ```
 ### 💡 인라인 스타일링
  - DOM 요소에 스타일 적용할 때는 **객체 형태**로 넣어주어야 함
  ```JSX
  function App() {
  const name='리액트';
  return(
    <div
    style={{
      //background-color는 backgroundColor와 같이 -가 사라지고 카멜 표기법으로 작성
      backgroundColor:'black',
      color:'aqua',
      fontSize:'48px', //font-size -> fontSize
      fontWeight:'bold', //font-weight -> fontWeight
      padding:16 //단위를 생략하면 px로 지정 
    }}
    >{name}</div>
  )
}
  ```
 ### 💡 class 대신 className
  ```CSS
/* App.css */
.react{
  background: aqua;
  color: black;
  font-size: 48px;
  font-weight: bold;
  padding: 16px;
}
  ```
  ```JSX
  //App.js
  function App() {
  const name='리액트';
  return(
    <div className='react'>{name}</div>
  )
}
  ```
 ### 💡 주석
  - `{/* ... */}` 형식으로 작성
  ```JSX
  function App() {
  const name='리액트';
  return(
    <>
      {/* 주석은 이렇게 작성합니다. */}
      <div 
        className='react' //시작 태그를 여러 줄로 작성하면 여기에 주석 작성 가능
      >{name}</div>
      //하지만 이런 주석이나
      /* 이런 주석은 페이지에 그대로 나타나게 됩니다. */
      <input/>
    </>
  )
}
  ```
  ## 📖2.3 ESLint와 Prettier 적용하기
  - 💡 ESLint : 문법 검사 도구
  - 💡 Prettier : 코드 스타일 자동 정리 도구
    - 저장할 때 자동으로 코드 정리 : 파일 > 기본 설정 > 설정
  ![image](https://user-images.githubusercontent.com/97418768/178146180-fabed165-26ad-484f-b87b-2019e4ffe729.png)

  
  </div>
  </details>
  
  <details>
<summary>📙3장 컴포넌트</summary>
<div markdown="3">
  
## 📖3.1 클래스형 컴포넌트
- 컴포넌트 선언 방식 : 함수 컴포넌트, 클래스형 컴포넌트
  
🔥 함수 컴포넌트
  - 선언이 편함, 메모리 자원 적게 사용
  
🔥 클래스형 컴포넌트
  - state 기능 및 라이프 사이클 기능, 임의 메서드 정의 가능
```JSX
import { Component } from "react";
import "./App.css";

class App extends Component {
  render(){
    const name='react';
    return<div className='react'>{name}</div>;
  }
}
export default App;
  ```
  <details>
<summary>📌ES6의 클래스 문법</summary>
<div markdown="1">
  
  - prototype 대신 class 사용 가능
  ```JSX
  class Dog{
  constructor(name){
    this.name=name;
  }
  say(){
    console.log(this.name+': 멍멍');
  }
}

const dog=new Dog('흰둥이');
dog.say(); //흰둥이: 멍멍
```
  
  </div>
  </details>
  
## 📖3.2 첫 컴포넌트 생성
  ### 💡 src 디렉터리에 MyComponent.js 파일 생성
  ### 💡 코드 작성하기
  ```JSX
  const MyComponent=()=>{
    return <div>나의 새롭고 멋진 컴포넌트</div>;
}

export default MyComponent;
  ```
  
  <details>
<summary>📌ES6의 화살표 함수</summary>
<div markdown="1">
  
  - ES6 문법에서 함수를 표현하는 새로운 방식, 함수를 파라미터로 전달할 때 유용
  - 값을 연산하여 바로 반환할 때 가독성 높음
  - 함수 컴포넌트 선언할 때, function 키워드와 화살표 함수 문법 큰 차이X
  ```JSX
  setTimeout(function(){
    console.log('hello world');
},1000);

setTimeout(()=>{
    console.log('hello world');
},1000);
  ```
  
  </div>
  </details>
  
  <details>
<summary>📌Reactjs Code Snippet을 사용하여 코드 생성하기</summary>
<div markdown="2">
  
  - 에디터에서 rsc를 입력하고 `Enter` 누르기
  
  ![image](https://user-images.githubusercontent.com/97418768/178147814-6ee5adba-da6c-45a4-832a-21190e5fe839.png)

  </div>
  </details>
  
  ### 💡 모듈 내보내기 및 불러오기
  **- 모듈 내보내기(export)**
  - 다른 파일에서 이 파일을 import 할 때, MyComponent 클래스 불러오도록 설정
  ```JSX
  export default MyComponent;
  ```
  **- 모듈 불러오기(import)**
  - App 컴포넌트에서 MyComponent 컴포넌트 불러와서 사용
  ```JSX
  //App.js
import MyComponent from "./MyComponent"

const App=()=>{
  return <MyComponent/>;
};

export default App;
  ```
  
## 📖3.3 props
- properties를 줄인 표현으로 컴포넌트 속성을 설정할 때 사용하는 요소
- props 값은 해당 컴포넌트를 불러와 사용하는 부모 컴포넌트에서 설정 가능
### 💡 JSX 내부에서 props 렌더링
- props 값은 컴포넌트 함수의 파라미터로 받아와 사용 가능
- JSX 내부에서 {} 기호로 감싸줌
```JSX
const MyComponent = (props) => {
  return <div>안녕하세요, 제 이름은 {props.name}입니다.</div>;
};

export default MyComponent;
```
### 💡 컴포넌트를 사용할 때 props 값 지정하기
```JSX
  //App.js
import MyComponent from "./MyComponent";

const App = () => {
  return <MyComponent name="React" />;
};

export default App;
```
 ### 💡 props 기본값 설정: defaultProps
  ```JSX
  const MyComponent = (props) => {
  return <div>안녕하세요, 제 이름은 {props.name}입니다.</div>;
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

export default MyComponent;
```
### 💡 태그 사이의 내용을 보여 주는 children
  - 리액트 컴포넌트 태그 사이의 내용을 보여주는 `props.children`
 ```JSX
  //App.js
import MyComponent from "./MyComponent";

const App = () => {
  return <MyComponent>리액트</MyComponent>;
};

export default App;
```
```JSX
  const MyComponent = (props) => {
  return (
    <div>
      안녕하세요, 제 이름은 {props.name}입니다.
      <br />
      children 값은 {props.children}
      입니다.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

export default MyComponent;
```
 ### 💡 비구조화 할당 문법을 통해 props 내부 값 추출하기
  - ES6의 비구조화 할당 : 객체에서 값을 추출하는 문법
 ```JSX
  const MyComponent = ({ name, children }) => {
  return (
    <div>
      안녕하세요, 제 이름은 {name}입니다.
      <br />
      children 값은 {children}
      입니다.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

export default MyComponent;
```
 ### 💡 propTypes
  **🔥propTypes를 통한 props 검증**
  - 컴포넌트의 필수 props를 지정하거나 props의 타입(type) 지정하는 경우 propTypes 사용
 ```JSX
  import PropTypes from "prop-types";

const MyComponent = ({ name, children }) => {
  return (
    <div>
      안녕하세요, 제 이름은 {name}입니다.
      <br />
      children 값은 {children}
      입니다.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

MyComponent.propTypes = {
  name: PropTypes.string,
};

export default MyComponent;
```
**🔥 isRequired를 사용하여 필수 propTypes 설정**
  - propTypes를 지정하지 않았을 때 경고 메시지 띄워줌
 ```JSX
import PropTypes from "prop-types";

const MyComponent = ({ name, favoriteNumber, children }) => {
  return (
    <div>
      안녕하세요, 제 이름은 {name}입니다.
      <br />
      children 값은 {children}
      입니다.
      <br />
      제가 좋아하는 숫자는 {favoriteNumber}입니다.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "기본 이름",
};

MyComponent.propTypes = {
  name: PropTypes.string,
  favoriteNumber: PropTypes.number.isRequired,
};

export default MyComponent;

```
 ### 💡 클래스형 컴포넌트에서 props 사용하기
  - render 함수에서 this.props 조회
  - defaultProps, propTypes 방식 동일
 ```JSX
  import PropTypes from "prop-types";
import { Component } from "react";

class MyComponent extends Component {
  render(){
    const {name, favoriteNumber,children}=this.props; //비구조화 할당
    return (
      <div>
        안녕하세요, 제 이름은 {name}입니다.
        <br />
        children 값은 {children}
        입니다.
        <br />
        제가 좋아하는 숫자는 {favoriteNumber}입니다.
      </div>
    );
  }
}

MyComponent.defaultProps = {
  name: "기본 이름",
};

MyComponent.propTypes = {
  name: PropTypes.string,
  favoriteNumber: PropTypes.number.isRequired,
};

export default MyComponent;
```
## 📖3.4 state
  - 컴포넌트 내부에서 바뀔 수 있는 값
  - 클래스형 컴포넌트가 지니고 있는 state, 함수 컴포넌트에서 useState라는 함수를 통해 사용하는 state
 ### 💡 클래스형 컴포넌트의 state
  - `constructor` : 컴포넌트의 생성자 메서드, 반드시 `super(props)` 호출!, state 초깃값 지정 위함
  - 컴포넌트의 state는 **객체 형식**
  ```JSX
  import { Component } from "react";

class Counter extends Component {
  constructor(props) {
    super(props);
    //state의 초깃값 설정하기
    this.state = {
      number: 0,
    };
  }
  render() {
    const { number } = this.state; //state를 조회할 때는 this.state로 조회
    return (
      <div>
        <h1>{number}</h1>
        <button
          //onClick을 통해 버튼이 클릭되었을 때 호출할 함수를 지정
          onClick={() => { //이벤트로 설정할 함수를 넣어 줄 때는 화살표 함수 문법!
            //this.setState를 사용하여 state에 새로운 값을 넣을 수 있음
            this.setState({ number: number + 1 });
          }}
        >
          +1
        </button>
      </div>
    );
  }
}
export default Counter;
  ```
 ```JSX
  //App.js
import Counter from "./Counter";

const App = () => {
  return <Counter />;
};

export default App;
```
**🔥 state 객체 안에 여러 값이 있을 때**
  - state 안에 fixedNumber값 추가
  ```JSX
  import { Component } from "react";

class Counter extends Component {
  constructor(props) {
    super(props);
    //state의 초깃값 설정하기
    this.state = {
      number: 0,
      fixedNumber: 0,
    };
  }
  render() {
    const { number, fixedNumber } = this.state; //state를 조회할 때는 this.state로 조회
    return (
      <div>
        <h1>{number}</h1>
        <h2>바뀌지 않는 값: {fixedNumber}</h2>
        <button
          //onClick을 통해 버튼이 클릭되었을 때 호출할 함수를 지정
          onClick={() => {
            //this.setState를 사용하여 state에 새로운 값을 넣을 수 있음
            this.setState({ number: number + 1 });
          }}
        >
          +1
        </button>
      </div>
    );
  }
}
export default Counter;
```
 **🔥 state를 constructor에서 꺼내기**
  - constructor 메서드 선언하지 않고 state의 초깃값 설정 가능
  ```JSX
 import { Component } from "react";

class Counter extends Component {
  state = {
    number: 0,
    fixedNumber: 0,
  };
```
 **🔥 this.setState에 객체 대신 함수 인자 전달하기**
  - `prevState`:기존 상태, `props`: 현재 지니고 있는 props, 생략 가능
  ```JSX
  this.setState((prevState,props) => {
     return {
       // 업데이트하고 싶은 내용
     };
  });
  ```
  - 화살표 함수에서 바로 객체로 반환
  ```JSX
  onClick={() => {
            this.setState((prevState) => {
              return {
                number: prevState.number + 1,
              };
            });
            //위 코드와 아래 코드는 완전히 똑같은 기능
            //아래 코드는 함수에서 바로 객체를 반환한다는 의미
            this.setState((prevState) => ({
              number: prevState.number + 1,
            }));
          }}
   ```
 **🔥 this.setState가 끝난 후 특정 작업 실행하기**
  - setState의 두 번째 파라미터인 콜백(callback) 함수 사용
  ```JSX
  onClick={() => {
            this.setState(
              {
                number: number + 1,
              },
              () => {
                console.log("방금 setState가 호출되었습니다.");
                console.log(this.state);
              }
            );
          }}
  ```
 ### 💡 함수 컴포넌트에서 useState 사용하기
  **🔥 배열 비구조화 할당**
  - 객체 비구조화 할당과 비슷, 배열 안에 들어 있는 값을 쉽게 추출하기 위한 문법
  ```JSX
  const array=[1,2];
  const [one,two]=array;
  ```
  **🔥 useState 사용하기**
  - useState 함수 인자에는 상태의 초깃값 넣어줌(값 형태 자유)
  - 함수 호출 -> 배열 반환 [현재 상태,상태를 바꾸어 주는 함수(Setter 함수)]
  ```JSX
  import { useState } from "react";

const Say = () => {
  const [message, setMessage] = useState(""); //"" : 초깃값
  //[현재 상태,상태를 바꾸어 주는 함수(Setter 함수)] 
  const onClickEnter = () => setMessage("안녕하세요!");
  const onClickLeave = () => setMessage("안녕히 가세요!");

  return (
    <div>
      <button onClick={onClickEnter}>입장</button>
      <button onClick={onClickLeave}>퇴장</button>
      <h1>{message}</h1>
    </div>
  );
};

export default Say;
```
 ```JSX
 //App.js
import Say from "./Say";

const App = () => {
  return <Say />;
};

export default App;
```
**🔥 한 컴포넌트에 useState 여러 번 사용하기**
  ```JSX
  import { useState } from "react";

const Say = () => {
  const [message, setMessage] = useState("");
  const onClickEnter = () => setMessage("안녕하세요!");
  const onClickLeave = () => setMessage("안녕히 가세요!");

  const [color, setColor] = useState("black");

  return (
    <div>
      <button onClick={onClickEnter}>입장</button>
      <button onClick={onClickLeave}>퇴장</button>
      <h1 style={{ color }}>{message}</h1>
      <button style={{ color: "red" }} onClick={() => setColor("red")}>
        빨간색
      </button>
      <button style={{ color: "green" }} onClick={() => setColor("green")}>
        초록색
      </button>
      <button style={{ color: "blue" }} onClick={() => setColor("blue")}>
        파란색
      </button>
    </div>
  );
};

export default Say;
```
## 📖3.5 state를 사용할 때 주의 사항
 - state 값을 변경할 때
    - setState 사용(클래스형 컴포넌트)
    - useState를 통해 전달받은 세터 함수 사용 (함수 컴포넌트)
  </div>
  </details>
 
<details>
<summary>📙6장 컴포넌트 반복</summary>
<div markdown="4">

## 📖6.1 자바스크립트 배열의 map() 함수
  - 반복되는 컴포넌트 렌더링에 사용
  - 파라미터로 전달된 함수를 사용해서 배열 내 각 요소를 원하는 규칙에 따라 변환한 후 그 결과로 새로운 배열 생성
  ### 💡 map 문법
  `arr.map(callback,[thisArg])`
  
  - callback: 새로운 배열의 요소를 생성하는 함수, 파라미터 3가지
    - currentValue: 현재 처리 요소
    - index: 현재 처리 요소 index 값
    - array: 현재 처리 원본 배열
  - thisArg(선택 항목): callback 함수 내부에서 사용할 this 레퍼런스
  ```JSX
  const numbers=[1,2,3,4,5];
  const result=numbers.map(num=>num*num);
  console.log(result);
  ```
## 📖6.2 데이터 배열을 컴포넌트 배열로 변환하기
 ```JSX
  const IterationSample = () => {
  const names = ["눈사람", "얼음", "눈", "바람"];
  const nameList = names.map((name) => <li>{name}</li>);
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```
```JSX
  //App.js
import { Component } from "react";
import IterationSample from "./IterationSample"; //IterationSample 컴포넌트 불러와 렌더링

class App extends Component {
  render() {
    return <IterationSample />;
  }
}

export default App;
```
## 📖6.3 key
  - 데이터가 가진 고유의 값으로 설정
  - map 함수의 인자로 전달되는 함수 내부에서 컴포넌트 props 설정하듯 설정
  - Virtual Dom 비교하는 과정에서 key로 바로 변화 감지 가능
  ```JSX
  const IterationSample = () => {
  const names = ["눈사람", "얼음", "눈", "바람"];
  const nameList = names.map((name, index) => <li key={index}>{name}</li>);
  //고유의 값이 없을 때만 index를 key 값으로 설정
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```
## 📖6.4 응용(동적인 배열 렌더링)
  
### 💡 초기 상태 설정하기
  
  - useState를 사용해 상태 설정
  - 3가지 상태 : 데이터 배열, 텍스를 입력 input 상태, 배열에 새로운 항목 추가할 때 사용하는 고유 id 상태
  
  ```JSX
  import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([ //해당 객체는 문자열과 고유 id 값이 있음
    { id: 1, text: "눈사람" },
    { id: 2, text: "얼음" },
    { id: 3, text: "눈" },
    { id: 4, text: "바람" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); //새로운 항목을 추가할 때 사용할 id

  const nameList = names.map((name) => <li key={name.id}>{name.text}</li>);
  //map함수에서 name.id를 key 값으로 설정
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```
  
### 💡 데이터 추가 기능 구현하기
  
 - `concat` : 배열에 새 항목 추가(새로운 배열을 만들어줌)
  
  ```JSX
  import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "눈사람" },
    { id: 2, text: "얼음" },
    { id: 3, text: "눈" },
    { id: 4, text: "바람" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); //새로운 항목을 추가할 때 사용할 id

  const onChange = (e) => setInputText(e.target.value);
  const onClick = () => {
    const nextNames = names.concat({
      id: nextId, //nextId 값을 id로 설정하고
      text: inputText,
    });
    setNextId(nextId + 1); //nextId 값에 1을 더해준다
    setNames(nextNames); //names 값을 업데이트
    setInputText(""); //inputText를 지운다
  };
  const nameList = names.map((name) => <li key={name.id}>{name.text}</li>);
  //name.id를 key 값으로 설정
  return (
    <>
      <input value={inputText} onChange={onChange} />
      <button onClick={onClick}>추가</button>
      <ul>{nameList}</ul>
    </>
  );
};

export default IterationSample;
```
### 💡 데이터 제거 기능 구현하기
 - 더블클릭(`onDoubleClick`) -> 해당 항목 삭제
 - `fiter` : 불변성 유지하면서 배열의 특정 항목 삭제할 때 쓰는 배열의 내장함수
  ```JSX
  import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "눈사람" },
    { id: 2, text: "얼음" },
    { id: 3, text: "눈" },
    { id: 4, text: "바람" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); //새로운 항목을 추가할 때 사용할 id

  const onChange = (e) => setInputText(e.target.value);
  const onClick = () => {
    const nextNames = names.concat({
      id: nextId, //nextId 값을 id로 설정하고
      text: inputText,
    });
    setNextId(nextId + 1); //nextId 값에 1을 더해준다
    setNames(nextNames); //names 값을 업데이트
    setInputText(""); //inputText를 지운다
  };

  const onRemove = (id) => {
    //onRemove 함수를 만들어 각 li 요소 이벤트 등록
    const nextNames = names.filter((name) => name.id !== id);
    //name.id ===id인 항목만 삭제
    setNames(nextNames);
  };
  const nameList = names.map((name) => (
    <li key={name.id} onDoubleClick={() => onRemove(name.id)}>
      {name.text}
    </li>
  ));
  //name.id를 key 값으로 설정
  return (
    <>
      <input value={inputText} onChange={onChange} />
      <button onClick={onClick}>추가</button>
      <ul>{nameList}</ul>
    </>
  );
};

export default IterationSample;
```
  </div>
  </details>
  
<details>
<summary>📙8장 Hooks</summary>
<div markdown="5">

## 📖8.1 useState
  - 가장 기본적인 Hook, 함수 컴포넌트에서도 가변적인 상태 지닐 수 있음
  - 하나의 useState 함수는 하나의 상태 값만 관리 -> 컴포넌트에서 관리해야 할 상태 여러개면 여러개 useState 사용
## 📖8.2 useEffect
  - 리액트 컴포넌트가 렌더링될 때마다 특정 작업을 수행하도록 설정할 수 있는 Hook
  ```JSX
  import { useState, useEffect } from "react";

const Info = () => {
  const [name, setName] = useState("");
  const [nickname, setNickname] = useState("");
  useEffect(() => {
    console.log("렌더링이 완료되었습니다!");
    console.log({
      name,
      nickname,
    });
  });

  const onChangeName = (e) => {
    setName(e.target.value);
  };

  const onChangeNickname = (e) => {
    setNickname(e.target.value);
  };

  return (
    <div>
      <div>
        <input value={name} onChange={onChangeName} />
        <input value={nickname} onChange={onChangeNickname} />
      </div>
      <div>
        <b>이름:</b> {name}
      </div>
      <div>
        <b>닉네임:</b> {nickname}
      </div>
    </div>
  );
};

export default Info;
```
```JSX
import Info from "./Info";
import "./App.css";

const App = () => {
  return <Info />;
};

export default App;
```  
### 💡 마운트될 때만 실행하고 싶을 때
  - useEffect에서 설정한 함수를 컴포넌트가 화면에 맨 처음 렌더링될 때만 실행, 업데이트될 때는 실행X
  
  ➡ 함수의 두 번째 파라미터로 비어 있는 배열 넣어줌
 ```JSX
  useEffect(() => {
    console.log("렌더링이 완료되었습니다!");
  }, []);
  ```
### 💡 특정 값이 업데이트될 때만 실행하고 싶을 때
  - useEffect의 두 번째 파라미터로 전달되는 배열 안에 검사하고 싶은 값 넣어줌
 ```JSX
    useEffect(() => {
    console.log("렌더링이 완료되었습니다!");
  }, [name]);
  ```
## 📖8.3 useReducer
  - useState보다 더 다양한 컴포넌트 상황에 따라 다양한 상태를 다른 값으로 업데이트할 때 사용하는 Hook
  - 현재 상태, 업데이트르 위해 필요한 정보를 담은 액션(action) 값을 전달받아 새로운 상태를 반환하는 함수
  - 불변성 지켜줘야함!
```JSX
 function reducer(state,action){
  return{...}; //불변성을 지키면서 업데이트한 새로운 상태를 반환
 }
```
```JSX
//액션 값 : useReducer의 액션은 꼭 type 지닐 필요X, 객체가 아니라 문자열, 숫자 상관X
{
  type:'INCREMENT',
  //다른 값들이 필요하다면 추가로 들어감
}
```
 - `useReducer(리듀서 함수, 해당 리듀서의 기본값)`
 - 장점: 컴포넌트 업데이트 로직을 컴포넌트 바깥으로 빼낼 수 있음
```JSX
  import { useReducer } from "react";

function reducer(state, action) {
  //action.type에 따라 다른 작업 수행
  switch (action.type) {
    case "INCREMENT":
      return { value: state.value + 1 };
    case "DECREMENT":
      return { value: state.value - 1 };
    default:
      //아무것도 해당되지 않을 때 기존 상태 반환
      return state;
  }
}

const Counter = () => {
  const [state, dispatch] = useReducer(reducer, { value: 0 });
  //state: 현재 가리키고 있는 상태, dispatch: 액션 발생시키는 함수
  //dispatch(action) => 리듀서 함수 호출
  //useReducer(리듀서 함수, 해당 리듀서의 기본값)
  return (
    <div>
      <p>
        현재 카운터 값은 <b>{state.value}</b>입니다.
      </p>
      <button onClick={() => dispatch({ type: "INCREMENT" })}>+1</button>
      <button onClick={() => dispatch({ type: "DECREMENT" })}>-1</button>
    </div>
  );
};

export default Counter;
```
### 💡 useReducer로 인풋 상태 관리하기
  - setState를 해준 것과 유사한 방식으로 처리 가능
  - 인풋의 개수가 많아져도 코드를 짧고 깔끔하게 유지 가능
```JSX
import { useReducer } from "react";

function reducer(state, action) {
  return {
    ...state,
    [action.name]: action.value,
  };
}

const Info = () => {
  const [state, dispatch] = useReducer(reducer, {
    name: "",
    nickname: "",
  });
  const { name, nickname } = state;

  //이벤트 객체가 지니고 있는 e.target 값 자체를 액션 값으로 사용
  const onChange = (e) => {
    dispatch(e.target);
  };

  return (
    <div>
      <div>
        {/* input 태그에 name 값을 할당하고 e.target.name을 참조해 setState와 유사하게 처리 */}
        <input name="name" value={name} onChange={onChange} />
        <input name="nickname" value={nickname} onChange={onChange} />
      </div>
      <div>
        <b>이름:</b> {name}
      </div>
      <div>
        <b>닉네임:</b> {nickname}
      </div>
    </div>
  );
};

export default Info;
```
## 📖8.4 useMemo
 - 함수 컴포넌트 내부에서 발생하는 연산 최적화
 - 렌더링하는 과정에서 특정 값이 바뀌었을 때만 연산을 실행, 원하는 값이 바뀌지 않았다면 이전에 연산했던 결과를 다시 사용하는 방식
 ```JSX
import { useState, useMemo } from "react";

const getAverage = (numbers) => {
  console.log("평균값 계산 중...");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");

  const onChange = (e) => {
    setNumber(e.target.value);
  };
  const onInsert = () => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
  };

  const avg = useMemo(() => getAverage(list), [list]); 
  //list 배열의 내용이 바뀔 때만 getAverge 함수 호출

  return (
    <div>
      <input value={number} onChange={onChange} />
      <button onClick={onInsert}>등록</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>평균값:</b>
        {avg}
      </div>
    </div>
  );
};

export default Average;
```
## 📖8.5 useCallback
  - useMemo와 비슷, 렌더링 성능 최적화 상황에 사용
  - 만들어 놨던 함수 재사용 가능
  - `useCallback(생성하고 싶은 함수, 배열(어떤 값이 바뀌었을 때 함수를 새로 생성하는지 명시))`
```JSX
 const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");

  const onChange = useCallback((e) => {
    setNumber(e.target.value);
  }, []); //컴포넌트가 처음 렌더링될 때만 함수 생성, 렌더링될 때 만들었던 함수 재사용

  const onInsert = useCallback(() => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
  }, [number, list]); //number 혹은 list가 바뀌었을 때만 함수 생성, 아니면 함수 
  ```
## 📖8.6 useRef
  - 함수 컴포넌트에서 ref를 쉽게 사용 가능하게 함
  - useRef를 사용해 ref 설정 -> useRef를 통해 만든 객체 안의 current 값이 실제 엘리먼트 가리킴
 ```JSX
  import { useState, useMemo, useCallback, useRef } from "react";

const getAverage = (numbers) => {
  console.log("평균값 계산 중...");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");
  //ref를 위한 변수 선언
  const inputEl = useRef(null);

  const onChange = useCallback((e) => {
    setNumber(e.target.value);
  }, []); //컴포넌트가 처음 렌더링될 때만 함수 생성

  const onInsert = useCallback(() => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
    inputEl.current.focus(); //커서 이동을 원할 때,
  }, [number, list]); //number 혹은 list가 바뀌었을 때만 함수 생성

  const avg = useMemo(() => getAverage(list), [list]);
  //list 배열의 내용이 바뀔 때만 getAverge 함수 호출

  return (
    <div>
      <input value={number} onChange={onChange} ref={inputEl} />
      <button onClick={onInsert}>등록</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>평균값:</b>
        {avg}
      </div>
    </div>
  );
};

export default Average;
 ```
  
 <details>
<summary>📌ref통한 input 태그 커서/포커스 조정</summary>
<div markdown="1">
  
  - `ref` : DOM에 직접 접근해야할 때 사용
  - 직접 접근이 필요한 경우
    - input / textare 등에 커서 조정
    - DOM 의 크기를 가져와야 할 때
    - DOM 에서 스크롤 위치를 가져오거나 설정을 해야 할 때
    - 외부 라이브러리 (플레이어, 차트, 캐로절 등)을 사용 할 때
  
  </div>
  </details>
  
  ### 💡 로컬 변수 사용하기
   - 로컬 변수 : 렌더링과 상관없이 바뀔 수 있는 값
   - 렌더링과 관련되지 않은 값을 관리할 때 사용, ref 안의 값이 바뀌어도 컴포넌트가 렌더링X
  ```JSX
  import { useRef } from "react";

const RefSample = () => {
  const id = useRef(1);
  const setId = (n) => {
    id.current = n;
  };
  const printId = () => {
    console.log(id.current);
  };
  return <div>refsample</div>;
};

export default RefSample;
```
  </div>
  </details>

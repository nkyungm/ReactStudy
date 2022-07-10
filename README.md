# 🥕ReactStudy
<details>
<summary>📙1장 리액트 시작</summary>
<div markdown="1">

## 📖1.1 왜 리액트 인가?
### 💡 리액트 이해
  - 자바스크립트 라이브러리로 사용자 인터페이스를 만드는데 사용
  - **컴포넌트(component)**
    - 특정 부분이 어떻게 생길지 정하는 선언체
    - 재사용이 가능한 API로 수많은 기능들을 내장
    - 컴포넌트 하나에서 해당 컴포턴트의 생김새와 작동 방식 정의
  - **렌더링**
    - 사용자 화면에 뷰를 보여주는 것
  
  1️⃣ **초기 렌더링**
  - render 함수 : 컴포넌트가 어떻게 생겼는지 정의, 작동 정보 지닌 객체 반환
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
  
## 📖3.4 state
## 📖3.5 state를 사용할 때 주의 사항
  
  </div>
  </details>

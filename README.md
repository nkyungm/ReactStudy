# ๐ฅReactStudy
<details>
<summary>๐1์ฅ ๋ฆฌ์กํธ ์์</summary>
<div markdown="1">

## ๐1.1 ์ ๋ฆฌ์กํธ ์ธ๊ฐ?.
### ๐ก ๋ฆฌ์กํธ ์ดํด
  - ์๋ฐ์คํฌ๋ฆฝํธ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ก ์ฌ์ฉ์ ์ธํฐํ์ด์ค๋ฅผ ๋ง๋๋๋ฐ ์ฌ์ฉ
  - **์ปดํฌ๋ํธ(component)**
    - ํน์  ๋ถ๋ถ์ด ์ด๋ป๊ฒ ์๊ธธ์ง ์ ํ๋ ์ ์ธ์ฒด
    - ์ฌ์ฌ์ฉ์ด ๊ฐ๋ฅํ API๋ก ์๋ง์ ๊ธฐ๋ฅ๋ค์ ๋ด์ฅ
    - ์ปดํฌ๋ํธ ํ๋์์ ํด๋น ์ปดํฌํดํธ์ ์๊น์์ ์๋ ๋ฐฉ์ ์ ์
  - **๋ ๋๋ง**
    - ์ฌ์ฉ์ ํ๋ฉด์ ๋ทฐ๋ฅผ ๋ณด์ฌ์ฃผ๋ ๊ฒ..
  
  1๏ธโฃ **์ด๊ธฐ ๋ ๋๋ง**
  - render ํจ์ : ์ปดํฌ๋ํธ๊ฐ ์ด๋ป๊ฒ ์๊ฒผ๋์ง ์ ์, ์๋ ์ ๋ณด ์ง๋ ๊ฐ์ฒด ๋ฐํ
  ```jsx
  render() { ... }
```
  ![image](https://user-images.githubusercontent.com/97418768/178123804-6d310f85-5cbb-4551-9cf2-4d3709b8df7b.png)
  
  - render ํจ์ ์คํ -> ์ปดํฌ๋ํธ ์ฌ๊ท์ ์ผ๋ก ๋ ๋๋ง -> HTML ๋งํฌ์ ๋ง๋ฆ -> ์ค์  ํ์ด์ง์ DOM ์์ ์์ ์ฃผ์ -> ์ด๋ฒคํธ ์ ์ฉ
  
  2๏ธโฃ **์กฐํ ๊ณผ์ (์๋ฐ์ดํธ)**
 1) ์ปดํฌ๋ํธ๋ ์๋ก์ด ๋ฐ์ดํฐ๋ฅผ ๊ฐ์ง๊ณ  render ํจ์ ์ฌํธ์ถ(์ ์ฒด UI๋ฅผ Virtual Dom์ ๋ฆฌ๋ ๋๋ง)
 2) JS๋ก ์ต์ํ์ ์ฐ์ฐ์ผ๋ก ์ด์  Virtual Dom์ ์๋ ๋ด์ฉ๊ณผ ํ์ฌ ๋ด์ฉ ๋น๊ต.
  ![image](https://user-images.githubusercontent.com/97418768/178123937-0c8fa9ed-04ec-493d-99d1-9ab1a94bd1f6.png)
  
 3) ๋ฐ๋ ๋ถ๋ถ๋ง ์ค์  DOM์ ์๋ฐ์ดํธ.
  
![image](https://user-images.githubusercontent.com/97418768/178123952-3a48d238-1147-43f7-a023-b62baaabb2c0.png)

## ๐1.2 ๋ฆฌ์กํธ์ ํน์ง
  ### ๐ก Virtual DOM
  - **๐ฅDOM(Document Object Model)**
    - ๊ฐ์ฒด๋ก ๋ฌธ์ ๊ตฌ์กฐ๋ฅผ ํํํ๋ ๋ฐฉ๋ฒ(XML, HTML๋ก ์์ฑ)
  ![image](https://user-images.githubusercontent.com/97418768/178124053-ee3bd821-876e-4179-9adf-cec3f079987e.png)
    - ๋ฌธ์ ์ : ๋์  UI์ ์ต์ ํX
  
  - **๐ฅVirtual DOM**
    - DOM ์๋ฐ์ดํธ ์ถ์ํํ ์๋ฐ์คํฌ๋ฆฝํธ ๊ฐ์ฒด๋ฅผ ๊ตฌ์ฑํ์ฌ ์ฌ์ฉ -> DOM ์ฒ๋ฆฌ ํ์ ์ต์ํ, ํจ์จ์  ์งํ
    - ์๋ฐ์ดํธ 3๊ฐ์ง ์ ์ฐจ (์กฐํ๊ณผ์ )
    
  ### ๐ก ๊ธฐํ ํน์ง
  - ๋ฆฌ์กํธ๋ ํ๋ ์์ํฌX, ๋ผ์ด๋ธ๋ฌ๋ฆฌO
    - ๋ทฐ๋ง ์ ๊ฒฝ ์ฐ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ, ๊ธฐํ ๊ธฐ๋ฅ ์ง์  ๊ตฌํ
  - ๋ค๋ฅธ ์น ํ๋ ์์ํฌ, ๋ผ์ด๋ธ๋ฌ๋ฆฌ ํผ์ฉ ๊ฐ๋ฅ
  
## ๐1.3 ์์ ํ๊ฒฝ ์ค์ 
  ### ๐ก Node.js์ npm
  - ์ค์น: Windows
  
  https://nodejs.org/ko/download/
  
  ![image](https://user-images.githubusercontent.com/97418768/178124389-7730337c-7b45-4d98-ba5f-7997a5f14049.png)
  
  ### ๐ก yarn
  - npm๋ณด๋ค ๋ ๋น ๋ฅด๊ณ  ํจ์จ์ ์ธ ์บ์ ์์คํ๊ณผ ๊ธฐํ ๋ถ๊ฐ ๊ธฐ๋ฅ ์ ๊ณต
  
  `$ npm install --global yarn`
  
  ### ๐ก ์๋ํฐ ์ค์น
  - VS Code ์ค์น
  
  https://code.visualstudio.com/Download
  
  ![image](https://user-images.githubusercontent.com/97418768/178139974-0a6e40c8-06bd-4a59-af9f-bd53c9695ff3.png)

  ### ๐ก Git ์ค์น
  - ํ์ ๊ด๋ฆฌ ๋๊ตฌ(configuration Management Tool), ํ๋ก์ ํธ ๋ฒ์  ๊ด๋ฆฌ ๋ฐ ํ์
  
  https://git-scm.com/download/
  
  ### ๐ก create-react-app์ผ๋ก ํ๋ก์ ํธ ์์ฑํ๊ธฐ
  - ํ๋ก์ ํธ ์์ ํ๊ฒฝ ๊ตฌ์ถํด ์ฃผ๋ ๋๊ตฌ
  
  `$ yarn init`
  
  `$ yarn create react-app hello-react #yarn create react-app <ํ๋ก์ ํธ ์ด๋ฆ>`
  
  - ๋ฆฌ์กํธ ๊ฐ๋ฐ ์ ์ฉ ์๋ฒ ๊ตฌ๋
  
  `$ cd hello-start`
  
  `$ yarn start #๋๋ npm start`
  
![image](https://user-images.githubusercontent.com/97418768/178141188-9525ba1c-ac19-4a60-a275-53c218864c07.png)

</div>
</details>
  
<details>
<summary>๐2์ฅ JSX</summary>
<div markdown="2">
  
  ## ๐2.1 JSX๋?
  - ์๋ฐ์คํฌ๋ฆฝํธ์ ํ์ฅ ๋ฌธ๋ฒ, XML๊ณผ ์ ์ฌ
  - ๋ธ๋ผ์ฐ์ ๊ฐ ์คํ๋๊ธฐ ์ ์ ์ฝ๋๊ฐ ๋ฒ๋ค๋ง๋๋ ๊ณผ์ ์์ ๋ฐ๋ฒจ์ ์ฌ์ฉํด ์ผ๋ฐ ์๋ฐ์คํฌ๋ฆฝํธ ํํ์ ์ฝ๋๋ก ๋ณํ
    - ๋ฐ๋ฒจ(Babel) : ๋ค์ํ ์ข๋ฅ์ ๋ฒ์ ์ ๋ธ๋ผ์ฐ์ ์์ ์ฌ์ฉ ๊ฐ๋ฅํ๋๋ก ์ฝ๋ ๋ณํ๊ธฐ
  
  ![image](https://user-images.githubusercontent.com/97418768/178141937-a42c703a-e420-4797-b8de-14489a571327.png)

  ## ๐2.2 JSX ๋ฌธ๋ฒ
  ### ๐ก ๊ฐ์ธ์ธ ์์
  - ์ปดํฌ๋ํธ์ ์ฌ๋ฌ ์์๊ฐ ์๋ค๋ฉด ๋ฐ๋์ ๋ถ๋ชจ ์์ ํ๋๋ก ๊ฐ์ธ์ผ ํ๋ค.
  - ์ปดํฌ๋ํธ ๋ด๋ถ์ ํ๋์ DOM ํธ๋ฆฌ ๊ตฌ์กฐ -> DOM์์ ์ปดํฌ๋ํธ ๋ณํ ๊ฐ์ง์ ํจ์จ์  ๋น๊ต๋ฅผ ์ํด
```jsx
  function App() {
  return (
    <div>
      <h1>๋ฆฌ์กํธ ์๋?</h1>
      <h2>์ ์๋ํ๋?</h2>
    </div>
  );
}
```
### ๐ก ์๋ฐ์คํฌ๋ฆฝํธ ํํ
  - ์๋ฐ์คํฌ๋ฆฝํธ ํํ์ ์์ฑ ๊ฐ๋ฅ : {}๋ก ๊ฐ์ธ๊ธฐ
  ```JSX
  function App() {
  const name='๋ฆฌ์กํธ';
  return (
    <div>
      <h1>{name} ์๋?</h1>
      <h2>์ ์๋ํ๋?</h2>
    </div>
  );
}
  ```
 <details>
<summary>๐ES6์ cosnt์ let</summary>
<div markdown="1">
  
  - `var` : scope์ด ํจ์ ๋จ์ -> ํจ์๋ฅผ ๋น ์ ธ๋์ค๋ฉด ๊ฐ์ด ๋ฌ๋ผ์ง
  
  **๐ก `let`๊ณผ `const`๋ scope์ด ๋ธ๋ก ๋จ์, ๊ฐ์ ๋ธ๋ก ๋ด๋ถ์์ ์ค๋ณต ์ ์ธ ๋ถ๊ฐ๋ฅ**
  - `const` : ํ๋ฒ ์ง์ ํ๊ณ  ๋๋ฉด ๋ณ๊ฒฝ์ด ๋ถ๊ฐ๋ฅํ ์์๋ฅผ ์ ์ธํ  ๋ ์ฌ์ฉํ๋ ํค์๋
  - `let` : ๋์ ์ธ ๊ฐ์ ๋ด์ ์ ์๋ ๋ณ์๋ฅผ ์ ์ธํ  ๋ ์ฌ์ฉํ๋ ํค์๋
  
  </div>
  </details>
  
 ### ๐ก If๋ฌธ ๋์  ์กฐ๊ฑด๋ถ ์ฐ์ฐ์
 - JSX ๋ด๋ถ์ ์๋ฐ์คํฌ๋ฆฝํธ ํํ์์์ if ๋ฌธ ์ฌ์ฉX 
 
 **โก JSX ๋ฐ์์ if๋ฌธ์ ์ฌ์ฉํด ์ฌ์ ์ ๊ฐ์ ์ค์ , {}์์ ์กฐ๊ฑด๋ถ ์ฐ์ฐ์(์ผํญ ์ฐ์ฐ์) ์ฌ์ฉ ๊ฐ๋ฅ**
 ```JSX
 function App() {
  const name='๋ฆฌ์กํธ';
  return (
    <div>
      {name==='๋ฆฌ์กํธ'?(
        <h1>๋ฆฌ์กํธ์๋๋ค.</h1>
      ):(
        <h2>๋ฆฌ์กํธ๊ฐ ์๋๋๋ค.</h2>
      )}
    </div>
  );
}
```
  ### ๐ก AND ์ฐ์ฐ์(&&)๋ฅผ ์ฌ์ฉํ ์กฐ๊ฑด๋ถ ๋ ๋๋ง
 - ํน์  ์กฐ๊ฑด ๋ง์กฑํ  ๋๋ง ๋ ๋๋ง
 - && ๊ฐ๋ฅํ ์ด์  : ๋ฆฌ์กํธ์์ false ๋ ๋๋งํ  ๋๋ null๊ณผ ๋์ผํ๊ฒ ๋ํ๋์งX
 - 0์ ์์ธ์ ์ผ๋ก ๋ํ๋จ
 ```JSX
  function App() {
  const name='๋ฆฌ์ฉํธ';
  return <div>{name==='๋ฆฌ์กํธ' && <h1>๋ฆฌ์กํธ์๋๋ค.</h1>}</div>;
}
  ``` 
 ### ๐ก undefined๋ฅผ ๋ ๋๋งํ์ง ์๊ธฐ
  - ์ด๋ค ๊ฐ์ด undefined์ธ ๊ฒฝ์ฐ
    - OR(||)์ฐ์ฐ์ ์ฌ์ฉ
    - JSX ๋ด๋ถ์์ undefined ๋ ๋๋ง์ ๊ฐ๋ฅ
  ```JSX
  function App() {
 const name=undefined;
 return <div>{name||'๋ฆฌ์กํธ'}</div>;
}
  ```
 ### ๐ก ์ธ๋ผ์ธ ์คํ์ผ๋ง
  - DOM ์์์ ์คํ์ผ ์ ์ฉํ  ๋๋ **๊ฐ์ฒด ํํ**๋ก ๋ฃ์ด์ฃผ์ด์ผ ํจ
  ```JSX
  function App() {
  const name='๋ฆฌ์กํธ';
  return(
    <div
    style={{
      //background-color๋ backgroundColor์ ๊ฐ์ด -๊ฐ ์ฌ๋ผ์ง๊ณ  ์นด๋ฉ ํ๊ธฐ๋ฒ์ผ๋ก ์์ฑ
      backgroundColor:'black',
      color:'aqua',
      fontSize:'48px', //font-size -> fontSize
      fontWeight:'bold', //font-weight -> fontWeight
      padding:16 //๋จ์๋ฅผ ์๋ตํ๋ฉด px๋ก ์ง์  
    }}
    >{name}</div>
  )
}
  ```
 ### ๐ก class ๋์  className
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
  const name='๋ฆฌ์กํธ';
  return(
    <div className='react'>{name}</div>
  )
}
  ```
 ### ๐ก ์ฃผ์
  - `{/* ... */}` ํ์์ผ๋ก ์์ฑ
  ```JSX
  function App() {
  const name='๋ฆฌ์กํธ';
  return(
    <>
      {/* ์ฃผ์์ ์ด๋ ๊ฒ ์์ฑํฉ๋๋ค. */}
      <div 
        className='react' //์์ ํ๊ทธ๋ฅผ ์ฌ๋ฌ ์ค๋ก ์์ฑํ๋ฉด ์ฌ๊ธฐ์ ์ฃผ์ ์์ฑ ๊ฐ๋ฅ
      >{name}</div>
      //ํ์ง๋ง ์ด๋ฐ ์ฃผ์์ด๋
      /* ์ด๋ฐ ์ฃผ์์ ํ์ด์ง์ ๊ทธ๋๋ก ๋ํ๋๊ฒ ๋ฉ๋๋ค. */
      <input/>
    </>
  )
}
  ```
  ## ๐2.3 ESLint์ Prettier ์ ์ฉํ๊ธฐ
  - ๐ก ESLint : ๋ฌธ๋ฒ ๊ฒ์ฌ ๋๊ตฌ
  - ๐ก Prettier : ์ฝ๋ ์คํ์ผ ์๋ ์ ๋ฆฌ ๋๊ตฌ
    - ์ ์ฅํ  ๋ ์๋์ผ๋ก ์ฝ๋ ์ ๋ฆฌ : ํ์ผ > ๊ธฐ๋ณธ ์ค์  > ์ค์ 
  ![image](https://user-images.githubusercontent.com/97418768/178146180-fabed165-26ad-484f-b87b-2019e4ffe729.png)

  
  </div>
  </details>
  
  <details>
<summary>๐3์ฅ ์ปดํฌ๋ํธ</summary>
<div markdown="3">
  
## ๐3.1 ํด๋์คํ ์ปดํฌ๋ํธ
- ์ปดํฌ๋ํธ ์ ์ธ ๋ฐฉ์ : ํจ์ ์ปดํฌ๋ํธ, ํด๋์คํ ์ปดํฌ๋ํธ
  
๐ฅ ํจ์ ์ปดํฌ๋ํธ
  - ์ ์ธ์ด ํธํจ, ๋ฉ๋ชจ๋ฆฌ ์์ ์ ๊ฒ ์ฌ์ฉ
  
๐ฅ ํด๋์คํ ์ปดํฌ๋ํธ
  - state ๊ธฐ๋ฅ ๋ฐ ๋ผ์ดํ ์ฌ์ดํด ๊ธฐ๋ฅ, ์์ ๋ฉ์๋ ์ ์ ๊ฐ๋ฅ
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
<summary>๐ES6์ ํด๋์ค ๋ฌธ๋ฒ</summary>
<div markdown="1">
  
  - prototype ๋์  class ์ฌ์ฉ ๊ฐ๋ฅ
  ```JSX
  class Dog{
  constructor(name){
    this.name=name;
  }
  say(){
    console.log(this.name+': ๋ฉ๋ฉ');
  }
}

const dog=new Dog('ํฐ๋ฅ์ด');
dog.say(); //ํฐ๋ฅ์ด: ๋ฉ๋ฉ
```
  
  </div>
  </details>
  
## ๐3.2 ์ฒซ ์ปดํฌ๋ํธ ์์ฑ
  ### ๐ก src ๋๋ ํฐ๋ฆฌ์ MyComponent.js ํ์ผ ์์ฑ
  ### ๐ก ์ฝ๋ ์์ฑํ๊ธฐ
  ```JSX
  const MyComponent=()=>{
    return <div>๋์ ์๋กญ๊ณ  ๋ฉ์ง ์ปดํฌ๋ํธ</div>;
}

export default MyComponent;
  ```
  
  <details>
<summary>๐ES6์ ํ์ดํ ํจ์</summary>
<div markdown="1">
  
  - ES6 ๋ฌธ๋ฒ์์ ํจ์๋ฅผ ํํํ๋ ์๋ก์ด ๋ฐฉ์, ํจ์๋ฅผ ํ๋ผ๋ฏธํฐ๋ก ์ ๋ฌํ  ๋ ์ ์ฉ
  - ๊ฐ์ ์ฐ์ฐํ์ฌ ๋ฐ๋ก ๋ฐํํ  ๋ ๊ฐ๋์ฑ ๋์
  - ํจ์ ์ปดํฌ๋ํธ ์ ์ธํ  ๋, function ํค์๋์ ํ์ดํ ํจ์ ๋ฌธ๋ฒ ํฐ ์ฐจ์ดX
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
<summary>๐Reactjs Code Snippet์ ์ฌ์ฉํ์ฌ ์ฝ๋ ์์ฑํ๊ธฐ</summary>
<div markdown="2">
  
  - ์๋ํฐ์์ rsc๋ฅผ ์๋ ฅํ๊ณ  `Enter` ๋๋ฅด๊ธฐ
  
  ![image](https://user-images.githubusercontent.com/97418768/178147814-6ee5adba-da6c-45a4-832a-21190e5fe839.png)

  </div>
  </details>
  
  ### ๐ก ๋ชจ๋ ๋ด๋ณด๋ด๊ธฐ ๋ฐ ๋ถ๋ฌ์ค๊ธฐ
  **- ๋ชจ๋ ๋ด๋ณด๋ด๊ธฐ(export)**
  - ๋ค๋ฅธ ํ์ผ์์ ์ด ํ์ผ์ import ํ  ๋, MyComponent ํด๋์ค ๋ถ๋ฌ์ค๋๋ก ์ค์ 
  ```JSX
  export default MyComponent;
  ```
  **- ๋ชจ๋ ๋ถ๋ฌ์ค๊ธฐ(import)**
  - App ์ปดํฌ๋ํธ์์ MyComponent ์ปดํฌ๋ํธ ๋ถ๋ฌ์์ ์ฌ์ฉ
  ```JSX
  //App.js
import MyComponent from "./MyComponent"

const App=()=>{
  return <MyComponent/>;
};

export default App;
  ```
  
## ๐3.3 props
- properties๋ฅผ ์ค์ธ ํํ์ผ๋ก ์ปดํฌ๋ํธ ์์ฑ์ ์ค์ ํ  ๋ ์ฌ์ฉํ๋ ์์
- props ๊ฐ์ ํด๋น ์ปดํฌ๋ํธ๋ฅผ ๋ถ๋ฌ์ ์ฌ์ฉํ๋ ๋ถ๋ชจ ์ปดํฌ๋ํธ์์ ์ค์  ๊ฐ๋ฅ
### ๐ก JSX ๋ด๋ถ์์ props ๋ ๋๋ง
- props ๊ฐ์ ์ปดํฌ๋ํธ ํจ์์ ํ๋ผ๋ฏธํฐ๋ก ๋ฐ์์ ์ฌ์ฉ ๊ฐ๋ฅ
- JSX ๋ด๋ถ์์ {} ๊ธฐํธ๋ก ๊ฐ์ธ์ค
```JSX
const MyComponent = (props) => {
  return <div>์๋ํ์ธ์, ์  ์ด๋ฆ์ {props.name}์๋๋ค.</div>;
};

export default MyComponent;
```
### ๐ก ์ปดํฌ๋ํธ๋ฅผ ์ฌ์ฉํ  ๋ props ๊ฐ ์ง์ ํ๊ธฐ
```JSX
  //App.js
import MyComponent from "./MyComponent";

const App = () => {
  return <MyComponent name="React" />;
};

export default App;
```
 ### ๐ก props ๊ธฐ๋ณธ๊ฐ ์ค์ : defaultProps
  ```JSX
  const MyComponent = (props) => {
  return <div>์๋ํ์ธ์, ์  ์ด๋ฆ์ {props.name}์๋๋ค.</div>;
};

MyComponent.defaultProps = {
  name: "๊ธฐ๋ณธ ์ด๋ฆ",
};

export default MyComponent;
```
### ๐ก ํ๊ทธ ์ฌ์ด์ ๋ด์ฉ์ ๋ณด์ฌ ์ฃผ๋ children
  - ๋ฆฌ์กํธ ์ปดํฌ๋ํธ ํ๊ทธ ์ฌ์ด์ ๋ด์ฉ์ ๋ณด์ฌ์ฃผ๋ `props.children`
 ```JSX
  //App.js
import MyComponent from "./MyComponent";

const App = () => {
  return <MyComponent>๋ฆฌ์กํธ</MyComponent>;
};

export default App;
```
```JSX
  const MyComponent = (props) => {
  return (
    <div>
      ์๋ํ์ธ์, ์  ์ด๋ฆ์ {props.name}์๋๋ค.
      <br />
      children ๊ฐ์ {props.children}
      ์๋๋ค.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "๊ธฐ๋ณธ ์ด๋ฆ",
};

export default MyComponent;
```
 ### ๐ก ๋น๊ตฌ์กฐํ ํ ๋น ๋ฌธ๋ฒ์ ํตํด props ๋ด๋ถ ๊ฐ ์ถ์ถํ๊ธฐ
  - ES6์ ๋น๊ตฌ์กฐํ ํ ๋น : ๊ฐ์ฒด์์ ๊ฐ์ ์ถ์ถํ๋ ๋ฌธ๋ฒ
 ```JSX
  const MyComponent = ({ name, children }) => {
  return (
    <div>
      ์๋ํ์ธ์, ์  ์ด๋ฆ์ {name}์๋๋ค.
      <br />
      children ๊ฐ์ {children}
      ์๋๋ค.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "๊ธฐ๋ณธ ์ด๋ฆ",
};

export default MyComponent;
```
 ### ๐ก propTypes
  **๐ฅpropTypes๋ฅผ ํตํ props ๊ฒ์ฆ**
  - ์ปดํฌ๋ํธ์ ํ์ props๋ฅผ ์ง์ ํ๊ฑฐ๋ props์ ํ์(type) ์ง์ ํ๋ ๊ฒฝ์ฐ propTypes ์ฌ์ฉ
 ```JSX
  import PropTypes from "prop-types";

const MyComponent = ({ name, children }) => {
  return (
    <div>
      ์๋ํ์ธ์, ์  ์ด๋ฆ์ {name}์๋๋ค.
      <br />
      children ๊ฐ์ {children}
      ์๋๋ค.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "๊ธฐ๋ณธ ์ด๋ฆ",
};

MyComponent.propTypes = {
  name: PropTypes.string,
};

export default MyComponent;
```
**๐ฅ isRequired๋ฅผ ์ฌ์ฉํ์ฌ ํ์ propTypes ์ค์ **
  - propTypes๋ฅผ ์ง์ ํ์ง ์์์ ๋ ๊ฒฝ๊ณ  ๋ฉ์์ง ๋์์ค
 ```JSX
import PropTypes from "prop-types";

const MyComponent = ({ name, favoriteNumber, children }) => {
  return (
    <div>
      ์๋ํ์ธ์, ์  ์ด๋ฆ์ {name}์๋๋ค.
      <br />
      children ๊ฐ์ {children}
      ์๋๋ค.
      <br />
      ์ ๊ฐ ์ข์ํ๋ ์ซ์๋ {favoriteNumber}์๋๋ค.
    </div>
  );
};

MyComponent.defaultProps = {
  name: "๊ธฐ๋ณธ ์ด๋ฆ",
};

MyComponent.propTypes = {
  name: PropTypes.string,
  favoriteNumber: PropTypes.number.isRequired,
};

export default MyComponent;

```
 ### ๐ก ํด๋์คํ ์ปดํฌ๋ํธ์์ props ์ฌ์ฉํ๊ธฐ
  - render ํจ์์์ this.props ์กฐํ
  - defaultProps, propTypes ๋ฐฉ์ ๋์ผ
 ```JSX
  import PropTypes from "prop-types";
import { Component } from "react";

class MyComponent extends Component {
  render(){
    const {name, favoriteNumber,children}=this.props; //๋น๊ตฌ์กฐํ ํ ๋น
    return (
      <div>
        ์๋ํ์ธ์, ์  ์ด๋ฆ์ {name}์๋๋ค.
        <br />
        children ๊ฐ์ {children}
        ์๋๋ค.
        <br />
        ์ ๊ฐ ์ข์ํ๋ ์ซ์๋ {favoriteNumber}์๋๋ค.
      </div>
    );
  }
}

MyComponent.defaultProps = {
  name: "๊ธฐ๋ณธ ์ด๋ฆ",
};

MyComponent.propTypes = {
  name: PropTypes.string,
  favoriteNumber: PropTypes.number.isRequired,
};

export default MyComponent;
```
## ๐3.4 state
  - ์ปดํฌ๋ํธ ๋ด๋ถ์์ ๋ฐ๋ ์ ์๋ ๊ฐ
  - ํด๋์คํ ์ปดํฌ๋ํธ๊ฐ ์ง๋๊ณ  ์๋ state, ํจ์ ์ปดํฌ๋ํธ์์ useState๋ผ๋ ํจ์๋ฅผ ํตํด ์ฌ์ฉํ๋ state
 ### ๐ก ํด๋์คํ ์ปดํฌ๋ํธ์ state
  - `constructor` : ์ปดํฌ๋ํธ์ ์์ฑ์ ๋ฉ์๋, ๋ฐ๋์ `super(props)` ํธ์ถ!, state ์ด๊น๊ฐ ์ง์  ์ํจ
  - ์ปดํฌ๋ํธ์ state๋ **๊ฐ์ฒด ํ์**
  ```JSX
  import { Component } from "react";

class Counter extends Component {
  constructor(props) {
    super(props);
    //state์ ์ด๊น๊ฐ ์ค์ ํ๊ธฐ
    this.state = {
      number: 0,
    };
  }
  render() {
    const { number } = this.state; //state๋ฅผ ์กฐํํ  ๋๋ this.state๋ก ์กฐํ
    return (
      <div>
        <h1>{number}</h1>
        <button
          //onClick์ ํตํด ๋ฒํผ์ด ํด๋ฆญ๋์์ ๋ ํธ์ถํ  ํจ์๋ฅผ ์ง์ 
          onClick={() => { //์ด๋ฒคํธ๋ก ์ค์ ํ  ํจ์๋ฅผ ๋ฃ์ด ์ค ๋๋ ํ์ดํ ํจ์ ๋ฌธ๋ฒ!
            //this.setState๋ฅผ ์ฌ์ฉํ์ฌ state์ ์๋ก์ด ๊ฐ์ ๋ฃ์ ์ ์์
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
**๐ฅ state ๊ฐ์ฒด ์์ ์ฌ๋ฌ ๊ฐ์ด ์์ ๋**
  - state ์์ fixedNumber๊ฐ ์ถ๊ฐ
  ```JSX
  import { Component } from "react";

class Counter extends Component {
  constructor(props) {
    super(props);
    //state์ ์ด๊น๊ฐ ์ค์ ํ๊ธฐ
    this.state = {
      number: 0,
      fixedNumber: 0,
    };
  }
  render() {
    const { number, fixedNumber } = this.state; //state๋ฅผ ์กฐํํ  ๋๋ this.state๋ก ์กฐํ
    return (
      <div>
        <h1>{number}</h1>
        <h2>๋ฐ๋์ง ์๋ ๊ฐ: {fixedNumber}</h2>
        <button
          //onClick์ ํตํด ๋ฒํผ์ด ํด๋ฆญ๋์์ ๋ ํธ์ถํ  ํจ์๋ฅผ ์ง์ 
          onClick={() => {
            //this.setState๋ฅผ ์ฌ์ฉํ์ฌ state์ ์๋ก์ด ๊ฐ์ ๋ฃ์ ์ ์์
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
 **๐ฅ state๋ฅผ constructor์์ ๊บผ๋ด๊ธฐ**
  - constructor ๋ฉ์๋ ์ ์ธํ์ง ์๊ณ  state์ ์ด๊น๊ฐ ์ค์  ๊ฐ๋ฅ
  ```JSX
 import { Component } from "react";

class Counter extends Component {
  state = {
    number: 0,
    fixedNumber: 0,
  };
```
 **๐ฅ this.setState์ ๊ฐ์ฒด ๋์  ํจ์ ์ธ์ ์ ๋ฌํ๊ธฐ**
  - `prevState`:๊ธฐ์กด ์ํ, `props`: ํ์ฌ ์ง๋๊ณ  ์๋ props, ์๋ต ๊ฐ๋ฅ
  ```JSX
  this.setState((prevState,props) => {
     return {
       // ์๋ฐ์ดํธํ๊ณ  ์ถ์ ๋ด์ฉ
     };
  });
  ```
  - ํ์ดํ ํจ์์์ ๋ฐ๋ก ๊ฐ์ฒด๋ก ๋ฐํ
  ```JSX
  onClick={() => {
            this.setState((prevState) => {
              return {
                number: prevState.number + 1,
              };
            });
            //์ ์ฝ๋์ ์๋ ์ฝ๋๋ ์์ ํ ๋๊ฐ์ ๊ธฐ๋ฅ
            //์๋ ์ฝ๋๋ ํจ์์์ ๋ฐ๋ก ๊ฐ์ฒด๋ฅผ ๋ฐํํ๋ค๋ ์๋ฏธ
            this.setState((prevState) => ({
              number: prevState.number + 1,
            }));
          }}
   ```
 **๐ฅ this.setState๊ฐ ๋๋ ํ ํน์  ์์ ์คํํ๊ธฐ**
  - setState์ ๋ ๋ฒ์งธ ํ๋ผ๋ฏธํฐ์ธ ์ฝ๋ฐฑ(callback) ํจ์ ์ฌ์ฉ
  ```JSX
  onClick={() => {
            this.setState(
              {
                number: number + 1,
              },
              () => {
                console.log("๋ฐฉ๊ธ setState๊ฐ ํธ์ถ๋์์ต๋๋ค.");
                console.log(this.state);
              }
            );
          }}
  ```
 ### ๐ก ํจ์ ์ปดํฌ๋ํธ์์ useState ์ฌ์ฉํ๊ธฐ
  **๐ฅ ๋ฐฐ์ด ๋น๊ตฌ์กฐํ ํ ๋น**
  - ๊ฐ์ฒด ๋น๊ตฌ์กฐํ ํ ๋น๊ณผ ๋น์ท, ๋ฐฐ์ด ์์ ๋ค์ด ์๋ ๊ฐ์ ์ฝ๊ฒ ์ถ์ถํ๊ธฐ ์ํ ๋ฌธ๋ฒ
  ```JSX
  const array=[1,2];
  const [one,two]=array;
  ```
  **๐ฅ useState ์ฌ์ฉํ๊ธฐ**
  - useState ํจ์ ์ธ์์๋ ์ํ์ ์ด๊น๊ฐ ๋ฃ์ด์ค(๊ฐ ํํ ์์ )
  - ํจ์ ํธ์ถ -> ๋ฐฐ์ด ๋ฐํ [ํ์ฌ ์ํ,์ํ๋ฅผ ๋ฐ๊พธ์ด ์ฃผ๋ ํจ์(Setter ํจ์)]
  ```JSX
  import { useState } from "react";

const Say = () => {
  const [message, setMessage] = useState(""); //"" : ์ด๊น๊ฐ
  //[ํ์ฌ ์ํ,์ํ๋ฅผ ๋ฐ๊พธ์ด ์ฃผ๋ ํจ์(Setter ํจ์)] 
  const onClickEnter = () => setMessage("์๋ํ์ธ์!");
  const onClickLeave = () => setMessage("์๋ํ ๊ฐ์ธ์!");

  return (
    <div>
      <button onClick={onClickEnter}>์์ฅ</button>
      <button onClick={onClickLeave}>ํด์ฅ</button>
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
**๐ฅ ํ ์ปดํฌ๋ํธ์ useState ์ฌ๋ฌ ๋ฒ ์ฌ์ฉํ๊ธฐ**
  ```JSX
  import { useState } from "react";

const Say = () => {
  const [message, setMessage] = useState("");
  const onClickEnter = () => setMessage("์๋ํ์ธ์!");
  const onClickLeave = () => setMessage("์๋ํ ๊ฐ์ธ์!");

  const [color, setColor] = useState("black");

  return (
    <div>
      <button onClick={onClickEnter}>์์ฅ</button>
      <button onClick={onClickLeave}>ํด์ฅ</button>
      <h1 style={{ color }}>{message}</h1>
      <button style={{ color: "red" }} onClick={() => setColor("red")}>
        ๋นจ๊ฐ์
      </button>
      <button style={{ color: "green" }} onClick={() => setColor("green")}>
        ์ด๋ก์
      </button>
      <button style={{ color: "blue" }} onClick={() => setColor("blue")}>
        ํ๋์
      </button>
    </div>
  );
};

export default Say;
```
## ๐3.5 state๋ฅผ ์ฌ์ฉํ  ๋ ์ฃผ์ ์ฌํญ
 - state ๊ฐ์ ๋ณ๊ฒฝํ  ๋
    - setState ์ฌ์ฉ(ํด๋์คํ ์ปดํฌ๋ํธ)
    - useState๋ฅผ ํตํด ์ ๋ฌ๋ฐ์ ์ธํฐ ํจ์ ์ฌ์ฉ (ํจ์ ์ปดํฌ๋ํธ)
  </div>
  </details>
 
<details>
<summary>๐6์ฅ ์ปดํฌ๋ํธ ๋ฐ๋ณต</summary>
<div markdown="4">

## ๐6.1 ์๋ฐ์คํฌ๋ฆฝํธ ๋ฐฐ์ด์ map() ํจ์
  - ๋ฐ๋ณต๋๋ ์ปดํฌ๋ํธ ๋ ๋๋ง์ ์ฌ์ฉ
  - ํ๋ผ๋ฏธํฐ๋ก ์ ๋ฌ๋ ํจ์๋ฅผ ์ฌ์ฉํด์ ๋ฐฐ์ด ๋ด ๊ฐ ์์๋ฅผ ์ํ๋ ๊ท์น์ ๋ฐ๋ผ ๋ณํํ ํ ๊ทธ ๊ฒฐ๊ณผ๋ก ์๋ก์ด ๋ฐฐ์ด ์์ฑ
  ### ๐ก map ๋ฌธ๋ฒ
  `arr.map(callback,[thisArg])`
  
  - callback: ์๋ก์ด ๋ฐฐ์ด์ ์์๋ฅผ ์์ฑํ๋ ํจ์, ํ๋ผ๋ฏธํฐ 3๊ฐ์ง
    - currentValue: ํ์ฌ ์ฒ๋ฆฌ ์์
    - index: ํ์ฌ ์ฒ๋ฆฌ ์์ index ๊ฐ
    - array: ํ์ฌ ์ฒ๋ฆฌ ์๋ณธ ๋ฐฐ์ด
  - thisArg(์ ํ ํญ๋ชฉ): callback ํจ์ ๋ด๋ถ์์ ์ฌ์ฉํ  this ๋ ํผ๋ฐ์ค
  ```JSX
  const numbers=[1,2,3,4,5];
  const result=numbers.map(num=>num*num);
  console.log(result);
  ```
## ๐6.2 ๋ฐ์ดํฐ ๋ฐฐ์ด์ ์ปดํฌ๋ํธ ๋ฐฐ์ด๋ก ๋ณํํ๊ธฐ
 ```JSX
  const IterationSample = () => {
  const names = ["๋์ฌ๋", "์ผ์", "๋", "๋ฐ๋"];
  const nameList = names.map((name) => <li>{name}</li>);
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```
```JSX
  //App.js
import { Component } from "react";
import IterationSample from "./IterationSample"; //IterationSample ์ปดํฌ๋ํธ ๋ถ๋ฌ์ ๋ ๋๋ง

class App extends Component {
  render() {
    return <IterationSample />;
  }
}

export default App;
```
## ๐6.3 key
  - ๋ฐ์ดํฐ๊ฐ ๊ฐ์ง ๊ณ ์ ์ ๊ฐ์ผ๋ก ์ค์ 
  - map ํจ์์ ์ธ์๋ก ์ ๋ฌ๋๋ ํจ์ ๋ด๋ถ์์ ์ปดํฌ๋ํธ props ์ค์ ํ๋ฏ ์ค์ 
  - Virtual Dom ๋น๊ตํ๋ ๊ณผ์ ์์ key๋ก ๋ฐ๋ก ๋ณํ ๊ฐ์ง ๊ฐ๋ฅ
  ```JSX
  const IterationSample = () => {
  const names = ["๋์ฌ๋", "์ผ์", "๋", "๋ฐ๋"];
  const nameList = names.map((name, index) => <li key={index}>{name}</li>);
  //๊ณ ์ ์ ๊ฐ์ด ์์ ๋๋ง index๋ฅผ key ๊ฐ์ผ๋ก ์ค์ 
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```
## ๐6.4 ์์ฉ(๋์ ์ธ ๋ฐฐ์ด ๋ ๋๋ง)
  
### ๐ก ์ด๊ธฐ ์ํ ์ค์ ํ๊ธฐ
  
  - useState๋ฅผ ์ฌ์ฉํด ์ํ ์ค์ 
  - 3๊ฐ์ง ์ํ : ๋ฐ์ดํฐ ๋ฐฐ์ด, ํ์ค๋ฅผ ์๋ ฅ input ์ํ, ๋ฐฐ์ด์ ์๋ก์ด ํญ๋ชฉ ์ถ๊ฐํ  ๋ ์ฌ์ฉํ๋ ๊ณ ์  id ์ํ
  
  ```JSX
  import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([ //ํด๋น ๊ฐ์ฒด๋ ๋ฌธ์์ด๊ณผ ๊ณ ์  id ๊ฐ์ด ์์
    { id: 1, text: "๋์ฌ๋" },
    { id: 2, text: "์ผ์" },
    { id: 3, text: "๋" },
    { id: 4, text: "๋ฐ๋" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); //์๋ก์ด ํญ๋ชฉ์ ์ถ๊ฐํ  ๋ ์ฌ์ฉํ  id

  const nameList = names.map((name) => <li key={name.id}>{name.text}</li>);
  //mapํจ์์์ name.id๋ฅผ key ๊ฐ์ผ๋ก ์ค์ 
  return <ul>{nameList}</ul>;
};

export default IterationSample;
```
  
### ๐ก ๋ฐ์ดํฐ ์ถ๊ฐ ๊ธฐ๋ฅ ๊ตฌํํ๊ธฐ
  
 - `concat` : ๋ฐฐ์ด์ ์ ํญ๋ชฉ ์ถ๊ฐ(์๋ก์ด ๋ฐฐ์ด์ ๋ง๋ค์ด์ค)
  
  ```JSX
  import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "๋์ฌ๋" },
    { id: 2, text: "์ผ์" },
    { id: 3, text: "๋" },
    { id: 4, text: "๋ฐ๋" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); //์๋ก์ด ํญ๋ชฉ์ ์ถ๊ฐํ  ๋ ์ฌ์ฉํ  id

  const onChange = (e) => setInputText(e.target.value);
  const onClick = () => {
    const nextNames = names.concat({
      id: nextId, //nextId ๊ฐ์ id๋ก ์ค์ ํ๊ณ 
      text: inputText,
    });
    setNextId(nextId + 1); //nextId ๊ฐ์ 1์ ๋ํด์ค๋ค
    setNames(nextNames); //names ๊ฐ์ ์๋ฐ์ดํธ
    setInputText(""); //inputText๋ฅผ ์ง์ด๋ค
  };
  const nameList = names.map((name) => <li key={name.id}>{name.text}</li>);
  //name.id๋ฅผ key ๊ฐ์ผ๋ก ์ค์ 
  return (
    <>
      <input value={inputText} onChange={onChange} />
      <button onClick={onClick}>์ถ๊ฐ</button>
      <ul>{nameList}</ul>
    </>
  );
};

export default IterationSample;
```
### ๐ก ๋ฐ์ดํฐ ์ ๊ฑฐ ๊ธฐ๋ฅ ๊ตฌํํ๊ธฐ
 - ๋๋ธํด๋ฆญ(`onDoubleClick`) -> ํด๋น ํญ๋ชฉ ์ญ์ 
 - `fiter` : ๋ถ๋ณ์ฑ ์ ์งํ๋ฉด์ ๋ฐฐ์ด์ ํน์  ํญ๋ชฉ ์ญ์ ํ  ๋ ์ฐ๋ ๋ฐฐ์ด์ ๋ด์ฅํจ์
  ```JSX
  import { useState } from "react";

const IterationSample = () => {
  const [names, setNames] = useState([
    { id: 1, text: "๋์ฌ๋" },
    { id: 2, text: "์ผ์" },
    { id: 3, text: "๋" },
    { id: 4, text: "๋ฐ๋" },
  ]);
  const [inputText, setInputText] = useState("");
  const [nextId, setNextId] = useState(5); //์๋ก์ด ํญ๋ชฉ์ ์ถ๊ฐํ  ๋ ์ฌ์ฉํ  id

  const onChange = (e) => setInputText(e.target.value);
  const onClick = () => {
    const nextNames = names.concat({
      id: nextId, //nextId ๊ฐ์ id๋ก ์ค์ ํ๊ณ 
      text: inputText,
    });
    setNextId(nextId + 1); //nextId ๊ฐ์ 1์ ๋ํด์ค๋ค
    setNames(nextNames); //names ๊ฐ์ ์๋ฐ์ดํธ
    setInputText(""); //inputText๋ฅผ ์ง์ด๋ค
  };

  const onRemove = (id) => {
    //onRemove ํจ์๋ฅผ ๋ง๋ค์ด ๊ฐ li ์์ ์ด๋ฒคํธ ๋ฑ๋ก
    const nextNames = names.filter((name) => name.id !== id);
    //name.id ===id์ธ ํญ๋ชฉ๋ง ์ญ์ 
    setNames(nextNames);
  };
  const nameList = names.map((name) => (
    <li key={name.id} onDoubleClick={() => onRemove(name.id)}>
      {name.text}
    </li>
  ));
  //name.id๋ฅผ key ๊ฐ์ผ๋ก ์ค์ 
  return (
    <>
      <input value={inputText} onChange={onChange} />
      <button onClick={onClick}>์ถ๊ฐ</button>
      <ul>{nameList}</ul>
    </>
  );
};

export default IterationSample;
```
  </div>
  </details>
  
<details>
<summary>๐8์ฅ Hooks</summary>
<div markdown="5">

## ๐8.1 useState
  - ๊ฐ์ฅ ๊ธฐ๋ณธ์ ์ธ Hook, ํจ์ ์ปดํฌ๋ํธ์์๋ ๊ฐ๋ณ์ ์ธ ์ํ ์ง๋ ์ ์์
  - ํ๋์ useState ํจ์๋ ํ๋์ ์ํ ๊ฐ๋ง ๊ด๋ฆฌ -> ์ปดํฌ๋ํธ์์ ๊ด๋ฆฌํด์ผ ํ  ์ํ ์ฌ๋ฌ๊ฐ๋ฉด ์ฌ๋ฌ๊ฐ useState ์ฌ์ฉ
## ๐8.2 useEffect
  - ๋ฆฌ์กํธ ์ปดํฌ๋ํธ๊ฐ ๋ ๋๋ง๋  ๋๋ง๋ค ํน์  ์์์ ์ํํ๋๋ก ์ค์ ํ  ์ ์๋ Hook
  ```JSX
  import { useState, useEffect } from "react";

const Info = () => {
  const [name, setName] = useState("");
  const [nickname, setNickname] = useState("");
  useEffect(() => {
    console.log("๋ ๋๋ง์ด ์๋ฃ๋์์ต๋๋ค!");
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
        <b>์ด๋ฆ:</b> {name}
      </div>
      <div>
        <b>๋๋ค์:</b> {nickname}
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
### ๐ก ๋ง์ดํธ๋  ๋๋ง ์คํํ๊ณ  ์ถ์ ๋
  - useEffect์์ ์ค์ ํ ํจ์๋ฅผ ์ปดํฌ๋ํธ๊ฐ ํ๋ฉด์ ๋งจ ์ฒ์ ๋ ๋๋ง๋  ๋๋ง ์คํ, ์๋ฐ์ดํธ๋  ๋๋ ์คํX
  
  โก ํจ์์ ๋ ๋ฒ์งธ ํ๋ผ๋ฏธํฐ๋ก ๋น์ด ์๋ ๋ฐฐ์ด ๋ฃ์ด์ค
 ```JSX
  useEffect(() => {
    console.log("๋ ๋๋ง์ด ์๋ฃ๋์์ต๋๋ค!");
  }, []);
  ```
### ๐ก ํน์  ๊ฐ์ด ์๋ฐ์ดํธ๋  ๋๋ง ์คํํ๊ณ  ์ถ์ ๋
  - useEffect์ ๋ ๋ฒ์งธ ํ๋ผ๋ฏธํฐ๋ก ์ ๋ฌ๋๋ ๋ฐฐ์ด ์์ ๊ฒ์ฌํ๊ณ  ์ถ์ ๊ฐ ๋ฃ์ด์ค
 ```JSX
    useEffect(() => {
    console.log("๋ ๋๋ง์ด ์๋ฃ๋์์ต๋๋ค!");
  }, [name]);
  ```
## ๐8.3 useReducer
  - useState๋ณด๋ค ๋ ๋ค์ํ ์ปดํฌ๋ํธ ์ํฉ์ ๋ฐ๋ผ ๋ค์ํ ์ํ๋ฅผ ๋ค๋ฅธ ๊ฐ์ผ๋ก ์๋ฐ์ดํธํ  ๋ ์ฌ์ฉํ๋ Hook
  - ํ์ฌ ์ํ, ์๋ฐ์ดํธ๋ฅด ์ํด ํ์ํ ์ ๋ณด๋ฅผ ๋ด์ ์ก์(action) ๊ฐ์ ์ ๋ฌ๋ฐ์ ์๋ก์ด ์ํ๋ฅผ ๋ฐํํ๋ ํจ์
  - ๋ถ๋ณ์ฑ ์ง์ผ์ค์ผํจ!
```JSX
 function reducer(state,action){
  return{...}; //๋ถ๋ณ์ฑ์ ์งํค๋ฉด์ ์๋ฐ์ดํธํ ์๋ก์ด ์ํ๋ฅผ ๋ฐํ
 }
```
```JSX
//์ก์ ๊ฐ : useReducer์ ์ก์์ ๊ผญ type ์ง๋ ํ์X, ๊ฐ์ฒด๊ฐ ์๋๋ผ ๋ฌธ์์ด, ์ซ์ ์๊ดX
{
  type:'INCREMENT',
  //๋ค๋ฅธ ๊ฐ๋ค์ด ํ์ํ๋ค๋ฉด ์ถ๊ฐ๋ก ๋ค์ด๊ฐ
}
```
 - `useReducer(๋ฆฌ๋์ ํจ์, ํด๋น ๋ฆฌ๋์์ ๊ธฐ๋ณธ๊ฐ)`
 - ์ฅ์ : ์ปดํฌ๋ํธ ์๋ฐ์ดํธ ๋ก์ง์ ์ปดํฌ๋ํธ ๋ฐ๊นฅ์ผ๋ก ๋นผ๋ผ ์ ์์
```JSX
  import { useReducer } from "react";

function reducer(state, action) {
  //action.type์ ๋ฐ๋ผ ๋ค๋ฅธ ์์ ์ํ
  switch (action.type) {
    case "INCREMENT":
      return { value: state.value + 1 };
    case "DECREMENT":
      return { value: state.value - 1 };
    default:
      //์๋ฌด๊ฒ๋ ํด๋น๋์ง ์์ ๋ ๊ธฐ์กด ์ํ ๋ฐํ
      return state;
  }
}

const Counter = () => {
  const [state, dispatch] = useReducer(reducer, { value: 0 });
  //state: ํ์ฌ ๊ฐ๋ฆฌํค๊ณ  ์๋ ์ํ, dispatch: ์ก์ ๋ฐ์์ํค๋ ํจ์
  //dispatch(action) => ๋ฆฌ๋์ ํจ์ ํธ์ถ
  //useReducer(๋ฆฌ๋์ ํจ์, ํด๋น ๋ฆฌ๋์์ ๊ธฐ๋ณธ๊ฐ)
  return (
    <div>
      <p>
        ํ์ฌ ์นด์ดํฐ ๊ฐ์ <b>{state.value}</b>์๋๋ค.
      </p>
      <button onClick={() => dispatch({ type: "INCREMENT" })}>+1</button>
      <button onClick={() => dispatch({ type: "DECREMENT" })}>-1</button>
    </div>
  );
};

export default Counter;
```
### ๐ก useReducer๋ก ์ธํ ์ํ ๊ด๋ฆฌํ๊ธฐ
  - setState๋ฅผ ํด์ค ๊ฒ๊ณผ ์ ์ฌํ ๋ฐฉ์์ผ๋ก ์ฒ๋ฆฌ ๊ฐ๋ฅ
  - ์ธํ์ ๊ฐ์๊ฐ ๋ง์์ ธ๋ ์ฝ๋๋ฅผ ์งง๊ณ  ๊น๋ํ๊ฒ ์ ์ง ๊ฐ๋ฅ
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

  //์ด๋ฒคํธ ๊ฐ์ฒด๊ฐ ์ง๋๊ณ  ์๋ e.target ๊ฐ ์์ฒด๋ฅผ ์ก์ ๊ฐ์ผ๋ก ์ฌ์ฉ
  const onChange = (e) => {
    dispatch(e.target);
  };

  return (
    <div>
      <div>
        {/* input ํ๊ทธ์ name ๊ฐ์ ํ ๋นํ๊ณ  e.target.name์ ์ฐธ์กฐํด setState์ ์ ์ฌํ๊ฒ ์ฒ๋ฆฌ */}
        <input name="name" value={name} onChange={onChange} />
        <input name="nickname" value={nickname} onChange={onChange} />
      </div>
      <div>
        <b>์ด๋ฆ:</b> {name}
      </div>
      <div>
        <b>๋๋ค์:</b> {nickname}
      </div>
    </div>
  );
};

export default Info;
```
## ๐8.4 useMemo
 - ํจ์ ์ปดํฌ๋ํธ ๋ด๋ถ์์ ๋ฐ์ํ๋ ์ฐ์ฐ ์ต์ ํ
 - ๋ ๋๋งํ๋ ๊ณผ์ ์์ ํน์  ๊ฐ์ด ๋ฐ๋์์ ๋๋ง ์ฐ์ฐ์ ์คํ, ์ํ๋ ๊ฐ์ด ๋ฐ๋์ง ์์๋ค๋ฉด ์ด์ ์ ์ฐ์ฐํ๋ ๊ฒฐ๊ณผ๋ฅผ ๋ค์ ์ฌ์ฉํ๋ ๋ฐฉ์
 ```JSX
import { useState, useMemo } from "react";

const getAverage = (numbers) => {
  console.log("ํ๊ท ๊ฐ ๊ณ์ฐ ์ค...");
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
  //list ๋ฐฐ์ด์ ๋ด์ฉ์ด ๋ฐ๋ ๋๋ง getAverge ํจ์ ํธ์ถ

  return (
    <div>
      <input value={number} onChange={onChange} />
      <button onClick={onInsert}>๋ฑ๋ก</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>ํ๊ท ๊ฐ:</b>
        {avg}
      </div>
    </div>
  );
};

export default Average;
```
## ๐8.5 useCallback
  - useMemo์ ๋น์ท, ๋ ๋๋ง ์ฑ๋ฅ ์ต์ ํ ์ํฉ์ ์ฌ์ฉ
  - ๋ง๋ค์ด ๋จ๋ ํจ์ ์ฌ์ฌ์ฉ ๊ฐ๋ฅ
  - `useCallback(์์ฑํ๊ณ  ์ถ์ ํจ์, ๋ฐฐ์ด(์ด๋ค ๊ฐ์ด ๋ฐ๋์์ ๋ ํจ์๋ฅผ ์๋ก ์์ฑํ๋์ง ๋ช์))`
```JSX
 const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");

  const onChange = useCallback((e) => {
    setNumber(e.target.value);
  }, []); //์ปดํฌ๋ํธ๊ฐ ์ฒ์ ๋ ๋๋ง๋  ๋๋ง ํจ์ ์์ฑ, ๋ ๋๋ง๋  ๋ ๋ง๋ค์๋ ํจ์ ์ฌ์ฌ์ฉ

  const onInsert = useCallback(() => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
  }, [number, list]); //number ํน์ list๊ฐ ๋ฐ๋์์ ๋๋ง ํจ์ ์์ฑ, ์๋๋ฉด ํจ์ 
  ```
## ๐8.6 useRef
  - ํจ์ ์ปดํฌ๋ํธ์์ ref๋ฅผ ์ฝ๊ฒ ์ฌ์ฉ ๊ฐ๋ฅํ๊ฒ ํจ
  - useRef๋ฅผ ์ฌ์ฉํด ref ์ค์  -> useRef๋ฅผ ํตํด ๋ง๋  ๊ฐ์ฒด ์์ current ๊ฐ์ด ์ค์  ์๋ฆฌ๋จผํธ ๊ฐ๋ฆฌํด
 ```JSX
  import { useState, useMemo, useCallback, useRef } from "react";

const getAverage = (numbers) => {
  console.log("ํ๊ท ๊ฐ ๊ณ์ฐ ์ค...");
  if (numbers.length === 0) return 0;
  const sum = numbers.reduce((a, b) => a + b);
  return sum / numbers.length;
};

const Average = () => {
  const [list, setList] = useState([]);
  const [number, setNumber] = useState("");
  //ref๋ฅผ ์ํ ๋ณ์ ์ ์ธ
  const inputEl = useRef(null);

  const onChange = useCallback((e) => {
    setNumber(e.target.value);
  }, []); //์ปดํฌ๋ํธ๊ฐ ์ฒ์ ๋ ๋๋ง๋  ๋๋ง ํจ์ ์์ฑ

  const onInsert = useCallback(() => {
    const nextList = list.concat(parseInt(number));
    setList(nextList);
    setNumber("");
    inputEl.current.focus(); //์ปค์ ์ด๋์ ์ํ  ๋,
  }, [number, list]); //number ํน์ list๊ฐ ๋ฐ๋์์ ๋๋ง ํจ์ ์์ฑ

  const avg = useMemo(() => getAverage(list), [list]);
  //list ๋ฐฐ์ด์ ๋ด์ฉ์ด ๋ฐ๋ ๋๋ง getAverge ํจ์ ํธ์ถ

  return (
    <div>
      <input value={number} onChange={onChange} ref={inputEl} />
      <button onClick={onInsert}>๋ฑ๋ก</button>
      <ul>
        {list.map((value, index) => (
          <li key={index}>{value}</li>
        ))}
      </ul>
      <div>
        <b>ํ๊ท ๊ฐ:</b>
        {avg}
      </div>
    </div>
  );
};

export default Average;
 ```
  
 <details>
<summary>๐refํตํ input ํ๊ทธ ์ปค์/ํฌ์ปค์ค ์กฐ์ </summary>
<div markdown="1">
  
  - `ref` : DOM์ ์ง์  ์ ๊ทผํด์ผํ  ๋ ์ฌ์ฉ
  - ์ง์  ์ ๊ทผ์ด ํ์ํ ๊ฒฝ์ฐ
    - input / textare ๋ฑ์ ์ปค์ ์กฐ์ 
    - DOM ์ ํฌ๊ธฐ๋ฅผ ๊ฐ์ ธ์์ผ ํ  ๋
    - DOM ์์ ์คํฌ๋กค ์์น๋ฅผ ๊ฐ์ ธ์ค๊ฑฐ๋ ์ค์ ์ ํด์ผ ํ  ๋
    - ์ธ๋ถ ๋ผ์ด๋ธ๋ฌ๋ฆฌ (ํ๋ ์ด์ด, ์ฐจํธ, ์บ๋ก์  ๋ฑ)์ ์ฌ์ฉ ํ  ๋
  
  </div>
  </details>
  
  ### ๐ก ๋ก์ปฌ ๋ณ์ ์ฌ์ฉํ๊ธฐ
   - ๋ก์ปฌ ๋ณ์ : ๋ ๋๋ง๊ณผ ์๊ด์์ด ๋ฐ๋ ์ ์๋ ๊ฐ
   - ๋ ๋๋ง๊ณผ ๊ด๋ จ๋์ง ์์ ๊ฐ์ ๊ด๋ฆฌํ  ๋ ์ฌ์ฉ, ref ์์ ๊ฐ์ด ๋ฐ๋์ด๋ ์ปดํฌ๋ํธ๊ฐ ๋ ๋๋งX
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

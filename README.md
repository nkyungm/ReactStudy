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
  
  ### 💡 yarn
  ### 💡 에디터 설치
  ### 💡 Git 설치
  ### 💡 create-react-app으로 프로젝트 생성하기
  
</div>
</detail>

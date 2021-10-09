# React ch.1

```컴포넌트란?

html 엘리먼트

<img src =" 이미지 주소"/>
<button class =" 클래스 이름"> 버튼</button>

클레스 이름은 이것이다 , 이것은 이미 정해져 있는 태그 

내가 만든 컴포넌트란?

내가 지은 이름을 가지고 내가 정한 어트리뷰트 하나를 표현 해주는 것 

src, class, name, props, 밖에서 넣어주는 데이터

문서 , 스타일, 동작 를 합쳐서 내가 만든 일종의 태그

컴포넌트 트리 ⇒ 돔 트리 

버츄얼 돔이란?

- 돔을 직접 제어하는 경우
    - 바뀐 부분만 정확히 바꿔야 한다.
- 돔을 직접 제어하지 않는 경우
    - 가상의 돔 트리를 사용해서,
    - 이전 상태와 이후 상태를 비교하여,
    - 바뀐 부분을 찾아내서 자동으로 바꾼다.
        
        <img width="997" alt="스크린샷_2021-10-09_오후_4 35 44" src="https://user-images.githubusercontent.com/88579497/136649453-2f004cf4-d733-4209-9a9b-4185fc9159a4.png">


리액트의 클라이언트 싸이드 랜더링 이란?

CSR 

- html 먼저 다운 받아 지고 → js 받아 지고 → 리액트 웹을 실행 하기 까지는 화면에 아직 안나온다
- js 가 전부 다운로드 되어 리액트 애플리케이션이 정상 실행되기 전까지는 화면이 보이지 않음.
- js 가 전부 다운로드 되어 리액트 애플리케이션이 정상 실행된 후, 화면이 보이면서 유저가 인터렉션 가능

리액트의 서버 싸이드 랜더링 이란?

SSR 

- html 에서 다운 되고 랜더 됨으로써 js는 동작 안 함 미리 내려온 화면은 볼수 있고 js와 react 앱이 
실행
- js가 전부 다운로드 되지 않아도, 일단 화면은 보이지만 유저가 사용 할 수 없음.
- js 가 전부 다운로드 되어 리액트 애플리케이션이 정상 실행된 후, 유저가 사용 가능

리액트가 하는 일
-리액트의 핵심 모듈 2개

//1. 리액트 컴포넌트 -> html엘레먼트 연결하기 
import ReactDOM from 'react-dom';
리액트 돔으로 부터 리액트 돔을 가져 온다 
리액트 돔은 리액트 컴포넌트 를 html 엘레먼트에 연결

//2. 리액트 컴포넌트 만들기 
import React from 'react';

import는 ES6 부터 사용하는 방법 


- 프론트 엔드

html -> css -> js로 dom을 조작 

직접 돔을 제어 하는 방식

https://user-images.githubusercontent.com/88579497/136651486-11c3d612-8104-47c2-bda7-749a473592e7.mov


- 컴포넌트를 활용한 프론트엔드 

https://user-images.githubusercontent.com/88579497/136651940-21aacd20-f9d5-417e-afe0-1cb407d11e6a.mov

-리액트를 이용한 



https://user-images.githubusercontent.com/88579497/136652611-44fe6055-a79d-4f92-ba4f-1260647be89d.mov



// const root = document.querySelector('#root');
    // const btn_plus = document.querySelector('#btn_plus')

    // let i= 0;

    // root.innerHTML = '<p>init : 0</p>';

    // btn_plus.addEventListener('click', ()=>{
    //   root.innerHTML = `<p> init : ${++i} </p>`
    // });

    // const component = {
    //   message: 'init',
    //   count: 0,
    //   render() {
    //     return `<p>${this.message} : ${this.count}</p>`;
    //   }
    // };

    // function render(rootElement, component) {
    //   rootElement.innerHTML = component.render();
    // }
    // //초기화
    // render(document.querySelector('#root'), component);

    // document.querySelector('#btn_plus').addEventListener('click', () => {
    //   component.message = 'update';
    //   component.count = component.count +1;

    //   render(document.querySelector('#root'), component);
    // });

    // 리액트 컴포넌트
    // <p hello = "world"> 피 태그를 쓸건데 null자리 들어 갈 피 태그 값이지만 null이라 받지 않는다
    // <p>""</p>
    // 외부에서 프롭스로 받은 메시지와 카운터를 피 태그의 가운데에 들어가는 값으로 정의 
    // const component = props => {
    //   return React.createElement('p', null, `${props.message}:${props.count}`);
    // }

    // ReactDOM.render(React.createElement(component, {
    //   message: 'init',
    //   count: 0
    // }, null), document.querySelector('#root'));

    // document.querySelector('#btn_plus').addEventListener("click", () => {
    //   ReactDOM.render(React.createElement(component, {
    //     message: 'update',
    //     count: 10
    //   }, null), document.querySelector('#root'));
    // });

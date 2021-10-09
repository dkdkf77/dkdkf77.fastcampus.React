

Hooks 이전 

 1. 컴포넌트 내부에 상태가 있다면?
  - class 컴포넌트를 사용
 2. 컴포넌트 내부에 상태가 없다면?
  - 라이프 사이클을 사용해야 한다면?
    - class
  - 라이프 사이클에 관계 없다면?
    - function 

Hook 이후 
 - class
 - function

 class 컴포넌트 

 import React from 'react';

 //정의

 <!-- class ClassComponent extends React.Component {
    render() {
      retrun (<div>Hello</div>)
    }
 }
// 사용
<ClassComponent/> -->
<!-- 
function 컴포넌트 

import React from 'react';

//정의 1
function FunctionComponent() {
  return <div>Hello</div>
}

//정의 2
const FunctionComponent = () => <div>Hello</div>;

//사용
<FunctionComponent/> -->

 //class 컴포넌트 사용법
    //정의
    // class ClassComponent extends React.Component{
    //   render() {
    //     return <div>Hello</div>;
    //   }
    // }

    // //사용 
    // ReactDOM.render(
    //   <ClassComponent/>,
    //   document.querySelector('#root')
    // )

    //function 컴포넌트 사용법
    //정의 1
    // JSX 란? 리액트.createElement를 하겠다는 말 
    // function FunctionComponent() {
    //   return <div>Hello</div>;
    // }
    
    // //사용
    // ReactDOM.render(<FunctionComponent/>, document.querySelector('#root'));

    // 정의 2
    // 에로우 펑션의 특징은 만약 리턴만 있다면 중괄호와 리턴을 생략 할 수 있다 !
    // const FunctionComponent = () => <div>Hello</div>;

    // ReactDOM.render(<FunctionComponent/>, document.querySelector('#root'));
    

    React.createElement로 컴포넌트 만들기

    // React.creatElement(
    //   type // 첫번째 인자: 태그 이름 문자열 | 리액트 컴포넌트 | React.Fragment
    //   [props] //두번째 인자 : 어떤 태그나 리액트 컴포넌트나 크리에이트 앨리먼트 를 데이터를 주입해서 사용 가능 , 리액트 컴포넌트에 넣어주는 데이터 객체
    //   [...children] //세번째 인자 : 자식으로 넣어주는 요소들 
    // );

    // // 1. 태그 이름 문자열 type
    // <h1>type 이"태그 이름 문자열" 입니다.</h1>
    // ReactDOM.render(
    //   React.createElement('h1', null, `type 이"태그 이름 문자열" 입니다.`),
    //   document.querySelector('#root')
    // );

    //2. 리엑트 컴포넌트 type 활용
// const Component = () => {
//   return React.createElement('p', null, `type 이 "리액트 컴포넌트" 입니다.`);
// }
//     // compoenet를 #root에다 넣을껀데 윗쪽 정의한 Component 함수에서 들고 온다.
//     // <Component></Compoenet> => <Component/> => <p>type 이 "리액트 컴포넌트" 입니다.</p>
//     ReactDOM.render(
//       React.createElement(Component, null, null),document.querySelector('#root')
//     )

    //3. 리엑트.프레그먼트 
    // 이게 왜 필요 한가? 태그 부분이 없이 바로 자식 부분이 여러게 나올수도 있다 .
    // ReactDOM.render(
    //   React.createElement(
    //     React.Fragment,
    //     null,
    //     `type 이 "React Fragment" 입니다`
    //   ),
    //   document.querySelector('#root')
    // );

     //4. 복잡한 리엑트 엘리먼트 모임 
    //<h1>안녕하세요</h1>
    // 밑에 것을 리액트 방식으로 표현 하기
    // <div>
    //   <div>
    //     <h1>주제</h1>
    //       <ul>
    //         <li>React</li>
    //       </ul> 
    //   </div>
    // </div>
      // 순수하게 자바스크립트로 코딩한 것 
    // ReactDOM.render(
    //   React.createElement('div', null, React.createElement('div', null, React.createElement('h1', null, "주제"), React
    //     .createElement('ul', null, React.createElement('li', null, "React"), React.createElement('li', null,
    //       "Vue"), ))),
    //   document.querySelector('#root')
    // )
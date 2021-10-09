

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
    
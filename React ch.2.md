

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

 //class 컴포넌트 

 import React from 'react';

 //정의

class ClassComponent extends React.Component {
    render() {
      retrun (<div>Hello</div>)
    }
 }
//사용
<ClassComponent/>

//function 컴포넌트 

import React from 'react';

//정의 1
function FunctionComponent() {
  return <div>Hello</div>
}

정의 2
const FunctionComponent = () => <div>Hello</div>;

//사용
<FunctionComponent/> -->

class 컴포넌트 사용법
//정의
 class ClassComponent extends React.Component{
   render() {
     return <div>Hello</div>;
   }
 }

 //사용 
 ReactDOM.render(
   <ClassComponent/>,
   document.querySelector('#root')
 )

//function 컴포넌트 사용법
//정의 1
 JSX 란? 리액트.createElement를 하겠다는 말 
 function FunctionComponent() {
   return <div>Hello</div>;
 }

//사용
 ReactDOM.render(<FunctionComponent/>, document.querySelector('#root'));

//정의 2
 에로우 펑션의 특징은 만약 리턴만 있다면 중괄호와 리턴을 생략 할 수 있다 !
 const FunctionComponent = () => <div>Hello</div>;

 ReactDOM.render(<FunctionComponent/>, document.querySelector('#root'));


React.createElement로 컴포넌트 만들기

 React.creatElement(
   type // 첫번째 인자: 태그 이름 문자열 | 리액트 컴포넌트 | React.Fragment
   [props] //두번째 인자 : 어떤 태그나 리액트 컴포넌트나 크리에이트 앨리먼트 를 데이터를 주입해서 사용 가능 , 리액트 컴포넌트에 넣어주는 데이터 객체
   [...children] //세번째 인자 : 자식으로 넣어주는 요소들 
 );

 1. 태그 이름 문자열 type
 <h1>type 이"태그 이름 문자열" 입니다.</h1>
 ReactDOM.render(
   React.createElement('h1', null, `type 이"태그 이름 문자열" 입니다.`),
   document.querySelector('#root')
 );

2. 리엑트 컴포넌트 type 활용
 const Component = () => {
  return React.createElement('p', null, `type 이 "리액트 컴포넌트" 입니다.`);
 }
compoenet를 #root에다 넣을껀데 윗쪽 정의한 Component 함수에서 들고 온다.
 <Component></Compoenet> => <Component/> => <p>type 이 "리액트 컴포넌트" 입니다.</p>
    ReactDOM.render(
       React.createElement(Component, null, null),document.querySelector('#root')
     )

3. 리엑트.프레그먼트 
 이게 왜 필요 한가? 태그 부분이 없이 바로 자식 부분이 여러게 나올수도 있다 .
 ReactDOM.render(
   React.createElement(
     React.Fragment,
     null,
     `type 이 "React Fragment" 입니다`
   ),
   document.querySelector('#root')
 );

  4. 복잡한 리엑트 엘리먼트 모임 
<!-- <h1>안녕하세요</h1>
 밑에 것을 리액트 방식으로 표현 하기
 <div>
   <div>
     <h1>주제</h1>
       <ul>
         <li>React</li>
       </ul> 
   </div>
 </div> -->
   순수하게 자바스크립트로 코딩한 것 
 ReactDOM.render(
   React.createElement('div', null, React.createElement('div', null, React.createElement('h1', null, "주제"), React
     .createElement('ul', null, React.createElement('li', null, "React"), React.createElement('li', null,
       "Vue"), ))),
   document.querySelector('#root')
 )

 우리가 작성한 어떤 코드를 => 순수하게 실행할 수 있는 자바스크립트
 babel 
 JSX
 JSX 문법으로 작성됭 코드는 순수한 자바스크립트로 컴파일 하여 사용한다.
 누가 해주냐? babel -> 사용하니 코드팬 처럼 자동으로 앨리먼트를 바꿔준다
 맨 처음 <div>는 부모 안의 <div>는 children  

 왜 JSX 을 쓰나요??
 가독성 완승
 바벨과 같은 컴파일 과정에서 문법적 오류를 인지하기 쉬움


JSX 문법 
 최상위 요소는 무조껀 하나만 있어야 한다.
 최상위 요소 리턴하는 경우, ()로 감싸야 한다
 자식들을 바로 랜더링하고 싶으면, <>자식들</>를 사용합니다. => Fragment
 자바스크립트 표현식을 사용하려면, {표현식}를 이용합니다. $ 필요없음
 if문은 사용할 수 없다
 삼항연산자 혹은 && 를 사용한다
 style을 이용해 인라인 스타일링이 가능
 class 대신 className을 사용해야 class를 적용 가능 
 자식요소가 있으면, 꼭 닫아야 하고, 자식요소가 없으면 열면서 닫아야 한다
  <p></p>
  <br/>


props 와 state

props 는 컴포넌트 외부에서 컴포넌트에게 주는 데이터이다.
state 는 컴포넌트 내부에서 변경할 수 있는 데이터이다.
둘다 변경이 발생하면, 랜더가 다시 일어날 수 있다.


Render 함수

Props 와 State 를 바탕으로 컴포넌트를 그린다
그리고 props와 state가 변경되면, 컴포넌트를 다시 그린다
컴포넌트를 그리는 방법을 기술하는 함수가 랜더 함수 이다

 {message: "안녕하세요!!"}

 body에서 <div>를 받아오고 함수에서 <div>랑 <h1>을 받아 온다 

<div><div><h1>"안녕하세요!"" 이것은 함수로 만든 컴포넌트 입니다."</h1></div></div>

 이런 식으로 표현 됌 

 function Component(props) {
   return (
     <div>
       <h1>{props.message} 이것은 함수로 만든 컴포넌트 입니다.</h1>
     </div>
   )
 }

 Component.defaultProps = {
   message : '기본값',
 }

state는 객체 형태로만 존재 

 state를 변경 할때는 규칙이 있다.
 constructor를 사용해도 된다.

 class Component extends React.Component {
 state = {
   count : 0,
 };

 constructor(props) {
   super(props);


   this.state = { count: 0};
 }

 render(){
   return (
     <div>
       <h1>{this.props.message} 이것은 함수로 만든 컴포넌트 입니다.</h1>
      <p>{this.state.count}</p>
     </div>
   )
 }

 라이프 사이클 훅 
 componentDidMount() {
   setTimeout(() => {
       
       this.state.count = this.state.count + 1;
       this.setState({
         count: this.state.count + 1,
       });
         this.setState((previousState) => {
           const newState = { count : previousState.count + 1};
           return newState;
         });
     }, 1000)
   }
    

   static defaultProps = {
       message : '기본값',
   }
 }


 ReactDOM.render(<Component message ="기본값 아님" />, document.querySelector('#root'))
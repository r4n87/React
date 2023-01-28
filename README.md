# React
- [Section 01. Welcome to React](#section-01-welcome-to-react)
- [Section 02. JavaScript for React](#section-02-javascript-for-react)
- [Section 03. Functional Programming with JavaScript]
- [Section 04. How React Works]
- [Section 05. React with JSX]
- [Section 06. React State Management]
- [Section 07. Enhancing Components with Hooks]
- [Section 08. Incorporating Data]
- [Section 09. Suspense]
- [Section 10. React Testing]
- [Section 11. React Router]
- [Section 12. React and the Server]

## Section 01. Welcome to React
### 설명
리액트
- 자바스크립트 라이브러리
- 자바스크립트 안에서 HTML과 같은 코드 작성 가능
- 브라우저에서 실행 시 전처리 필요
- 웹팩과 같은 도구 필요

리액트 기초
- 자바스크립트의 배열, 객체, 함수
- 함수형 자바스크립트
- 컴포넌트를 사용해 사용자 인터페이스를 만듦
- 컴포넌트를 합성(compose)하고 프롭(prop)과 상태(state)를 사용해 로직을 추가
- 리액트 훅스(React Hooks)를 사용해 컴포넌트에 대한 상태 로직 재사용
- 훅스와 서스펜스(Suspense)가 데이터를 읽어올 때 하는 역할
- 라우팅(routing), 테스팅, 서버측 렌더링(server-side rendering) 도구

리액트 도구
- 리액트 개발자 도구: 다른 프로젝트에서 리액트가 어떻게 쓰이는지 배우거나 디버깅할 때 유용
- 노드: Node.js - 풀 스택 애플리케이션을 구축할 수 있는 런타임 환경
- npm: 노드 패키지 관리자 / 여러 패키지를 설치하기 위해 사용
- 얀: npm의 대안 / npm보다 의존 관계를 신뢰성 있게 관리할 수 있도록 도움


## Section 02. JavaScript for React
### 설명
변수 선언
1. const
- 상수
- 값을 변경할 수 없는 변수

2. let
- 구문적 변수 영역 규칙 lexical variable scoping
- let 사용 시 코드 블록 내의 변수로부터 글로벌 변수 보호

3. 템플릿 문자열
- concatenation 대신 사용
- ${}
- 공백(빈칸, 탭, 개행 문자 등) 유지


함수 만들기
1. 함수 선언
- function 키워드로 시작
```
function logCompliment() {
    console.log("잘했어요!");
}

logCompliment();
```

2. 함수 표현식
- 이름 없는 함수를 만듦
- 변수를 값에 대입 가능
- 함수 선언은 호이스팅되지만 함수 표현식은 호이스팅되지 않음
```
const logCompliment = function() {
    console.log("잘했어요!");
};

logCompliment();
```

3. 디폴트 파라미터
- 함수 호출 시 인자값을 지정하지 않으면 디폴트 값을 씀
```
function logActivity(name="raney", activity="swimming") {
    console.log ('${name}은 ${activity}를 좋아합니다.');
}
```

4. 화살표 함수
- ES6에서 추가된 기능
- function 키워드 없이 함수 생성
```
const lordify = function(firstname) {
    return '켄터베리의 ${firstname}';
}

const lordify = firstname => '켄터베리의 ${firstname}'
```
- 파라미터가 2개 이상인 경우
```
const lordify = (firstname, land) => '${land}의 ${firstname}';
```
- 객체를 반환할 경우
```
const person = (firstName, lastName) => ({
    first: firstName,
    last: lastName
});

console.log(person("Raney", "Jang"));
```
- 화살표 함수와 영역


자바스크립트 컴파일
- 컴파일링: 브라우저에서 코드를 실행하기 전에 더 호환성이 높은 코드로 변환
- 컴파일링 도구: 바벨

객체와 배열
- 객체와 배열 안에서 변수의 영역을 제한하는 방법 제공
1) 구조 분해 Destructing
- 객체 안에 있는 필드 값을 원하는 변수에 대입 
- 배열 구조 분해해서 값을 원하는 변수에 대입: 리스트 매칭 사용 가능(불필요한 값에 콤마 사용)
2) 객체 리터럴 개선
- 구조 분해의 반대
- 구조를 다시 만들어내는 과정 또는 내용을 한데 묶는 과정
- 객체 메서드를 만드는 것도 가능
- 더 이상 function 키워드를 사용하지 않아도 됨
```
const skier = {
    name,
    sound,
    powderYell() {
        let yell = this.sound.toUpperCase();
        console.log('${yell} ${yell} ${yell}!!!');
    }
    speed(mph) {
        this.speed = mph;
        console.log('속력(mph):', mph);
    }
}
```
3) 스프레드 연산자 Spread Operator
- 3개의 점으로 이뤄진 연산자
- 스프레드 연산자를 사용해 배열 내용 조합
- 함수 파라미터 정의에서 쓰일 때는 레스트 파라미터 rest parameter


비동기 자바스크립트
1) 단순한 프라미스와 fetch
- fetch() : 데이터를 받아옴
- then() : 데이터가 도착하면 그 데이터를 가지고 다른 일을 함

2) async/await
- const getFakePerson = async() => {let res = await fetch("");}
- 프라미스 호출 앞에 await 키워드를 붙임
- async/await를 사용할 때는 프라미스 호출 주변을 try...catch 블록으로 둘러쌓아 오류 처리

ES6 모듈
- 다른 자바스크립트 파일에서 이름 충돌이 없이 불러 사용할 수 있는 재사용 가능 코드 조각
- 모듈을 한 모듈당 하나씩 별도의 파일로 저장
- 노출방식: 한 모듈에서 여러 자바스크립트 객체를 외부에 노출 / 한 모듈에 하나의 자바스크립트 객체를 외부에 노출
- 커먼JS: 모든 버전의 노드에서 지원하는 일반적인 모듈 패턴

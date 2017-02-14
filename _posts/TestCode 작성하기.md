## Test Code 작성하기

### TEST 방법론
- TDD 방법론
  - 기능별로 작성
- BDD 방법론
  - user가 사용하는 프로세스 방식으로 작성

### TDD
1. 실패하는 테스트 유닛을 만든다.
2. 함수 로직을 만든다.
3. 테스트에 성공한다.

### Tool
- mocha
- should-sinon

### TEST Tool [Mocha]
#### 작성 방식
1. describe()으로 테스트 suite을 만들고 그 안에 it()으로 테스트 코드를 작성한다.
2. descirbe()은 중첩해서 사용할 수 있다.

#### 후커
- before(), after()
: suite 시작 전, 후 한번씩 실행
- beforeEach(), afterEach()
: 테스트 suite 안에 정의한 모든 테스트 코드 실행 전/후마다 실행

#### Exclusive
- describe.only : 이 테스트만 수행
- describe.skip : 이 테스트 skip

#### done
- 비동기 테스트 종료

#### timeout
mocha는 기본적으로 2초이내 테스트를 완료하도록 한다.
수행시간 설정 : this.timeout(1000); //1초내로 수행



#### 참고 사이트
- [mocha 설명] (http://blog.jeonghwan.net/mocha/)

최상단 describe: 파일 이름 + 타입 + 'TestSuite'
그 다음 describe: 사용자가 읽기 쉽게 작성

각 it작업은 독립되야한다.
상세정보 등 선 작업이 필요한 경우 it안에서 실행한다.


### WAS service 작성 방식
- route
  - just api and parameter
- model
  - just db and db's parameter
  - DB작업을 stub하는 것은 의미가 없으므로 직접 쿼리를 작성한다.
- service
  - all test
  이 부분이 좀 헷갈린다. 이번에 변경된 방식인데
  1. service를 사용하지 않는 코드는 안해도 되는가?
  2. service에는 어떤 코드들이 오는거지?
    1. 기존에 어떤거 사용중인지 보고
    2. route에 있는거에서 옮길 수 있는지
    3. model에 있는거에서 옮길 수 있는지
    

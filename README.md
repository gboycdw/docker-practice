# docker-practice

## Intro

### 1. Docker의 탄생 배경 & 필요성

✔️ 기본 배경지식
  - 서버는 24시간 구동해야 함.
  - 다양한 Linux Package, Update 등으로 인해 프로그램 설정이 수시로 달라짐
  - 서버 이전 시 이전할 서버에 맞게 환경 재설정 필요함

✔️ Docker가 왜 좋은가?
  - 흔히 도커로 말아올렸다고 포현하는데, 서버 환경을 감싸서 서버 이전을 하든 프로그램 설정이 달라지든 상관 없이 구동 가능함.

✔️ 서버 구조의 변화와 Docker의 필요성
  - 기존에는 모놀리틱 구조를 사용, 하나의 서버에 모든 기능을 포함함. 한 서비스가 문제를 일으키면 나머지 서비스도 모두 문제 발생.
  - 최신 트렌드는 `Micro Service`로, 여러 서버에 기능을 분산하는 방식을 선호함.
  - 즉, 여러 서버에 기능을 분산하면서 각 서버의 환경을 동일하게 맞춰야 하는 불편함을 Docker가 해소해 준다고 보면 된다.

### 2. DevOps 조직의 탄생

✔️ 조직 구성의 변화
  - 기존에는 개발팀 / 운영팀으로 구성
  - 소통 문제, 잦은 릴리즈, Micro Service로 다분화되며 핸들링해야 하는 서버 수 증가, 서비스 문제 발생, 개발팀과 운영팀의 ping-pong, 퇴사자 속출

✔️ DevOps의 탄생
  - 서버 운영 + 운영 시스템의 효율화/자동화를 전문적으로 수행하는 신규 조직
  - 릴리즈 시스템 자동화, 테스트 자동화, 서비스 모니터링, 코드 리뷰, 이슈 발생 시 커뮤니케이션 시스템 등
  - 요약하면 "Deploy"의 전문가 집단이라고 보면 된다.

✔️ Docker와 Kubernetes
  - 각 Micro Service를 동일한 환경에서 구동하기 위해 `Docker` 사용
  - 매우 거대한 서비스 유지보수를 위한 서버 핸들링을 위해 `Kubernetes` 사용
  
✔️ CI/CD
  - CI : Continuous Integration
  - CD : Continuous Delivery(또는 Deployment)
  - 개발자가 작업을 해와서 그 내용을 서비스에 반영하고 싶으면? 업데이트를 해야겠지? 그 과정을 자동화 하는 것이 CI/CD라고 보면 된다.
  - 엄밀하게 구분을 하자면, CI는 새로 작성된 코드의 오류 테스트와 build 작업이고, CD는 build 완료된 코드를 배포하는 작업이라고 보면 되겠다.
  - 새로 배포되는 과정에서 서버가 재가동되면 짧은 시간이지만 서비스가 먹통이 되는데, 이걸 방지하는 걸 `무중단 배포`라고 한다.
  - 이 모든 과정의 기본이 `Docker`라는 것임.
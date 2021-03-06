# 진행한 프로젝트

## 관리자 기능 - 파일 업로드

- 빗썸은 망분리가 외부, 내부, 인터넷망 이렇게 3개로 나누어져 있고, 이벤트 메일 발송용 템플릿을 생성해야되는데 내부망에서 이미지 업로드 하고, 그 업로드 한 이미지의 링크를 외부망으로 옮겨적은 후 템플릿 만드는 작업이 너무 번거로웠음

- 그래서 기획팀을 통해 간단하게 이미지 업로드 후 html 로 페이지 생성하여 html 그 생성된 html 파일만 외부망으로 전달하면 되는 프로세스를 만들어 기능 요청을 하였음

- 회사 들어갔던 첫 단기 프로젝트였고, 일정이 급하진 않았음

- 실무 담당자로 부터 기획서에 없는 기능 추가를 요청받았는데, 업로드 된 파일의 위치를 드래그&드랍으로 옮길 수 있게 하는 기능이었고, 큰 공수가 들지 않을 것 같아 그 자리에서 바로 Ok 해버림 (할 수 없는건 없다! 모든지 가능하다~ 식으로 패기롭게 얘기함)

- 구두로 전해진 기능이다 보니, 어디까지 원하는 지지 몰랐고 기획팀에 재요청하여 해당 기능에 대한 확인을 다시 받음

- 이후에 완료하여 기능 검수 완료했고, 다음부터는 작업을 할 때 항상 추가 기능에 대한 일정 재확인이 필요하다는 것을 알았음

- PHP 와 Javascript 모두 다루는 일이었고, 소스 파악 후 진행하였고, Jquery 기반의 라이브러리를 사용해 드래그&드랍 기능을 구현했음


## 빗썸 코인쿠폰

- 빗썸 메인 서비스에 추가되는 기능 이었음

- 기존에 수수료 쿠폰이 있지만, 수수료 쿠폰 갯수 증가와 비트코인 쿠폰 (구매하고 등록하면 비트코인이 충전되는 시스템) 시스템을 추가하는 프로젝트

- 백엔드 담당이었고, 실제 코인 쿠폰이 이루어지는 결제 부분에 대한 담당이었음

- 개인적인 사정으로 휴가를 내어 기획을 완전히 다 알지 못하는 상태에서 프로젝트 투입이 되었음

- 코인쿠폰 구입 시, 외부 쇼핑몰에서 구입을 하고, 등록할 때 특정 업체(외부 쇼핑몰)가 보유하고 있는 비트코인이 증거금으로 먼저 잡고 이후 체결 시 업체가 보유하고 있는 코인이 회원의 코인계좌로 입금이 된다.

- 코인쿠폰을 등록할 때 현재 시세로 환산하여 계산된다.

- 쿠폰 내역 조회에 대한 EndPoint 를 만듦

- Front-End 쪽에서도 QA 기간에 검수하여 이중으로 등록되는 버그를 찾았고, 이후에 Select ~ For Update 구문을 활용해서 해결했음

- 추후에 잡았던 증거금이 해제가 안되는 버그가 발생하여 코인 쿠폰 등록이 안되는 버그가 발생했는데, 매출에 심각하게 영향을 주는 버그는 아니었고 이후에 본인이 긴급하게 해결하였음


## 빗썸 알림서비스

- 기존의 서비스에서 EndPoint 추가하는 작업을 하였고 그 과정에서 시세 알림, 지정가 알림, 급등락 알림 및 공지 알림 등의 알림 서비스가 생겼음

- 하드코딩된 템플릿을 DB에 저장하여 템플릿 화 하는 방식으로 재설계하였으며, 그 과정에서 ehcache 패키지를 도입하여 적용하였음

- 기존 코인 정보는 스프링부트의 @Scheduled Annotation 을 사용하여 가지고 오고 있음.

- 외주 API 매뉴얼 파악 및 연동하는 작업을 주로 했고, 그 과정에서 REST API 설계 문서를 작성하여 팀내 공유하였음.

- 서비스 모니터링은 제니퍼를 사용해서 하고있음

- 서비스 오픈 이후 예기치 못하게 상당히 많은 수의 알림 요청으로 인해 DB Insert 부분에서 성능상의 문제가 발생했는데, 알림푸시 등록은 mysql 로 등록하고 있었기 때문에 해당 부분에서 DB Connection Pool 에서 지연 현상이 발생함

- 특정 EndPoint 에 대해 새로운 JDBC Connection Pool 을 만들고, UNION ALL 구문을 이용해서 요청한 DB Insert 처리를 한꺼번에 처리하도록 작업하였음

- 서비스 구조는 Controller, Repository(dto, vo 존재), Service 단으로 나누어져 있고, 공통 라이브러리는 Nexus 저장소를 사용했으며, Core Library 가 별개로 존재하여 gradle 빌드 시 받아옴


## 멀티 DEV/QA 서버 환경 구성

- PHP 기반 환경의 서비스에서 지라 티켓별로 유지보수 할 수 있는 환경 구성

- 개발자는 온전히 자신이 수정한 코드만을 볼 수 있어, 다른 개발자 코드가 자신의 작업물에 영향이 갈 일이 없음

- Bamboo(CI/CD 툴) 와 Apache 동적 디렉터리 기능을 사용한 간단한 구현

- 이후엔 hostsman(window) / gasmask(mac) 를 사용해 호스트 설정해서 사용할 수 있는 방법을 전사에 공유


## 빗썸오피셜 취약점 조치

- ISMS 인증 심사 기간으로 인해 취약점 조치를 해야되서 작업

- 관리자 관리 기능 추가

- 로그인 & 로그아웃 & 패스워드 변경에 대한 기록이 남을 수 있는 테이블 설계

- GET 과 POST 를 혼용하여 데이터를 전송하는 부분에 대해 모두 POST 로 전환

- 패스워드 90일 강제 변경 기능 추가하여 90일이 지나거나 패스워드 변경을 하지 않으면 로그인이 안되도록 설계

- 전에 사용했던 패스워드는 사용하지 못하게 수정했음


## 각 서비스 배포 환경 구성

- 자바로 시작하는 많은 프로젝트들에 대한 배포 환경 구성

- Jenkins Pipeline Script 를 템플릿화 하여 공통적으로 배포환경 구성하였음

- DEV / QA / Perform(선택) / Prod 에서 각각 확인

- Java8 / Java11 프로젝트


## AML 솔루션 배포

- Maven 도 아니고 Gradle 도 아닌 서비스에 대해 CI/CD 적용

- 처음엔 개발하는 담당자도 어떻게 빌드가 되는지 모르겠다 이클립스로 하면 자동으로 빌드 된다고 해서 멘붕

- 좀 더 파악해보고 검색해본 결과 Ant Build 라는 것을 알게되었고, build.xml 에 설정된 메인 클래스를 실행

- 이후 Health Check 를 위한 End-Point 요청 후 확인하여 배포 확인 완료했음


## 코인힐즈 서비스 배포

- PHP 로 구성되어있지만 별도의 프레임 워크가 없는 서비스

- Api / Batch / Web 소스가 나누어져 있음

- 별도의 서버를 새로 발행하고 이후에 DNS 를 교체하는 형태로 서비스 배포가 이루어짐

- DEV 와 Prod 서버만 존재하고 QA 환경이 없어 서버 발급 요청

- 배포 하는데 DEV 와 Prod 다르게 설계되어 있고 설정값이 분기처리 되어있지 않아 개발자에게 요청함

- 서비스 경로가 제각각 이어서 DevOps 룰에 맞게 경로 변경 했음

- 이후 서비스 배포 이후 nginx reload 로 서버 설정 적용함

- 근데 서버 설정의 경우엔 인프라팀에서 관리하는 거라 nginx reload 하니까 에러 터짐

- 원인 파악이 인프라팀 외에는 안됐고, 서버 설정해달라고 본인이 요청했다면서 본인이 잘못한 걸로 몰아감

- 데브옵스 파트장님은 그 부분에 대해 인지했고, 인프라팀에서 nginx reload 하지 않고 DevOps 에서 서버 설정 관리할 수 있게 링크(ln) 으로 nginx.conf 연결해서 서버 설정함

- 젠킨스 서버 재실행 권한 부여해서 배포 때 마다 nginx reload 할 수 있게 설계 후 배포하였음
# 진행한 프로젝트

## 빗썸 알림서비스

- 기존의 서비스에서 EndPoint 추가하는 작업을 하였고 그 과정에서 시세 알림, 지정가 알림, 급등락 알림 및 공지 알림 등의 알림 서비스가 생겼음

- 하드코딩된 템플릿을 DB에 저장하여 템플릿 화 하는 방식으로 재설계하였으며, 그 과정에서 ehcache 패키지를 도입하여 적용하였음

- 기존 코인 정보는 스프링부트의 @Scheduled Annotation 을 사용하여 가지고 오고 있음.

- 외주 API 매뉴얼 파악 및 연동하는 작업을 주로 했고, 그 과정에서 REST API 설계 문서를 작성하여 팀내 공유하였음.

- 서비스 모니터링은 제니퍼를 사용해서 하고있음

- 서비스 오픈 이후 예기치 못하게 상당히 많은 수의 알림 요청으로 인해 DB Insert 부분에서 성능상의 문제가 발생했는데, 알림푸시 등록은 mysql 로 등록하고 있었기 때문에 해당 부분에서 DB Connection Pool 에서 지연 현상이 발생함

- 특정 EndPoint 에 대해 새로운 JDBC Connection Pool 을 만들고, UNION ALL 구문을 이용해서 요청한 DB Insert 처리를 한꺼번에 처리하도록 작업하였음

- 서비스 구조는 Controller, Repository(dto, vo 존재), Service 단으로 나누어져 있고, 공통 라이브러리는 Nexus 저장소를 사용했으며, Core Library 가 별개로 존재하여 gradle 빌드 시 받아옴

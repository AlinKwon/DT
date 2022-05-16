
# Dev with SAAS    

###  1계명: 버전 관리되는 하나의 코드베이스와 다양한 배포를 지원하라.
###  2계명: 명시적으로 선언되고 분리된 종속성으로 관리하라.
###  3계명: 환경에 저장된 설정을 구성하고 사용하라.
###  4계명: 백엔드 서비스를 연결된 리소스를 취급하라.   
###  5계명: 빌드, 릴리즈, 실행을 철저하게 분리하라.
###  6계명: 프로세스는 무상태(Stateless)로 실행하라.
###  7계명: 포트로 서비스를 구분하라.
###  8계명: 수평적 확장을 위한 동시성을 고려하라.
###  9계명: 빠른 시작과 우하한 종료(graceful shutdown)를 지원하라.
### 10계명: 개발과 운영 환경을 최대한 같게 유지하라.
### 11계명: 로그를 이벤트 스트림으로 취급하라.
### 12계명: 별도에 설치나 구성없이 관리 프로세스를 실행할 수 있게 하라.
------------
### 13계명: 모든 의존성은 주입되어야 하며, 주입된 의존성은 테스트에 포함되지 않게 하라.
<hr>

## For 12 factor    
### 1. Codebase     
```
1계명: 버전 관리되는 하나의 코드베이스와 다양한 배포를 지원하라.
```
소스의 히스토리는 너의 어버이를 알고 자식을 알 수 있게 함이라.
> Gitlab

### 2. Dependencies
```
2계명: 명시적으로 선언되고 분리된 종속성으로 관리하라.
```
모든 개발자가 동일한 버전에 종속성을 가질수 있게 함이라.

> go.mod , go.sum

### 3. Config
```
3계명: 환경에 저장된 설정을 구성하고 사용하라.
```
너의 소스에 구성정보를 포함하지 않게 함이라.    
> volt

> [Viper](https://github.com/spf13/viper)
![Viper](https://github.com/spf13/viper/blob/master/.github/logo.png?raw=true)  
Go configuration with fangs!


> [COBRA](https://github.com/spf13/cobra)   
![cobra logo](https://cloud.githubusercontent.com/assets/173412/10886352/ad566232-814f-11e5-9cd0-aa101788c117.png)
cobra logo
Cobra is a library for creating powerful modern CLI applications.

Cobra is used in many Go projects such as Kubernetes, Hugo, and Github CLI to name a few. This l                                                                                                                                                                                                                    
### 4. Backing services
```
4계명: 백엔드 서비스를 연결된 리소스를 취급하라.   
```
백엔드 서비스에 종속되지 않게 함이라. 이는 같은 회사에 서비스에도 차별없이 적용할 지어다.
> ORM solution, gorm, ent

### 5. Build, release, run 
```
5계명: 빌드, 릴리즈, 실행을 철저하게 분리하라.
```
각 부분에서 롤백할 수 있는 역량을 가지게 함이라.    
* 빌드: 실행가능한 번들로 변환
* 릴리즈: 설정과 결합
* 실행: 애플리케이션 프로세스의 집합을 시작하고 실행환경에서 구동


### 6. Process
```
6계명: 프로세스는 무상태(Stateless)로 실행하라.
```
동일한 값에 의한 호출이 동일한 응답을 받을 수 있게 함이라.
> memcashed, redis


### 7. Port binding
```
7계명: 포트로 서비스를 구분하라.
```
설정으로 너의 서비스를 찾을 수 있게 함이라.
> kubernetes, docker swarm, nomade


### 8. Concurrency
```
8계명: 수평적 확장을 위한 동시성을 고려하라.
```
아무것도 공유하지 않고, 수평으로 분할 할 수 있는 서비스를 만들기 위함이라.

> go rutine

### 9. Disposability
```
9계명: 빠른 시작과 우하한 종료(graceful shutdown)를 지원하라.
```
이는 너의 서비스에 안정성을 극대화 하기 위함이라.
하드웨어 에러에 의한 갑작스러운 죽음에도 견고하게하라.

> Beanstalkd와 같은 요청을 큐로 되돌릴 수 있는 기능 지원.


### 10. Dev/prod parity
```
10계명: 개발과 운영 환경을 최대한 같게 유지하라.
```
PC 환경이외에 인적, 물적 환경도 고려하라.
테스트의 강건성을 지켜주기 위함이라.

> vagrant , web dev, cloud dev


### 11. Log
```
11계명: 로그를 이벤트 스트림으로 취급하라.
```
로그 스트림을 처리하는 것은 로그 정책에 맡겨라.
로그는 분석되고 인사이트를 줄것이다.
진단 테이타도 로그로 간주하라. 
> logstash

### 12. 관리프로세스
```
12계명: 별도에 설치나 구성없이 관리 프로세스를 실행할 수 있게 하라.
```
원격 명령어 실행 매커니즘을 통해 관리를 강화하라.

> script file for REPL Shell

------------

### 13. Test
```
13계명: 모든 의존성은 주입되어야 하며, 주입된 의존성은 테스트에 포함되지 않게 하라.
```
> gomock, testify, GoConvey

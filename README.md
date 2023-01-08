# AWS_basic

#### 이 Repository는 Inflearn '노마드 콘텐츠 랩'의 '스스로 구축하는 AWS 클라우드 인프라 - 기본편' 의 강의 내용을 개인적으로 정리한 것입니다.  
  
### 아키텍처 관련 기술/서비스/다이어그램/구현 순서 검토  
Amazon S3(Simple Storage Service)  
Amazon CloudFront  
			
(1) S3 Bucket 생성 및 정적 웨사이트 호스팅  
  _1: S3 Bucket 생성  
  _2: Object(File) 업로드  
    > mycar.html  
    > car.jpg  
  _3: 정적 웹 사이트 호스팅 기능 활성화  
  _4: Bucket과 Object에 대한 액세스 정책 설정  
  _5: 웹 브라우저에서 웹 사이트 작동 확인  
  
(2) CloudFront를 통한 웹사이트 성정 가속화  
  _1: CloudFront Distribution 생성  
    > Origin, Cache behavior 등 설정  
  _2: 웹 브라우저에서 CloudFront Distribution 작동 확인  
  _3: 웹 사이트 성능 테스트  
    > S3 정적 웹 사이트 호스팅을 통한 콘텐츠 로드 속도  
    > CloudFront를 통한 콘텐츠 로드 속도  
    
### LAMP 웹 서버 및 Application Load Balancer 구성  
1) 기본 네트워크 환경 구성(VPN/Subnet/Interner Gatway/Route Table)
  - VPC 생성
  - Subnet 생성
  - Interner Gatway 생성
  - Route Table 생성 및 Route 설정

2) Public EC2 인스턴스 생성 및 LAMP 웹서버 구성
  - EC2 생성
    > AMI
    > LAMP 웹 서버 구성
    > Security group
    > Stroage
    > Key pair
  - Index.php 파일 생성
  - 웹 브라우저에서 LAMP 웹 서버 작동 테스트

3) Custom AMI를 통한 Pulbic EC2 인스턴스 생성
  - Custom AMI 생성
  - Custom AMI를 통해 EC2 추가 생성
  - 웹 브라우저에서 LAMP 웹 서버 작동 테스트

4) EFS를 통한 네트워크 파일 시스템 구성
  - EFS용 Security group생성
  - EFS 생성
    > Availability
    > Lifecycle
    > Performance/Throughput mode
    > Network 등
  - EFS-EC2 마운트
  - 웹 브라우저를 통한 EFS 마운트 테스트

5) Application Load Balancer를 통한 이중화 네트워크 구성(1)
  - Target group 생성
    > Target type
    > Protocol/Port
    > Target registration 등
  - Application Load Balancer 구성
    > Scheme
    > Network
    > Security group
    > Listener/Rule 등
  - 웹 브라우저를 통한 Application Load Balancer 작동 테스트

6) Bastion host와 NAT Gateway를 통한 Private EC2 인스턴스의 외부 통신 구성  
> Private subnet에 EC2 생성
> Private subnet의 EC2를 통해 접속(+key pair 생성)
> NAT Gateway 생성
> Route table 설정
> Private subnet의 EC2의 외부 통신 테스트

7) Application Load Balancer를 통한 이중화 네트워크 구성(2)  
> Target group 생성
> Application Load Balancer 구성
> 웹 브라우저를 통한 테스트

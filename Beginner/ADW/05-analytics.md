![oracle-auto](./img/oracle-auto.png)

# 05 - Analytics : 이제 분석을 해볼까요?

## 실습 소개

본 실습은 오라클 클라우드를 시작하기 위해 콘솔 대시보드를 접속하고 살펴봅니다.

이 가이드는 Oracle Autonomous Data Warehouse Cloud(ADWC)에서 제공하는 기능들을 준비된 시나리오에 따라 실습을 하여 ADWC 에 대한 폭 넓은 이해와 함께 직접 경험 할 수 있도록 구성되었습니다.

가장 먼저 ADWC 를 프로비저닝 하는 방법에서 부터, Oracle SQL Developer 를 이용해 데이터베이스 접속 후 샘플 데이터를 이용하여 쿼리 수행, 성능 테스트, 워크로드를 관리하는 방법 등 ADWC 에서 제공되는 서비스들을 학습합니다.

이후 각 로컬 PC 에 다운로드 받은 샘플 데이터 파일을 ADWC 에 직접 로딩 후 해당 데이터의 시각화를 위해 툴을 연결 및 설정하고 대시보드를 생성하는 실습 또한 함께 진행합니다.

이번 실습을 통해서 Autonomous Data Warehouse Cloud 가 제공하는 확장성 및 탄력성 등에 대해서 체험할 수 있습니다

가이드에 뒷부분에 제공되는 추가 실습을 통해서 Cloud Object Storage Service 에서 실제 데이터를 로딩 하는 방법, 인스턴스 관리 및 모니터링 방법 등을 실습하며 보다 심층적인 ADWC 서비스 기능들을 체험할 수 있습니다.

마지막으로 ADWC 의 가장 강력한 기능 중의 하나인 Oracle 에서 제공하는 새로운 notebook 어플리케이션을 이용해 Oracle Machine Learning 을 체험하게 됩니다.

본 가이드는 강사와 함께 실습이 진행되며 강사의 도움을 받아 진행하 실 수 있습니다.

Lab 가이드 원본(영문)을 보시려면 다음 링크를 통해 확인 할 수 있습니다.
[adwc4dev of Oracle GitHub](https://github.com/oracle/learning-library/tree/master/workshops/adwc4dev)

## 실습 목표

- Oracle Cloud Console 접속 및 기능 살펴보기

## 사전 준비 사항

- 웹 브라우저
  - Microsoft Internet Explorer 11+
  - Google Chrome 63+
  - Mozilla Firefox 52+
  - Apple Safari 10+
- 오라클 클라우드 어카운트 (Oracle Cloud Account)
  - 오라클 클라우드 어카운트는 본 세션에 신청하신 이메일로 안내 메일이 전송 되었습니다.
    - **Welcome to ~~** 라는 제목으로 no-reply@oracle.com에서 안내 메일이 발송되었습니다.
  - 오라클 클라우드 어카운트는 오라클 클라우드의 IaaS, PaaS 등 솔루션을 생성하고, 운영하는 공간을 의미합니다.

# Steps

**Note:** 본 가이드에서 제시하는 화면과 실습하시는 분의 계정 상세정보가 다를 수 있습니다. (예: Compartment Name) 

### **STEP 1:  Oracle Cloud 접속**

- 브라우저에서 **[cloud.oracle.com](https://cloud.oracle.com)**로 이동하여 `Sign In`  아이콘을 클릭합니다.
  ![cloud.oracle.com](/Users/haje/Documents/workspace/ADWCML/Beginner/ADW/img/00-sign-in/01.png)

  ![Sign In](/Users/haje/Documents/workspace/ADWCML/Beginner/ADW/img/00-sign-in/02.png)





- `Cloud Account Name `을 입력하고, `Next` 클릭합니다.
  ![](/Users/haje/Documents/workspace/ADWCML/Beginner/ADW/img/00-sign-in/03.png)

  ![](/Users/haje/Documents/workspace/ADWCML/Beginner/ADW/img/00-sign-in/04.png)





- 계정 정보를 입력 후,    `Sign In` 클릭합니다.

  ![](/Users/haje/Documents/workspace/ADWCML/Beginner/ADW/img/00-sign-in/05.png)



- Hello World! 오라클 클라우드에 오신 것을 환영합니다!

  ![](/Users/haje/Documents/workspace/ADWCML/Beginner/ADW/img/00-sign-in/06.png)




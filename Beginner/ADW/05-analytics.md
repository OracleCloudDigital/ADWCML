![oracle-auto](./img/oracle-auto.png)

# 05 Analytics : 이제 분석을 해볼까요?

## 실습 소개

앞에서는 자율 운영 데이터 웨어하우스를 생성도 하고 모니터링과 쿼리 날리는 방법도 익혔습니다.
이제 본격적으로 데이터를 분석하는 방법을 알아봅니다.
쉽게 접근할 수 있도록 준비하였습니다.

## 실습 목표

- Oracle Autonomous Data Warehouse와 Oracle Analytics Cloud를 통해 데이터를 분석 하기
- Cloud Wallet 만들어 보고 사용하기
  - Cloud Wallet은 자율 운영 데이터 웨어하우스를 사용하기 위해서 사용자 자격 증명 서비스입니다.

## 사전 준비 사항

- 오라클 분석 클라우드 (Oracle Analytics Cloud)
- 자율 운영 데이터 웨어하우스 (Oracle Autonomous Data Warehouse)
- ~~데이터베이스 지식~~
  - 아주 아주 간단한 Query Syntax (SELECT / FROM만 알아도 괜찮아요)
- 웹 브라우저
  - Microsoft Internet Explorer 11+
  - Google Chrome 63+
  - Mozilla Firefox 52+
  - Apple Safari 10+
- 오라클 클라우드 어카운트 (Oracle Cloud Account)

# Steps

### **STEP 1:  ADW Cloud Wallet 생성**

- 생성한 adwoac0의 Oracle Autonomous Database 화면으로 접속 후, `DB Connection`을 선택합니다.
  ![cloud.oracle.com](./img/06-create-adw-wallet/01.png)

  

- `Download `를 선택합니다.
  ![cloud.oracle.com](./img/06-create-adw-wallet/02.png)

  

- 패스워드를 입력 후, `Download`를 선택합니다. zip 형태의 Cloud Wallet 파일이 다운로드 됩니다.

  Password: Oracle987654
  
  ![cloud.oracle.com](./img/06-create-adw-wallet/03.png)



### **STEP 2:  Oracle Analytics Cloud 생성**

- Oracle Cloud Dashboard Console로 돌아옵니다.
  
https://console.eu-frankfurt-1.oraclecloud.com/
  
  ![cloud.oracle.com](./img/07-oac/01.png)



- 좌측 상단의 햄버거 메뉴를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/02.png)

  



- My Services Dashobard를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/03.png)

  



- Cloud My Services Dashboard 입니다.

  ![cloud.oracle.com](./img/07-oac/04.png)

  

- 좌측 상단의 햄버거 메뉴를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/05.png)

  



- Analytics를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/06.png)

  



- Analytics Cloud 관리창입니다.

  ![cloud.oracle.com](./img/07-oac/07.png)

  



- Create Instance를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/08.png)

  



- Instance Name만 입력하고, 나머지는 기본값으로 둔 채 Next를 선택합니다.

  Instance Name: adwoac0~n

  ![cloud.oracle.com](./img/07-oac/10.png)

  

- 생성할 정보를 다시 한 번 확인하고, Create를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/11.png)

- Status가 Creating service 상태인 것을 확인 할 수 있습니다.

  Status가 사라지면 생성 완료 상태입니다.

  ![cloud.oracle.com](./img/07-oac/12.png)





- Oracle Analytics Cloud 서비스를 이용해보도록 하겠습니다.

  먼저 생성된 adwoac0의 우측의 메뉴 아이콘을 선택합니다.

  ![cloud.oracle.com](./img/07-oac/13.png)

  

- Oracle Analytics Cloud URL을 선택합니다.

  ![cloud.oracle.com](./img/07-oac/14.png)

  



- 환영합니다! Oracle Analytics Cloud 입니다.

  ![cloud.oracle.com](./img/07-oac/15.png)

  







### **STEP 3:  Oracle Analytics Cloud로 쉽게 대시보드 만들기**

- Oracle Analytics Cloud 서비스 화면에서 `Create`  아이콘을 선택합니다.
  ![cloud.oracle.com](./img/07-oac/16.png)



- `Data Set (데이터셋)` 을 선택합니다.
  ![cloud.oracle.com](./img/07-oac/17.png)



- 파일을 업로드 하기 위하여 `Drop data file here or click to browse`  아이콘을 선택합니다.
  ![cloud.oracle.com](./img/07-oac/18.png)





- 미리 다운로드 했던 `finance_manager.xlsx` 를 선택합니다.
  ![cloud.oracle.com](./img/07-oac/19.png)





- EXCEL 파일을 Oracle Analytics Cloud에 저장하고자 합니다. Name 수정하고, 파일의 데이터를  살펴 보고 `Add` 를 선택합니다.

  Name: finance_manager-이름 이니셜 

  ![cloud.oracle.com](./img/07-oac/20.png)





- 파일의 데이터를 클라우드(Oracle Analytics Cloud)에 저장하였습니다.

  ![cloud.oracle.com](./img/07-oac/21.png)





- 아주 간단한 데이터 전처리를 해볼까요?

  `요일`을 뽑아봅시다. 어떻게 할까요?
  쉽습니다! Oracle Analytics Cloud는 자동으로 추천해줍니다. 추천 리스트 중에  `Extract Day of Week from Month` 를 선택합니다.
  Python에서 같은 작업을 할 때는 DataFrame 라이브러리를 사용하여 조금은 코드를 구성해야 하는데, 여기서는 간단한 몇 번의 클릭으로 처리가 가능하죠.

  ![cloud.oracle.com](./img/07-oac/22.png)

  ![cloud.oracle.com](./img/07-oac/23.png)





- 요일 컬럼의 이름을 변경해볼까요.

  컬럼에 마우스를 가까이 간 후에 메뉴 버튼을 선택합니다. 그리고 Rename을 선택합니다.

  ![cloud.oracle.com](./img/07-oac/24.png)





- Name에 Day of Week 또는 요일을 입력하고 Add Step을 선택합니다.

  ![cloud.oracle.com](./img/07-oac/25.png)

  

- 컬럼명이 바뀌었는지 확인 후, 본격적으로 간단한 데이터 분석을 해보겠습니다.
  Create Project를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/26.png)





- 첫 프로젝트입니다. 새 하얀 대시 Canvas를 어떻게 채울까요?
  조금은 막막할 수 있을 것 같아요. 걱정 하지 마세요. 어렵지 않게 추가해보는 방법을 알아 보도록 할게요!
  Oracle Analytics Cloud는 데이터를 살펴 보고 연관성 있는 데이터를 그래프로 제시해줍니다!

  ![cloud.oracle.com](./img/07-oac/27.png)

  



- 왼쪽에 입력한 데이터 컬럼명들이 보입니다.
  Expense Amount 컬럼에서 마우스 우클릭을 합니다.

  Explain Expense Amount를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/28.png)

  



- 데이터를 살펴보고 제시해주는 그래프를 선택해보도록 합니다.

  그래프에 마우스 커서를 올리면 체크 박스가 나타납니다. 체크해봅니다.
  왼쪽에 Basic Facts about Expense Amount와 Anomalies of Expense Amount에 여러 그래프를 살펴 보아요.
  그리고 자유롭게 원하시는 그래프를 선택한 후에 Add Selected를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/29.png)

  ![cloud.oracle.com](./img/07-oac/30.png)

  ![cloud.oracle.com](./img/07-oac/31.png)

  

- 아주 간단하게 대시보드가 구성되었습니다!

  ![cloud.oracle.com](./img/07-oac/32.png)

  





### **STEP 4:  Oracle Analytics Cloud 대시보드 분석하기**



- 이번에는 이미 구성된 대시보드를 살펴볼 거에요.

  현재 화면에서 상단 좌측의 햄버거 메뉴를 선택 후, `Projects`를 선택합니다.

  ![cloud.oracle.com](./img/07-oac/33.png)





- `Shared Folders > 재무 관리 > 수익/비용 `을 선택합니다.

  ![cloud.oracle.com](./img/07-oac/34.png)

  ![cloud.oracle.com](./img/07-oac/35.png)

  ![cloud.oracle.com](./img/07-oac/36.png)

  ![cloud.oracle.com](./img/07-oac/37.png)





- `캔버스 `는 여러 차트를 생성하여 목적에 따라 구별하여 생성할 수 있습니다.
  그리고 생성된 캔버스는 하단에 캔버스 탭에서 생성 및 이동이 가능합니다.

  ![cloud.oracle.com](./img/07-oac/38.png)

  



- `데이터 분석`을 시작해보아요.

  연간 매입, 매출이 증가하고 있지만 당기순이익은 하락하고 있습니다.

  ![cloud.oracle.com](./img/07-oac/39.png)





- 아마도 영국의 운영 비용이 전년 대비 증가해서 일까요?

  ![cloud.oracle.com](./img/07-oac/40.png)

  





- 매출 캔버스로 이동해보았습니다.

  ![cloud.oracle.com](./img/07-oac/41.png)

  





- 상품 카테고리 별 매출이 보이네요.

  ![cloud.oracle.com](./img/07-oac/42.png)

  





- 상품 카테고리 별 매출이 보이네요.

  프린터가 제일 잘 나가네요.

  ![cloud.oracle.com](./img/07-oac/42.png)

  





- OPEX 캔버스로 이동합니다.

  ![cloud.oracle.com](./img/07-oac/43.png)

  







[첫 페이지로 돌아가기](./README.md)

[이전 핸즈온으로 돌아가기](04-query-adw.md)

[다음 핸즈온으로 넘어가기](06-machine-learning.md)
# Database
>## 1.2 Purpose of Database Systems
>### 기존 file-processing system(The system stores permanent records in various files, and it needs different application programs to extract records from, and add records to, the appropriate files.)이 가지는 문제를 해결하는 것.
>- Data redundancy and inconsistency.
  >   -  여러 파일에 중복된 데이터 또는 같은 요소에 다른 데이터가 들어있는 문제.
>- Difficulty in accessing data.
  >   - 여러 파일에 저장되어 있는 데이터로 인해 원하는 데이터에만 접근하기 어려운 문제.
>- Data isolation.
  >   - 여러 파일에 데이터가 저장되어 원하는 데이터를 찾기 힘든 문제.
>- Integrity problems.
  >   - ?
>- Atomicity problems.
  >   - 모 아니면 도를 유지해야 하는 문제.
>- Concurrent-access anomalies.
  >   - 동시에 데이터에 접근할때 발생하는 문제.
>- Security problems.
  >   - 특정 사용자만 접근을 허용해야 하는 경우.
> ## 위의 문제를 해결하는 방향으로 현재의 데이터베이스 시스템이 발전되었다.

<br/><br/>

>## 1.3 View of Data
>데이터베이스 시스템의 주요 목적 중 하나는 사용자에게 추상화된 데이터의 관점을 제공하는 것.
>>Data Abstraction
>>-  Physical level : 데이터가 어떻게 저장되는지 묘사하는 단계.
>>-  Logical level : 어떤 데이터가 저장되는지, 그들 사이의 관계를 어떤지를 묘사하는 단계.
>>-  View level : 전체 중 일부만 보여주는 단계. 데이터베이스 시스템과 간단한 상호작용만 존재.
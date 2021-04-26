# Database

> ## 1.2 Purpose of Database Systems
>
> ### 기존 file-processing system(The system stores permanent records in various files, and it needs different application programs to extract records from, and add records to, the appropriate files.)이 가지는 문제를 해결하는 것.
>
> - Data redundancy and inconsistency.
>   - 여러 파일에 중복된 데이터 또는 같은 요소에 다른 데이터가 들어있는 문제.
> - Difficulty in accessing data.
>   - 여러 파일에 저장되어 있는 데이터로 인해 원하는 데이터에만 접근하기 어려운 문제.
> - Data isolation.
>   - 여러 파일에 데이터가 저장되어 원하는 데이터를 찾기 힘든 문제.
> - Integrity problems.
>   - ?
> - Atomicity problems.
>   - 모 아니면 도를 유지해야 하는 문제.
> - Concurrent-access anomalies.
>   - 동시에 데이터에 접근할때 발생하는 문제.
> - Security problems.
>   - 특정 사용자만 접근을 허용해야 하는 경우.
>
> ## 위의 문제를 해결하는 방향으로 현재의 데이터베이스 시스템이 발전되었다.

<br/><br/>

> ## 1.3 View of Data
>
> 데이터베이스 시스템의 주요 목적 중 하나는 사용자에게 추상화된 데이터의 관점을 제공하는 것.
>
> > ### Data Abstraction
> >
> > - Physical level : 데이터가 어떻게 저장되는지 묘사하는 단계.
> > - Logical level : 어떤 데이터가 저장되는지, 그들 사이의 관계를 어떤지를 묘사하는 단계.
> > - View level : 전체 중 일부만 보여주는 단계. 데이터베이스 시스템과 간단한 상호작용만 존재.

> > ### Instances and Schemas
> >
> > - Instance : 특정 순간에 저장되는 정보집합.
> > - Schema : 전체적인 데이터베이스 설계.

> ## 1.4 Database Languages
>
> > - Data-definition language (DDL) : 데이터베이스 스키마와 데이터의 특성을 규정하는 언어.
> >   - Domain Constraints : 데이터타입 제한.
> >   - Referential Integrity : 하나의 관계에서 나타나는 값이 다른 관계에서도 동일하게 나타나야 한다.
> >   - Authorization : 데이터에 대한 권한.
> >   - DDL의 결과는 Data Dictionary에 보관되고, Data Dictionary는 metadata(데이터에 대한 데이터)를 포함한다.
> >   - 데이터베이스 시스템은 쓰거나, 수정하기 전에 Data Dictionary를 참고한다.
> > - Data-Manipulation Language (DML) : 사용자가 만들어진 데이터에 접근하거나 조작하도록 하는 언어.

> ## 1.6 Functional components of Database System
>
> > - Storage Manager : low-level data와 응용프로그램 사이의 interface제공. 여러 역할이 있고, 추후 나옴.
> > - The Query Processor
> > - Transaction Management : atomicity(all or nothing) and consistency를 관리하는 것.

> ## 2.2 Database Schema
>
> > - relation : 프로그래밍 언어에서 변수.
> > - relation schema : 프로그래밍 언어에서 타입정의.
> > - relation instance : 프로그래밍 언어에서 변수의 값.

> ## 2.3 Keys
>
> > - superkey : relation에서 tuple을 구분할 수 있는 하나 또는 그 이상의 특성집합.
> > - candidate keys : 최소 superkey 집합.
> > - primary key : relation에서 튜플들을 식별하는 주요 수단으로 선택된 후보키.
> > - foreign key : 한 테이블에서 다른 테이블의 행을 식별할 수 있는 특성.
> > - foreign key constraint : foreign key로 설정된 특성은 다른 테이블에서는 primary key여야 한다는 제약.
> > - referential integrity constraint : 참조하는 테이블의 특성값이 참조되는 테이블의 값으로 존재해야만 한다는 제약.

> ## 2.6 The Relational Algebra
>
> > - The Select Operation
> > - The Project Operation
> > - Composition of Relational Operations
> > - The Cartesian-Product Operation
> > - The Join Operation
> > - Set Operations
> > - The Assignment Operation
> > - The Rename Operation

> ## 3.2 SQL Data Definition
>
> DDL은 Data Definition language의 약자로 테이블, 테이블에 대한 정보 등을 지정한다.주요 역할로 테이블의 스키마, 특성의 타입, 무결성 제약, 각 테이블을 관리할 인덱스 집합, 보안과 권한, 물리적 저장구조을 설정한다.
>
> ### 3.2.1 Basic Types
>
> > - char(n) : 고정길이 n의 문자.
> > - varchar(n) : 최대 길이 n의 가변문자.
> > - int
> > - smallint
> > - numeric(p,d) : 숫자 개수가 p개인 수를 표현, d는 p의 소수점 아래의 숫자개수.
> > - real, double precision
> > - float
>
> ### 3.2.2 Basic Schema Definition
>
> > - create table
> > - drop table
> > - alter table

> ## 3.3 Basic Structure of SQL Queries
>
> 기본구조 : select { 특성 } from { 테이블 } where { 조건 }

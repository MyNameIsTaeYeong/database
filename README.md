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
>
> > - 쿼리의 결과를 명확하게 하는 단계.
> >
> > 1. Generate a Cartesian product of the relations listed in the from clause.
> > 2. Apply the predicates specified in the where clause on the result of Step 1.
> > 3. For each tuple in the result of Step 2, output the attributes (or results of expressions) specified in the select clause.

> ## 3.6 Null Value
>
> > - true and unknown is unknown.
> > - false and unknown is false.
> > - unknown and unknown is unknown.
> > - true or unknown is true.
> > - false or unknown is unknown.
> > - unknown or unknown is unknown.
> > - not unknown is unknown.

> ## 3.7 Aggregate Functions
>
> > : input으로 집합또는 집합들을 받아서 single value를 return해주는 함수. avg, min, max등이 있다.
>
> ### 3.7.2 Aggregation with Grouping
>
> > : 그룹으로 묶어서 집계하는 방법이다. 이때 group by절에 나타나는 특성은 select절에 올 수 있지만, group by절에 나타나지 않은 특성은 오직 Aggregate function에 인자로 나타나야 한다. 예를 들어<br>
> >
> > - ### **select** dept_name, ID, avg(salary)
> >
> >   ### **from** instructor
> >
> >   ### **group_by** dept_name;
> >
> > 이와 같은 쿼리문은 ID특성이 group_by절에 나타나지 않았기 때문에 단독으로 올 수 없다. 왜냐하면 각 그룹에 대한 결과는 튜플 1개이고, 이를 위해 서로 다른 ID들 중에 유일하게 1개의 ID를 정하는 방법이 존재하지 않기 때문이다. 따라서 잘못된 쿼리다.
>
> ### 3.7.3 The Having Clause
>
> > : 그룹에 적용하는 특성. 위와 같이 having절에 나타나는 특성은 group by절에 나타나거나, aggregate function이어야 한다.
> >
> > - ### **select** dept_name, avg(salary)
> >
> >   ### **from** instructor
> >
> >   ### **group_by** dept_name
> >
> >   ### **having** avg(salary) > 42000;
> >
> > - 위와 같은 쿼리가 따르는 연산의 순서
> >
> > 1. **from** 절로부터 relation을 얻는다.
> > 2. **where** 절의 조건을 1번의 relation에 적용한다.
> > 3. **group_by** 를 2번 relation에 적용한다. 이때 각 그룹을 하나의 튜플로 바라본다.
> > 4. **having** 을 3번 relation에 적용한다.
> > 5. **select** 을 4번 relation에 적용한다.

> ## 3.8 Nested Subqueries
>
> ### 3.8.1 Set Membership
>
> > - A in (subquery): 특성 A가 subquery의 결과에 나타나는지 확인
> > - A not in (subquery): 특성 A가 subquery의 결과에 나타나지 않는지 확인.
>
> ### 3.8.2 Set Comparison
>
> > - \> some (subquery) : subquery의 일부보다 크다면.
> > - \> all (subquery) : subquery의 전부보다 크다면.
>
> ### 3.8.3 Test for Empty Relations
>
> > - exists(subquery) : subquery가 nonempty라면 true를 return
>
> ### 3.8.4 Test for the Absence of Duplicate Tuples
>
> > - unique(subquery) : subquery의 결과에 중복튜플이 있다면 true를, 그렇지 않다면 false를 리턴.
>
> ### 3.8.5 Subqueries in the From Clause
>
> ```
> select
>   name, salary, avg salary
> from
>   instructor I1,
>   lateral(select
>               avg(salary) as avg salary
>           from
>               instructor I2
>           where
>               I2.dept_name=I1.dept_name
>           );
> ```
>
> - from절의 subquery에서는 같은 from절의 다른 relation을 참조할 수 없다. 참조하려면 'lateral'을 붙여야 한다.
>
> ### 3.8.6 The With Clause
>
> ```
> with max_budget(value)
>   as (select max(budget) from department)
> ```
>
> > - 일시적인 relation을 정의하는 방식. as뒤의 subquery를 value라는 속성을 가지는 max_budget relation이라고 일시적으로 정의.
>
> ### 3.8.7 Scalar Subqueries
>
> - subquery가 특성 1개를 가진 튜플 1개를 리턴한다면 그것을 Scalar Subqueries라 한다.

> ## 3.9 Modification of the Database
>
> ### 3.9.1 Deletion
>
> ```
> delete from R
> where P;
> ```
>
> ### 3.9.2 Insertion
>
> ```
> insert into R(attributes)
> values(attribute's values)
> ```
>
> ### 3.9.3 Updates
>
> ```
> update instructor
> set salary = salary * 1.05;
> ```

> ## 4.1 Join Expressions
>
> ### 4.1.1 The Natural Join(=inner join)
>
> - A natural join B : A와 B 두 relation에서 나타나는 공통된 특성들이 모두 같은 값인 tuple들을 출력한다.
> - A join B using (a,b) : A와 B 두 relation에서 나타나는 특성 a,b가 같은 값인 tuple들을 출력한다. 특성 c가 공통된 특성일지라도 같은 값일 필요가 없다.
>
> ### 4.1.2 Join Conditions
>
> - A join B on (conditions) : 조건에 맞는 두 relation의 조인.
>
> ### 4.1.3 Outer Joins
>
> - A left outer join B on (conditions) : conditions에 맞지 않는 A의 tuple들도 출력한다.
> - A right outer join B on (conditions) : conditions에 맞지 않는 B의 tuple들도 출력한다.
> - A full outer join B on (conditions) : conditions에 맞지 않는 A와 B의 tuple들도 출력한다.

> ## 4.2 Views
>
> - 기존의 관계에서 필요한 특성만 뽑아서 만드는 가상의 관계.
> - 쿼리의 결과를 계산한다. 이때 미리 계산하여 저장하는 것이 아니라, 가상의관계가 사용될때마다 계산한다. 미리 계산하여 저장하게 되면 기존의 관계에서 변화가 일어났을시에 데이터가 맞지 않는 경우가 생기기 때문이다.
>
> ### 4.2.1 View Definition
>
> ```
> create view v as <query expression>;
> ```
>
> - 데이터베이스 시스템은 뷰와 관련된 쿼리를 저장하고 뷰가 사용될때마다 쿼리를 계산한다.
>
> ### 4.2.3 Materialized Views
>
> - 미리 쿼리의 결과를 계산하여 저장하는 뷰.
> - 뷰를 사용할때 속도는 굉장히 빠르다. 큰 관계들의 계산을 필요로 하는 뷰를 사용할때 이점이 있다.
> - 이러한 이점은 저장공간과 최신화를 유지하기위한 오버헤드와 비교하여야 한다.
>
> ### 4.2.4 Update of a View
>
> - 뷰의 수정은 실제 relation의 수정으로 이어지기 때문에 여러가지 문제가 발생한다.

> ## 4.3 Transactions
>
> - all or nothing
> - Commit work : 현재 transaction을 기록한다.
> - Rollback work : 현재 transaction을 되돌린다.

> ## 4.4 Integrity Constraints
>
> ### 4.4.2 Not Null Constraint
>
> ### 4.4.3 Unique Constraint
>
> ### 4.4.4 The Check Clause
>
> - check(P) : 속성 P를 모든 tuple이 만족시켜야 한다.
>
> ### 4.4.5 Referential Integrity
>
> - 한 테이블에서 나타나는 값이 다른 테이블에서도 나타나야 한다는 제약.
> - 참조 무결성 제약이 위반되는 update 또는 delete를 한다면, 일반적으로 위반을 야기하는 행동은 거절된다. 그러나 거절대신 튜플에 변화를주어 제약을 회복하도록 할 수 있다.
>
> ```
> create table course
>   (...
>    foreign key(dept_name) references department
>           on delete cascade
>           on update cascade,
>   ...);
> ```
>
> - on delete cascade : department의 특정 부서가 삭제되면, 그 특정 부서를 참조하는 course의 튜플도 삭제한다.
> - on update cascade : department에 존재하지 않은 dept_name이 course에서 업데이트 된다면, 해당 값을 department에도 업데이트 해준다.
>
> ### 4.4.6 Assigning Names to Constraints
>
> ### 4.4.7 Integrity Constraint Violation During a Transaction
>
> - 기본은 단계마다 제약확인을 하는것.
> - 그러나 첫 단계에는 제약조건을 위반하지만 몇 단계를 완료한 후에 제약조건을 회복하는 경우가 생긴다.
> - 이러한 상황을 다루기 위해 제약조건을 확인인하는 과정을 transaction이 완료된 후로 연기할 수 있다.
> - 그러나 많은 데이터베이스구현은 이 부분을 지원하지 않는다.
> - 따라서 프로그래밍적 테크닉으로 이러한 상황을 다룬다.
>
> ## 4.5 SQL Data Types and Schemas
>
> ### 4.5.8 Schemas, Catalogs, and Environments
>
> - 현대 데이터베이스 시스템들은 relation들에 이름을 붙일때, 3단계의 계층을 사용한다. Catalogs - Schemas - relations. 3개중 최소 1개가 다르면 다른 relation이다.
>
> ## 4.6 Index Definition in SQL
>
> : 목차와 같은 개념. 원하는 데이터를 검색할때, 전체 데이터베이스를 찾는 것이 아니라 해당데이터가 있는 index를 먼저 찾는다.
>
> ## 4.7 Authorization
>
> ### 4.7.2 Roles
>
> : 역할.역할에 권한들을 부여하고, 유저에게 역할을 부여한다. 데이터베이스는 유저의 권한을 확인할 때, 역할을 확인하고, 역할에 부여된 권한을 확인한다.

> # Chapter 5 Advanced SQL
>
> ## 5.1 Accessing SQL from a Programming Language
>
> > : 2가지 이유로 인해 데이터베이스 프로그래머는 범용 프로그래밍 언어에 접근할 수 있어야 한다.
> >
> > - 모든 query들이 SQL로 표현될 수 없다.
> > - report 출력, 유저와의 상호작용, 쿼리의 결과를 유저 인터페이스에 보내는 것 등은 SQL로 수행될 수 없다.
>
> > : 프로그래밍 언어로부터 SQL에 접근하는 2가지 방법
> >
> > - Dynamic SQL : 프로그램이 실행되는 동안 SQL query를 수행할 수 있게 한다.
> > - Embedded SQL : 컴파일 타임에 SQL문이 식별된다.
>
> ## 5.2 Functions and Procedures
>
> : 개발자가 정의한 함수, 절차가 가지는 이점
>
> - 다수의 어플리케이션에서 접근할 수 있다.
> - 하나의 function,procedure를 수정하면 business rule 전체가 바뀐다. 즉, 데이터베이스에 접근하는 다수의 앱을 일일히 바꿀 필요가 없다.
>
> ### 5.2.1 Declaring and Invoking SQL Functions and Procedures
>
> : 일반적인 프로그래밍 언어처럼 정의하고 호출한다.
>
> ### 5.2.2 Language Constructs for Procedures and Functions
>
> : sql이 지원하는 프로그래밍 기능들. 그러나 데이터베이스마다 문법이 다 다르다.
>
> ### 5.2.3 External Language Routines
>
> : 범용 프로그래밍 언어로 function과 procedure를 정의하고, sql쿼리 등에서 호출을 허용하도록 하는 방법.
>
> ## 5.3 Triggers
>
> : 데이터베이스 event에 대한 side effect
>
> - Trigger가 필요한 이유
>   - event(삽입, 수정, 삭제등)가 발생하기 전후로 제약조건을 만족하도록 사전 또는 사후작업을 할 수 있다.
> - Trigger를 대체할 기능이 존재한다면 Trigger를 피하는게 최고의 방법이다.
> - 많은 Trigger들은 적절한 저장된 Procedure의 사용으로 대체될 수 있다.
>
> ## 5.4 Recursive Queries
>
> ## 5.5 Advanced Aggregation Features

> # Chapter 6 Database Design Using the E-R Model
>
> ## 6.1 Overview of the Design Process
>
> ### 6.1.1 Design Phases
>
> - 유저 요구사항을 지정한다.
> - conceptual-design phase.데이터 모델을 고르고, 요구사항들을 개념적인 스키마로 옮긴다.이 단계의 목적은 entity-relationship diagram을 만드는 것이다.
> - specification of functional requirements.
> - logical-design phase. E-R모델을 사용하요 정의한 개념적 스키마를 관계스키마로 맵핑하는 단계.
> - physical-design phase. 시스템별 데이터 베이스 스키마를 사용한다.
>
> ## 6.2 The Entity-Relationship Model
>
> ### 6.2.1 Entity Sets
>
> - entity : 객체
> - entity set : 객체 집합.
> - extension of the entity set : entity set에 속한 실제 entity들의 collection을 참조하는 것.
>
> ### 6.2.2 Relationship Sets
>
> - relationship : 여러 entities사이의 연관.
> - relationship set : 관계 집합.
> - degree of the relationship set : 관계집합에 참여하는 entity set의 수

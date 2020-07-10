# Oracle_Server

## customer Table 
<pre><code>
create table customer(
    cno char(4) not null,
    cname varchar(12) not null,
    city varchar(20),
    point int,
    constraint pk_customer_cno primary key (cno)
);
</code></pre>
## customer Insert
<pre><code>
insert into customer values('c101','홍길동','서울',500);
insert into customer values('c102','임꺽정','인천',300);
insert into customer values('c103','박찬호','안양',800);
insert into customer values('c204','신동엽','과천',350);
insert into customer values('c205','정진우','고양',400);
insert into customer values('c307','정동우','서울',null);
</code></pre>
<hr/>

### Charter1
#### 1-1 테이블의 모든 열을 검색하라
<code>select * from customer;</code>
#### 1-2 테이블의 모든 열을 검색(필드명 사용)
#### 1-3 고객의 고객명, 거주지를 검색하라(테이블의 특정 열을 검색)
#### 1-4 cname 은 성명, city는 거주지로 출력하라(화면에 표시되는 열 이름 변경하여 검색)
#### 1-5 customer 테이블에서 거주지를 검색하라
#### 1-6 거주지를 검색하는데 중복 행을 제거하여 한 번씩만 검색하라


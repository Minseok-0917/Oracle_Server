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

### Chapter1
#### 1-1 테이블의 모든 열을 검색하라 
    select * from customer;
#### 1-2 테이블의 모든 열을 검색(필드명 사용)
    select cno,cname,city,point from customer;
#### 1-3 고객의 고객명, 거주지를 검색하라(테이블의 특정 열을 검색)
    select * from customer where cno = '고객명' AND city = '거주지';
#### 1-4 cname 은 성명, city는 거주지로 출력하라(화면에 표시되는 열 이름 변경하여 검색)
    select cno as 고객명,city 거주지 from customer;
#### 1-5 customer 테이블에서 거주지를 검색하라
    select city from customer;
#### 1-6 거주지를 검색하는데 중복 행을 제거하여 한 번씩만 검색하라 (distinct도 가능) ★
    select city from customer group by city;
    

### Chapter2
#### 2-1 고객번호가 c101 인 고객의 모든 정보를 검색하라
    select * from customer where cno = 'c101';
#### 2-2 포인트가 400 이하인 고객의 모든 정보를 검색하라
    select * from customer where point <= 400;
#### 2-3 거주지가 서울 **이면서** 포인트가 500 이상인 고객의 이름, 거주지, 포인트를 검색하라
    select cname,city,point from customer where city = '서울' and point >= 500;
#### 2-4 거주기가 서울 **이거나** 포인트가 500 이상인 고객의 이름, 거주지, 포인트를 검색하라
    select cname,city,point from customer where city = '서울' or point >= 500;
#### 2-5 포인트가 350부터 500 사이인 고객이름, 거주지, 포인트를 검색하라
    select cname,city,point from customer where point >= 350 and point <= 500;
#### 2-6 거주지가 서울 이거나 안양인 고객번호, 이름, 거주지를 검색하라 (IN 사용) ★★
    select cname,city,point from customer where city in('서울','안양');
#### 2-7 거주지가 서울 아니거나 안양인 고객번호, 이름, 거주지를 검색하라 (NOT IN 사용)
    select cname,city,point from customer where city not in('서울','안양');

### Chapter3
#### 3-1 정씨 성을 가진 고객의 모든 열을 검색하라
    select * from customer where cname like '정%';
#### 3-2 이름에 '동'자가 들어가는 고객의 모든 열을 검색하라
    select * from customer where cname like '_%동%';
#### 3-3 이름의 세번째 글자가 '우' 자가 들어가는 고객의 모든 열을 검색하라
    select * from customer where cname like '__우';
#### 3-4 성이 홍씨, 박씨, 정씨이 고객을 검색하라 ( 성이 홍씨, 박씨, 정씨이 아닌 고객을 검색하라 )
    select * from customer where cname like '정%' or cname like '홍%' or cname like '박%';
    select * from customer where cname not like '정%' and cname not like '홍%' and cname not like '박%';
#### 3-5 포인트가 없는 고객의 번호, 이름, 포인트를 검색하라 ( 포인트가 있는 고객의 번호, 이름, 포인트를 검색하라 )
    select cno,cname,point from customer where point is null;
    select cno,cname,point from customer where point is not null;


### Chapter4
#### 4-1 고객 테이블에서 이름을 오름차순 정렬하라
    select * from customer order by cname asc;
#### 4-2 거주지가 서울인 고객의 모든 데이터를 검색하는데, 이름의 오름차순 정렬하여 출력하라
    select * from customer where city = '서울' order by cname asc;
#### 4-3 거주지의 오름차순으로 정렬하고, 거주기가 같으면 포인트의 내림차순으로 정렬하라    
    select * from customer order by city asc,point desc;
#### 4-4 포인트가 많은 순으로(내림차순) 먼저 정렬하고, 같은 포인트는 이름의 오름차순으로 정렬하고 이름이 같으면 거주지의 오름차순으로 정렬하고 검색하라
    select * from customer order by point desc,cname asc,city asc;
#### 4-5 다음의 의미는 ? 
    select cno, cname, city, point from customer order by 3;
    customer 테이블에 3번째 열을 기준으로 cno,cname,city,point 필드를 출력한다

# Oracle_Server

<pre><code>
create table customer(
    cno char(4) not null,
    cname varchar(12) not null,
    city varchar(20),
    point int,
    constraint pk_customer_cno primary key (cno)
);

insert into customer values('c101','홍길동','서울',500);
insert into customer values('c102','임꺽정','인천',300);
insert into customer values('c103','박찬호','안양',800);
insert into customer values('c204','신동엽','과천',350);
insert into customer values('c205','정진우','고양',400);
insert into customer values('c307','정동우','서울',null);

select * from customer;
select cno,cname,city,point from customer;
select * from customer where cno = '고객명' AND city = '거주지';
select cno as 고객명,city 거주지 from customer;
select city from customer;
select city from customer group by city;

select * from customer where cno = 'c101';
select * from customer where point <= 400;
select cname,city,point from customer where city = '서울' and point >= 500;
select cname,city,point from customer where city = '서울' or point >= 500;
select cname,city,point from customer where point >= 350 and point <= 500;
select cname,city,point from customer where city in('서울','안양');
select cname,city,point from customer where city not in('서울','안양');

select * from customer where cname like '정%';
select * from customer where cname like '_%동%';
select * from customer where cname like '__우';
select * from customer where cname like '정%' or cname like '홍%' or cname like '박%';
select * from customer where cname not like '정%' and cname not like '홍%' and cname not like '박%';
select cno,cname,point from customer where point is null;
select cno,cname,point from customer where point is not null;

select * from customer order by cname asc;
select * from customer where city = '서울' order by cname asc;
select * from customer order by city asc,point desc;
select * from customer order by point desc,cname asc,city asc;
-- customer 테이블에 3번째 열을 기준으로 cno,cname,city,point 필드를 출력한다
</code></pre>

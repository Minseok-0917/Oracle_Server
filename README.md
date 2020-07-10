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
### 1
+ a

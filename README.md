# selfstudy

####proc sql 기본 구문(160529)
>proc sql;

>select

>from

>where

>group by

>order by

 
- proc sql; <- sql을 시작하기 위한 구문
- select 절은 data step에서 input 구문과 비슷하게, 변수를 지정해주는 것
- from 절은 data step에서 set 구문과 비슷하게 어느 데이터 셋에서 불러올지를 정하는 것
- where 절은 하나 이상의 조건으로 from에서 불러올 때, 부분집합을 만들어주는 것 data step에서 where 과 같음
- group by 절은 특정 변수에 따라 그룹을 나누는 것
- order by 절은 특정 변수에 따라 최종 쿼리를 정렬하는 것
 
다른 프로시져와는 달리, sql은 절의 순서가 중요해서, 위와 같은 순서를 유지해야함
select 와 from 절은 항상 존재해야 하며, where/group by/order by 절들은 옵션형태를 가짐
 
####<테이블을 쿼리하는 기본 예제>
>proc sql;

>select empid, jobcode, salary, salary *.06 as bonus

>from sasuser.payrollmaster

>where salary<32000

>order by jobcode;

>quit;



proc sql로 시작하고, from 절에서 지정된 sasuser.payrollmaster 라는 데이터셋에서 where 절에서 지정된 조건 salary 가 32000 보다 작은 관찰치만을 불러와서, select 절에서 지정된, empid, jobcode, salary, bonus를 만드는데, bonus는 salary에 .06을 곱한 값, 다음과 같은 형태를 alias 라고 부름 출력에는 empid, jobcode, salary, bonus 만이 나옴 마지막으로 결과값은 jobcode에 따라 정렬함

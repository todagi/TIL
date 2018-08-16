## hflights : Flights that departed Houston in 2011

***
```sql
● 연도 확인
select Year, count() from hflights
```

● 출발시간과 도착시간만 보기
```sql
select DepTime, ArrTime from hflights
``` 

● 도착지 코드 중 'DFW'만 보기
```sql
select * from hflights where Dest = 'DFW'
```

● 도착지 코드별 빈도수 보기
```sql
select Dest, count() from hflights group by Dest
```

● 비행시간 평균
```sql
select avg(AirTime) from hflights
``` 

● 비행시간 평균보다 많은 건수만 보기
```sql
select * from hflights where AirTime >= (select avg(AirTime) from hflights)
```

● 비행기 번호 별 평균
```sql
select FlightNum, avg(AirTime) from hflights group by FlightNum
```

● 취소 빈도수 확인
```sql
select Cancelled, count() from hflights group by Cancelled
```

● 취소 코드별 빈도수 확인
```sql
select Cancelled, CancellationCode, count() from hflights group by CancellationCode
```

● 평균 비행거리
```sql
select avg(Distance) from hflights
```  

● 평균 비행거리 이상만 도착지코드 별 비행거리 
```sql
select Dest, Distance from hflights group by Dest having Distance >= avg(Distance)
``` 

● 평균 출발 지연 시간
```sql
select avg(DepDelay) from hflights
``` 

● 출발 지연 시간 별 횟수
```sql
select DepDelay, count() from hflights group by DepDelay
```

● 평균 연착 시간 
```sql
select avg(ArrDelay) from hflights
``` 

● 연착 시간 별 횟수
```sql
select ArrDelay, count() from hflights group by ArrDelay
```

● 1월 데이터만 보기
```sql
select * from hflights where Month = '1'
```

● 1월 중 금요일(6)만 보기
```sql
select * from hflights where Month = '1' and DayOfWeek = '6'
``` 

● 3월 중 주말(1:일요일, 7:토요일)만 보기 
```sql
select * from hflights where Month = '3' and DayOfWeek = '1' or DayOfWeek = '7'
```

● 캐리어 종류별로 개수 보기
```sql
select UniqueCarrier, count() from hflights group by UniqueCarrier
```

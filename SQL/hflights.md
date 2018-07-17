hflights : Flights that departed Houston in 2011

***

#### 연도 확인
select Year, count() from hflights 

#### 출발시간과 도착시간만 보기
select DepTime, ArrTime from hflights 

#### 도착지 코드 중 'DFW'만 보기
select * from hflights where Dest = 'DFW'

#### 도착지 코드별 빈도수 보기
select Dest, count() from hflights group by Dest

#### 비행시간 평균
select avg(AirTime) from hflights   

#### 비행기 번호 별 평균
select FlightNum, avg(AirTime) from hflights group by FlightNum

#### 취소 빈도수 확인
select Cancelled, count() from hflights group by Cancelled

#### 취소 코드별 빈도수 확인
select Cancelled, CancellationCode, count() from hflights group by CancellationCode

#### 평균 비행거리
select avg(Distance) from hflights   

#### 평균 비행거리 이상만 도착지코드 별 비행거리 
select Dest, Distance from hflights group by Dest having Distance >= avg(Distance) 

#### 평균 출발 지연 시간
select avg(DepDelay) from hflights 

#### 출발 지연 시간 별 횟수
select DepDelay, count() from hflights group by DepDelay

#### 평균 연착 시간 
select avg(ArrDelay) from hflights 

#### 연착 시간 별 횟수
select ArrDelay, count() from hflights group by ArrDelay

#### 1월 데이터만 보기
select * from hflights where Month = '1'

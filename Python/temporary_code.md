## day 5

============================================================================

### [10 minutes to pandas 판다스 공부](https://pandas.pydata.org/pandas-docs/stable/10min.html)
### 쥬피터 팁 : 함수쓸 때 탭 키를 누르면 함수들이 뜬다. 혹은 함수하고 '.'치고 탭을 치면 하위 메서드 들이 뜬다. 


Json

```python
import json

j_d = { 
       'Class' : 'A', 
       'name' : 'Jane', 
       'Age' : 20, 
       'Country'  : 'Korean'
      }
j_c = json.JSONEncoder().encode(j_d)

j_c
'{"Class": "A", "name": "Jane", "Age": 20, "Country": "Korean"}'


print(j_c)
{"Class": "A", "name": "Jane", "Age": 20, "Country": "Korean"}

che = json.dumps('한글')
print(che)
"\ud55c\uae00"

che = json.dumps('한글', ensure_ascii = False)
print(che)
"한글"

che = json.dumps(j_d, ensure_ascii = False)
print(che)
{"Class": "A", "name": "Jane", "Age": 20, "Country": "Korean"}


j_c= json.JSONDecoder().decode(che)
j_c
{'Class': 'A', 'name': 'Jane', 'Age': 20, 'Country': 'Korean'}

j_c['Country']
'Korean'

'''

큰수 찾기

```python

k = [1, -2, 3, 6, -7, 4]

def g_max(k):
    z = k[0]
    for i in k:
        if z < i:
            z = i
    return z
 g_max(k)
 6
```
 
 ```python
 
 data = ["cat", "cat", "cat", "sheep", "sheep", "duck", "duck", "duck", "duck" ]

dic_data = {}
dic_data['cat'] = 0
dic_data['sheep'] = 0
dic_data['duck'] = 0

for i in data:

    if i == 'cat':
        dic_data['cat'] += 1
    elif i == 'sheep':
        dic_data['sheep'] += 1
    elif i == 'duck':
        dic_data['duck'] += 1
        
dic_data
{'cat': 3, 'sheep': 2, 'duck': 4}
 
```
```python
def draw_hist(data):
    for i, j in data.items():
        print(i,"\t", "=" *j, )
draw_hist(dic_data)

cat 	 ===
sheep 	 ==
duck 	 ====

```


```python
from pandas import Series, DataFrame
# 위처럼 해주어야  'pd.DataFrame(df)' 안하고 바로 'Datafame(df) 할 수 있다.

```

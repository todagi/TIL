## day 5

============================================================================



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

'''



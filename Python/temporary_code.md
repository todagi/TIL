## day 5

============================================================================

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


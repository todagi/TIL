## day 3

============================================================================
```python

for i in range(9, 1, -1):
    print(i)
    
```


```python

def intro_car(brand, seats =4, type = '세단'):
    print('my car is {b} {s}인승 {t}이다.'.format(
          b= brand,
          s= seats,
          t= type
    ) )

intro_car('아우디')

intro_car('벤츠', seats = 2)

intro_car(brand = '머큐리', type = '머슬카')

intro_car('폭스바겐', 6, '집차')

```

```python

def introduceMyFamily(my_name, *family_names, **family_info):
    print('안녕하세요, 저는 %s 입니다.' % (my_name))
    print('-' * 35)
    print('제 가족들의 이름은 아래와 같아요. ')

    for name in family_names:
        print('* %s ' % (name), end='\t')
    else:
        print()
    print('-' * 35)

    for key in family_info.keys():
        print('- %s : %s ' % (key, family_info[key]))

introduceMyFamily('영희', '찬희', '영수', '동수', 주소 = '아파트', 가훈 = '밥 먹기')

```

```python

def add(a, b):
    return a + b

data = (20, 30)

print(add(*data))

```

```python 

def intro(name, greet, happy):
    return "{name}님, {greet}, {happy}!".format(
             name = name,
             greet = greet,
             happy = happy
              )

intro_dict = {'name' : '진수', 'greet' : '안녕', 'happy' : '반가워'}
print(intro(**intro_dict))

```

```python

def introduce(name, greeting):
    return "{name}님, {greeting}".format(
        name=name,
        greeting=greeting,
    )

introduce_dict = {
    "name" : "김진수",
    "greeting" : "안녕하세요",
}
print(introduce(**introduce_dict))

```

```python 

def mf():
    """
    아무것도 안하고 주석만 호출하는 함수
      """
    pass

print(mf.__doc__)

```

```python

def introduce_your_family(name, *family_names, **family_info):
    '''
    가족을 소개하는 함수입니다.
    Args:
        name: 자기이름 입력하기
        *family_names: 가족이름 입력하기
        **family_info: 가족소개하기

    Returns: 없습니다.
    '''
    pass

print(introduce_your_family.__doc__)

```

```python
string = '클래스'

print('string은 %s이다.' % type(string))


class Song:
    song = '선물'

    def __init__(self, name):
        self.name = name

    def sing_a_song(self):
        print(self.name + "이는 " + self.song + ' 노래를 부릅니다.')

singer1 = Song('지영')
singer2 = Song('원영')
singer3 = Song('유란')

singer1.sing_a_song()
singer2.song = '동화'
singer3.song = '몰락'
singer2.sing_a_song()
singer3.sing_a_song()
```


```python

class Game:
    names = []

    def __init__(self, name):
        self.name = name
    def add_genre(self, genre):
        self.names.append(genre)

game1 = Game('스타크래프트')
game2 = Game('리그오브레전드')

game1.add_genre('RTS')
game2.add_genre('AOS')

print(game1.name, " : ", game1.names)
print(game2.name, " : ", game2.names)

```


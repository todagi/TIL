## day 3

============================================================================
```python

for i in range(9, 1, -1):
    print(i)
    
9
8
7
6
5
4
3
2    
    
    
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


my car is 아우디 4인승 세단이다.
my car is 벤츠 2인승 세단이다.
my car is 머큐리 4인승 머슬카이다.
my car is 폭스바겐 6인승 집차이다.


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


안녕하세요, 저는 영희 입니다.
-----------------------------------
제 가족들의 이름은 아래와 같아요. 
* 찬희 	* 영수 	* 동수 	
-----------------------------------
- 주소 : 아파트 
- 가훈 : 밥 먹기 

```

```python

def add(a, b):
    return a + b

data = (20, 30)

print(add(*data))

50


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


진수님, 안녕, 반가워!

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

김진수님, 안녕하세요

```

```python 

def mf():
    """
    아무것도 안하고 주석만 호출하는 함수
      """
    pass

print(mf.__doc__)


    아무것도 안하고 주석만 호출하는 함수

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



    가족을 소개하는 함수입니다.
    Args:
        name: 자기이름 입력하기
        *family_names: 가족이름 입력하기
        **family_info: 가족소개하기

    Returns: 없습니다.

```

```python
string = '클래스'

print('string은 %s이다.' % type(string))

string은 <class 'str'>이다.


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



지영이는 선물 노래를 부릅니다.
원영이는 동화 노래를 부릅니다.
유란이는 몰락 노래를 부릅니다.
```


#### 클래스 변수 -> 인스턴스 간 공유 됨
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



스타크래프트  :  ['RTS', 'AOS']
리그오브레전드  :  ['RTS', 'AOS']

```

#### 인스턴스 변수 -> 인스턴스간 공유 안됨

```python
class Game2:
    def __init__(self, name):
        self.name = name
        self.names = []

    def add_genre(self, genre):
        self.names.append(genre)

game3 = Game2('리니지')
game4 = Game2('오버워치')

game3.add_genre('RPG')
game4.add_genre('FPS')

print(game3.name, " : ", game3.names)
print(game4.name, " : ", game4.names)



리니지  :  ['RPG']
오버워치  :  ['FPS']
```

```python

class Myhome:
    home = 'Guri'

result = dir(Myhome)
print(result)


['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'home']


num = 0

for intele in result:
    num += 1
    print(num, intele, end = " ")
    
1 __class__ 2 __delattr__ 3 __dict__ 4 __dir__ 5 __doc__ 6 __eq__ 7 __format__ 8 __ge__ 9 _    

```

```python
class Myhome:
    __home = 'Guri'

result = dir(Myhome)

num = 0

for intele in result:
    num += 1
    print(num, intele,  end = " ")

1 _Myhome__home 2 __class__ 3 __delattr__ 4 __dict__ 5 __dir__ 6 __doc__ 7 __eq__ 8 __format__ 9 __ge__ 10 __getattribute__ 11 __gt__ 12 __hash__ 13 __init__ 14 __init_subclass__ 15 __le__ 16 __lt__ 17 __module__ 18 __ne__ 19 __new__ 20 __reduce__ 21 __reduce_ex__ 22 __repr__ 23 __setattr__ 24 __sizeof__ 25 __str__ 26 __subclasshook__ 27 __weakref__ 


```

```python
class meal:
    __lunch =  '샌드위치'
    __dinner = '비빔밥'

    def get_lunch(self):
        return self.__lunch

    def get_dinner(self):
        return self.__dinner

    def set_lunch(self, lunch):
        self.__lunch = lunch

    def set_dinner(self, dinner):
        self.__dinner = dinner

myMeal = meal()
my_lunch = myMeal.get_lunch()
my_dinner = myMeal.get_dinner()

print("I ate %s and %s yesterday" % (my_lunch, my_dinner) )


I ate 샌드위치 and 비빔밥 yesterday


```

```python

class meal:
    __lunch =  '샌드위치'
    __dinner = '비빔밥'

    def get_lunch(self):
        return self.__lunch

    def get_dinner(self):
        return self.__dinner

    def set_lunch(self, lunch):
        self.__lunch = lunch

    def set_dinner(self, dinner):
        self.__dinner = dinner

myMeal = meal()
my_lunch = myMeal.get_lunch()
my_dinner = myMeal.get_dinner()


myMeal.set_lunch('햄버거')
myMeal.set_dinner('설렁탕')

my_lunch = myMeal.get_lunch()
my_dinner = myMeal.get_dinner()

print('Today I will eat {ml} in the afternoon and {dl} at night'.format(ml = my_lunch, dl = my_dinner))


Today I will eat 햄버거 in the afternoon and 설렁탕 at night

```

```python
var = 10

def glre():
    var = 20
    return var


print('Global_variables : ', var)
print('Regional_variables : ', glre())


Global_variables :  10
Regional_variables :  20

```


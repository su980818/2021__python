# 1. 메타문자

## 1) 문자 클래스[]
[abc] = a or b or c

[a-zA-z] = a\~z or A\~Z


### #) 자주 사용되는 문자 클래스의 short_cut

|short cut|-|
|-|-|
|\d | 숫자와 매치, [0-9]와 동일한 표현식이다.|
|\D | 숫자가 아닌 것과 매치, [^0-9]와 동일한 표현식이다.|
|\s |whitespace 문자와 매치, [ \t\n\r\f\v]와 동일한 표현식이다. 맨 앞의 빈 칸은 공백문자(space)를 의미한다.|
|\S |whitespace 문자가 아닌 것과 매치, [^ \t\n\r\f\v]와 동일한 표현식이다.|
|\w |문자+숫자(alphanumeric)와 매치, [a-zA-Z0-9_]와 동일한 표현식이다.|
|\W |문자+숫자(alphanumeric)가 아닌 문자와 매치, [^a-zA-Z0-9_]와 동일한 표현식이다.|

## 2) Dot(.)

정규 표현식의 Dot(.) 메타 문자는 줄바꿈 문자인 \n을 제외한 모든 문자와 매치됨을 의미한다.


## 3) 반복   

### a. *
\* = 0 ~ INF 


### b. +
\+ = 1 ~ INF 

### c. {m,n}

{m,n} = m ~ n

? = {0,1}

## 4) or |

str1|str2 = str1 or str2

## 5) Anchor( ^ \A ),( $ \Z )

<pre>
>>> print(re.search('^Life', 'Life is too short'))
<re.Match object; span=(0, 4), match='Life'>
</pre>

\A 의 겨우 ^과 모든  부분에서 동일하지만 compile option re.M 을 사용하여도 라인의 첫버째로 바뀌는 ^ 과 달리 무조건 문자열의 맨 처음을 가르킴 


<pre>
>>> print(re.search('short$', 'Life is too short'
matching
</pre>

\Z 도 위와 동일

## 6) Word boundary ( \b )

<pre>
>>> p = re.compile(r'\bclass\b')
>>> print(p.search('no class at all')) 
matching
</pre>

white space에 의해 구분된 문자열을 match

## 7) Word boundary ( \B )

white space이외의 것으로 구분된 문자열을 match

# 2. Grouping
grouping 을 하는 이유
### a. 반복되는 문자열을 표현하기위해
<pre>
re.match("(abc)+","abcabcabc")
</pre>
### b. 매치된 문자열중 특정 문자열을 재참조 하기위해

<pre>
p = re.compile(r"(\w+)\s+\d+[-]\d+[-]\d+")
m = p.search("park 010-1234-1234")

print(m.group(1))
</pre>
 [group() method와 원하는 index를 사용하여 재참조 할 수 있음]()

### c. 패턴내부에서도 group 된 문자열을 재참조 할 수 있음
#### \1 OR \num 을 사용하여 group된 문자를 재참조
<pre>
p = re.compile(r'(\b\w+)\s+\1')
p.search('Paris in the the spring').group()
'the the'
</pre>

[string 앞에 r을 주어 내부에 \1,\b을 메타문자로 인식하게 할 수 있음]()


### d. 2,3 번에서의 재참조에 이름을 붙이자.

#### 그룹 naming : ([?P<group_name>]()pattern)

#### re.match_class에서의 재참조 : m.group("group_name")

<pre>
p = re.compile(r"(?P<name>\w+)\s+((\d+)[-]\d+[-]\d+)")
m = p.search("park 010-1234-1234")
print(m.group("name"))
</pre>

#### 패턴 내부에서의 재참조 : (?P=group_name)
<pre>
p = re.compile(r'(?P<word>\b\w+)\s+(?P=word)')
p.search('Paris in the the spring').group()
</pre>


# 3. 전방탐색 (Lookahead Assertions)
[조건을 추가하는 기법]()

[이러한 패턴을 충족할시 이를 충족하는 패턴은 소비하지않고 이것이 없었던 것처럼 다음에 오는 일반적인 패턴을 수행함 충족하지 않을경우는 패턴 매칭을 종료]()

### a. 긍정형 전방 탐색 [(?=patter_of_condition)]()
<pre>
p = re.compile(".+:")
m = p.search("http://google.com")
print(m.group())
>>> http:
</pre>
match 를 통해 http만을 match하고싶다고 하자 

위에서 설명한 전방탐색을 생각해보면 마지막이 : 로 끝나는 조건을 만족하고 이를 만족한다면 다음에 오는 패턴을 수행하면 된다. (지금의 경우는 패턴이 끝남)

<pre>
p = re.compile(".+(?=:)")
m = p.search("http://google.com")
print(m.group())
>>> http
</pre>




### b. 부정형 전방 탐색 [(?!=patter_of_condition)]()

<pre>
import re

p = re.compile(".+[.].+$")
print( p.search("abc.h").group() );
print( p.search("abc.bat").group() );
print( p.search("abc.bad").group() );
</pre>
match를 통해 확장자가 bad 인 경우만을 제외하고 match를 하고 싶다고 하자. 

부정형 전방탐색은 긍정형 전방 탐색과 다르게 조건에 있는 patter과 일치하지 않는 경우만 다음에 오는 패턴을 수행하기 때문에 

<pre>
p = re.compile(".+[.](?!bad).+$")
print( p.search("abc.h").group() );
print( p.search("abc.bat").group() );
print( p.search("abc.bad") ); >> NONE
</pre>
(?1bad) 라는 조건을 충족하는지를 검색할때는 문자를 소비하지않고 조건의 일치 여부를 판단한후 조건이 원래부터 없었던거 처럼 패턴매칭을 시작한다. 

# 5. 문자열 바꾸기
패턴과 매치되는 문자열을 지정한 문자열로 바꾼다. 
<pre>
p = re.compile('(blue|white|red)')
p.sub('colour', 'blue socks and red shoes', [count = n] ) 매치되는 문자중에 n번만 바꿈
>>> 'colour socks and colour shoes'
</pre>

sub의 바꿀 문자열에 위에서 배운 group을 참조할 수 있다. 
<pre>
\g<group_name>
</pre>

<pre>
p = re.compile(r"(?P<name>\w+)\s+(?P<phone>(\d+)[-]\d+[-]\d+)")
print(p.sub("\g<phone> \g<name>", "park 010-1234-1234"))
>>> 010-1234-1234 park
</pre>
# 6. Greedy vs Non-Greedy

>>> s = '<html><head><title>Title</title>'
>>> len(s)
32
>>> print(re.match('<.*>', s).span())
(0, 32)
>>> print(re.match('<.*>', s).group())
<html><head><title>Title</title>
<.*> 정규식의 매치 결과로 <html> 문자열을 돌려주기를 기대했을 것이다. 하지만 * 메타 문자는 매우 탐욕스러워서 매치할 수 있는 최대한의 문자열인 <html><head><title>Title</title> 문자열을 모두 소비해 버렸다. 어떻게 하면 이 탐욕스러움을 제한하고 <html> 문자열까지만 소비하도록 막을 수 있을까?

다음과 같이 non-greedy 문자인 ?를 사용하면 *의 탐욕을 제한할 수 있다.

>>> print(re.match('<.*?>', s).group())
<html>
non-greedy 문자인 ?는 *?, +?, ??, {m,n}?와 같이 사용할 수 있다. 가능한 한 가장 최소한의 반복을 수행하도록 도와주는 역할을 한다

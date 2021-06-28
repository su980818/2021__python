# 1. 메타문자

## 1) 문자 클래스[]
[abc] = a or b or c
[a-zA-z] = a~z or A~Z


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
* = 0 ~ INF 


### b. +
+ = 1 ~ INF 

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
>>> print(re.search('short$', 'Life is too short'))
<re.Match object; span=(12, 17), match='short'>
</pre>

\Z 도 위와 동일

## 6) Word boundary ( \b )

<pre>
>>> p = re.compile(r'\bclass\b')
>>> print(p.search('no class at all')) 
<re.Match object; span=(3, 8), match='class'>
</pre>

white space에 의해 구분된 문자열을 match

## 7) Word boundary ( \B )

white space이외의 것으로 구분된 문자열을 match

# 2. Grouping


 

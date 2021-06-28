
# 1. 파이썬에서의 정규표현식 사용

1. re module 을 import 
2. p = re.compile(” regex pattern “) : re.Pattern class 를 갖는 객체 p 생성
3. p의 메소드를 활용하여 원하는 문자열을 patter_p에 matching



# 2 re.Pattern class의 method

|Method|목적|
|-|-|
|match()|문자열의 처음부터 정규식과 매치되는지 확인|
|Search()|문자열 전체를 검색하여 정규식과 매치되는지 확인|
|Findall()|정규식과 매치되는 모든 문자열을 리스트로 return|
|Finditer()|정규식과 매치되는 모든 문자열을 반복가능한 객체로 return|

## 1) match()
문자열의 처음부터 정규식과 매치되는지 확인하여

패턴 매치 시  <class 're.Match’>

패턴 불일치 시  NONE



<pre>
import re

str1 = "abc"
str2 = "def"
p = re.compile("abc")
print(p.match(str1))
print(p.match(str2))
</pre>

## 2) search()
문자열 전체를 검색하여 정규식과 매치되는지 확인
<pre>
import re
str1 = "abc def"
p = re.compile("def")

print(p.match(str1))
print(p.search(str1))
</pre>
*# match에 경우 문자열의 처음부터 matching하기때문에 ^ 가 붙어있다고 생각할수 있음*

## 3) findall()
정규식과 match되는 문자열을 문자열 list로 return

<pre>
import re
str1 = "abc def abc"
p = re.compile("abc")

print((p.findall(str1)))
</pre>

## 4) finditer()
정규식과 match되는 문자열을 match_class list로 return

<pre>
import re
str1 = "abc def abc"
p = re.compile("abc")

for i in p.finditer(str1) :
print(i)
</pre>

## #) re.match class?

[위에서 배운 method를 사용했을때 return 되는 re.match 값은 무엇일까?]()
Re.match class 의 객체를 통해 
Match되는 문자열의 정보 즉

Match되는 문자열의 문자열과
해당 문자열이 전체문자열에서 어디에 위치 하는지의 정보를 알 수 있음

|method| 목적|
|-|-|
|group()|매치된 문자열을 돌려준다.|
|start()|매치된 문자열의 시작 위치를 돌려준다.|
|end()|매치된 문자열의 끝 위치를 돌려준다.|
|span()|매치된 문자열의 (시작, 끝)에 해당하는 튜플을 돌려준다.|

# 3. 정규표현식 컴파일 옵션
<pre> p = re.compile(＇regexp_pattern ’, option )  </pre>

|옵션 |내용|
|-|-|
|DOTALL(S) |. 이 줄바꿈 문자를 포함하여 모든 문자와 매치할 수 있도록 한다.|
|IGNORECASE(I)  |대소문자에 관계없이 매치할 수 있도록 한다.|
|MULTILINE(M) |^, $ 메타 문자의 기준을 전체 문자열이 아닌 \n으 로 나누어지는 라인을 기준으로 바꿔줌|
|VERBOSE(X) |verbose 모드를 사용할 수 있도록 한다. (정규식을 보기 편하게 만들수 있고 주석등을 사용할 수 있게된다.)|

## 4) VEPBOSE, X

아래와 같이 복잡한 정규표현식 패턴을 다른 개발자가 그나마 쉽게 해석 할 수 있도록 패턴을 풀어쓸 수 있게 해줌

<pre>
charref = re.compile(r'&[#](0[0-7]+|[0-9]+|x[0-9a-fA-F]+);')
</pre>

<pre>
charref = re.compile(r"""
 &[#]                # Start of a numeric entity reference
 (
     0[0-7]+         # Octal form
   | [0-9]+          # Decimal form
   | x[0-9a-fA-F]+   # Hexadecimal form
 )
 ;                   # Trailing semicolon
""", re.VERBOSE)
</pre>
[옵션 사용시 문자열에 사용된 whitespace는 컴파일할 때 제거된다(단 [ ] 안에 사용한 whitespace는 제외). 그리고 줄 단위로 #기호를 사용하여 주석문을 작성할 수 있다.]()





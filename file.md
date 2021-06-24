# FILE 
파일 생성하기
파일을 쓰기 모드로 열어 출력값 적기
프로그램의 외부에 저장된 파일을 읽는 여러 가지 방법
함수 이용하기
readlines 함수 사용하기
read 함수 사용하기
파일에 새로운 내용 추가하기
with문과 함께 사용하기

# 1.파일생성하기

#### [open, close 내장함수를 사용하여 파일 포인터 사용]()
<pre>
f = open("새파일.txt", 'w')
f.close()
</pre>

|파일열기모드|	설명|
|-|-|
|r	|읽기모드 - 파일을 읽기만 할 때 사용|
|w	|쓰기모드 - 파일에 내용을 쓸 때 사용 [무조건 파일의 내용을 초기화함]()|
|a	|추가모드 - 파일의 마지막에 새로운 내용을 추가 시킬 때 사용|

#### [write() 메소드를 이용하여 쓰기 가능]()
<pre>
f.write()
</pre>

# 2.파일을 읽는 여러 방법 
## 1)readline() 
#### [라인별 read]()
<pre>
f = open("C:/doit/새파일.txt", 'r')
while True:
    line = f.readline()
    if not line: break
    print(line)
f.close()
</pre>


*# 읽을 라인이 없을 경우 "" 문자열 반환*



## 2)readlines()
#### [모든라인을 리스트로 read]()
<pre>
lines_list = f.readlines()
</pre>




## 3)read
#### [모든라인을 문자열로 read]()
<pre>
lines_string = f.read()
</pre>

# 3.파일에 내용 appand

<pre>
f = open("C:/doit/새파일.txt",'a')
f.write()
f.close()
</pre>

# 4.with문을 통한 파일 입출력
#### [파일 open , close 를 자동으로 하는 command]()
<pre>
with open("foo.txt", "w") as f:
    f.write("Life is too short, you need python")
</pre>

<pre>
with open("foo.txt", "w") as f:
    f.write("Life is too short, you need python")
</pre>

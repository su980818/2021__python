# 1. ERROR의 종류

FileNotFoundError | 없는 파일을 open
ZeroDivisionError | 0으로 나눔
IndexError | 지정된 index범위를 초과 

# 2. 오류 예외 처리 기법 ( try , except )

try문을 수행하고 예외가 있을시 except 문을 실행

<pre>
try:
    ...
except [발생 오류[as 오류 메시지 변수]]:
    ...
</pre>
*# except 뒤에 발생오류를 적으면 이에 해당하는 오류만 except실행*


try문을 모두 실행할때까지 예외가 없었다면 else문을 실행 , 오류가 있었다면 except수행후 바로 종료
<pre>
try:
    ...
except [발생 오류[as 오류 메시지 변수]]:
    ...
else:  # 오류가 없을 경우에만 수행된다.
    ...
</pre>

# 3. 오류 회피하기 
<pre>
try:
    f = open("나없는파일", 'r')
except FileNotFoundError:
    pass
</pre>

# 4. 오류 발생시키기

<pre>
class Bird:
    def fly(self):
        raise NotImplementedError
</pre>
    
# 5. 오류 만들기

exception class 를 상속받아 나만의 예외 생성 가능
<pre>
class MyError(Exception):
    def __str__(self):
        return "허용되지 않는 별명입니다."
def say_nick(nick):
    if nick == '바보':
        raise MyError()
    print(nick)        
</pre>   
    
    
    
    
    
    
    

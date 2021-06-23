
모듈이란? 
함수 , 변수 , 클래스를 저장해놓은 파일 


# 1.모듈 불러오기
## 1)mod1.py 이 있을 경우(python 라이브러리나 실행 스크립트와 같은 파일에 있어야만 import가능)

<pre>
import mod1
mod1.fuc()
</pre>

## 2)fuc()으로만 사용하고 싶은경우

<pre>
from mod1 import fuc
fuc()

from mod1 import *
fuc1()
</pre>

# 2."__main__"의 의미 

<pre>
# mod1.py 
def add(a, b): 
    return a+b

def sub(a, b): 
    return a-b

print(add(1, 4))
print(sub(4, 2))
</pre>

위와 같은 파일을 import 할경우 밑에 함수가 실행되는 일이 발생하는데 이를 해결하려면?

> if __name__ == "__main__":ㅡ
#### [__name__ : 파이썬 환경변수로 스크립트를 직접실행시 __main__이 저장되고 import시에는 mod1.py이 저장됨]()

# 2.모듈 스크립트의 path설정
<pre>
improt sys
sys.path.append("dir")
</pre>
*# sys.path에는 모듈경로가 포함되있음*

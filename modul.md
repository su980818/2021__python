
### 모듈이란? 

함수 , 변수 , 클래스를 저장해놓은 파일 
Cancel changes

# 1.모듈 불러오기

## 1)mod1.fuc()

mod1.py 이 있을 경우(python 라이브러리나 실행 스크립트와 같은 파일에 있어야만 import가능)

<pre>
import mod1
mod1.fuc()
</pre>

## 2)fuc()

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

----

### 패키지란?
패키지란 모듈을 담고있는 디렉토리로 모듈을 계층적으로 관리하기위해 만들어짐

ex) parent_dir.child_dir.modul

# 3.패키지내부 모듈 import
if) a/b/mod.py 의 계층을 가진 파이선 파일을 불러오고싶다면?

<pre>
import a.b.mod
a.b.mod.fuc();

from a.b improt mod
mod.fuc();

from a.b.mod improt fuc
fuc();
</pre>

[폴더의 경로는 상대경로이기 때문에 같은 폴더에 있을경우 바로 improt할수도 있음 (..:부모경로) ]()




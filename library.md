  1. sys
  2. pickle
  3. os
  4. shutil
  5. glob
  6. tempfile
  7. time
  8. calendar
  9. random
 10. webbrowserwebbrowser


# 1. sys 
[python interpreter가 제공하는 모듈]()
> sys.argv   (variable)
command줄에서 parameter을 리스트로 저장중

> sys.exit()
강제 종료 Ctrl+Z

> sys.path (variable)
모듈을을 불러오는 경로를 list로 저장중



# 2. pickle
[pickle은 value의 data_type을 그대로 유지하면서 파일에 저장하고 불러올 수 있게 하는 모듈이다]()
###### <write to file>
<pre>
import pickle
f = open("test.txt", 'wb')
data = {1: 'python', 2: 'you need'}
pickle.dump(data, f)
f.close()
</pre>

###### <read from file>
<pre>
f = open("test.txt", 'rb')
data = pickle.load(f)
print(data)
{2:'you need', 1:'python'}
</pre>


# 3. os
[OS 모듈은 환경 변수나 디렉터리 , 파일 등의 OS자원을 제어할 수 있게 해주는 모듈]()

> os.environ
시스템의 환경변수를 딕셔너리로 저장중

> os.chdir('PATH')
현재 딕셔너리 이동

> os.getcwd()
현재 딕셔너리 string으로 반환

> os.system('command')
system 명령어 호출후 return값 출력

> os.popen('command')  = file_variable
실행한 명령어의 결과갑을 파일변수에 읽기모드로 return
print(f.read())


|함수|	설명|
|-|-|
|os.mkdir(디렉터리)|	디렉터리를 생성한다.|
|os.rmdir(디렉터리)|	디렉터리를 삭제한다.단, 디렉터리가 비어있어야 삭제가 가능하다.|
|os.unlink(파일)|	파일을 지운다.|
|os.rename(src, dst)|	src라는 이름의 파일을 dst라는 이름으로 바꾼다.|
	



# 4. shutil
> shutill.copy('file_name1','file_name2')

# 5. glob
> glob.glob('path_name')
path_name의 파일이름을 리스트로 반환 ( ? * 의 메타문자 사용가능) 
#  6. tempfile
> tempfile.mkstemp() = "temp_file_name"

> tempfile.TemporaryFile() = file_variable ( wb로 열림 ) 


#  7. time
> time.time() = float
1970년 1월 1일 0시 0분 0 기준으로 몇초 지나는지 float으로 반환

> time.localtime()
time.time() 를 time_class로 반환

> time.asctime()
time.localtime() 을 읽을수 있는 string으로 반환

> time.ctime()
위와 동일하지만 현재시간만을 반환

> time.strftime(format)
시간을 format형태의 string으로 반환

###### < format >
|포맷코드|설명|	예|
	|-|-|-|
|%a|	요일 줄임말|	Mon|
|%A|	요일	|Monday|
|%b|	달 줄임말	|Jan|
|%B|	달	|January|
|%c|	날짜와 시간을 출력함|	06/01/01 17:22:21|
|%d|	날(day)	|[01,31]|
|%H|	시간(hour)-24시간 출력 형태	|[00,23]|
|%I|	시간(hour)-12시간 출력 형태	|[01,12]|
|%j|	1년 중 누적 날짜|	[001,366]|
|%m|	달	|[01,12]|
|%M|	분	|[01,59]|
|%p|	AM or PM|	AM|
|%S|	초|	[00,59]|
|%U|	1년 중 누적 주-일요일을 시작으로|	[00,53]|
|%w|	숫자로 된 요일	|[0(일요일),6]|
|%W|	1년 중 누적 주-월요일을 시작으로	|[00,53]|
|%x|	현재 설정된 로케일에 기반한 날짜 출력|	06/01/01|
|%X|	현재 설정된 로케일에 기반한 시간 출력|	17:22:21|
|%Y|	년도 출력|	2001|
|%Z|	시간대 출력	|대한민국 표준시|
|%%|	문자	|%|
|%y|	세기부분을 제외한 년도 출력	|01|

> time.sleep(num) 
num_second 의 시간을 두고 다음명령 실행


#  8. calendar
> print(calendar.calendar(연도))
> calendar.prmonth(2015, 12)
> calendar.weekday(2015, 12, 31)
해당 날짜에 대응하는 요일 반환

> calendar.monthrange
( 해당 날짜 1일의 요일 , 몇일가지 있는지 ) 반환




#  9. random
> random.random() = float ( 0 ~ 1 )
> random.randint(start , end ) = int
> random.choice(array) = array[random_value]
> random.shuffle(array) 
array 를 suffle해서 바로 저장







# 10. webbrowser
>  webbrowser.open("http://google.com")







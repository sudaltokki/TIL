# 파이썬 사용법
>[데이터 사이언스 스쿨](https://datascienceschool.net/intro.html)에서 공부한 내용을 기록합니다.

파이썬은 다음 두 가지 방법으로 사용할 수 있다.
1. 콘솔이나 주피터 노트북을 사용한 REPL(Read–Eval–Print Loop) 방식
2. 스크립트(script) 실행 방식

## REPL(Read–Eval–Print Loop) 방식

REPL(레플) 방식은 주피터 노트북이나 파이썬(또는 IPython) 콘솔을 실행해서 명령어를 한 줄씩 입력하며 실행 상황을 지켜보는 방식이다.  
파이썬 프로그래밍을 공부하거나 코드의 초기 버전을 제작할 때 유용하다. 이 책에서는 모든 코드를 REPL 방식으로 실행하면서 공부한다.

노트북은 셀(cell)이라는 네모 칸들로 구성된다.

![jpt01](https://github.com/sudaltokki/TIL/blob/main/Machine_Learning/img/jpt.PNG)

코드를 입력한 후에 `shift` + `Enter` 키를 누르면 현재 셀이 실행되며 결과가 출력된다.  
실행된 셀의 프롬프트에는 실행 순서를 나타내는 번호가 붙는다. Enter 키만 누르면 다음 줄로 넘어가기만 하고 코드가 실행되지는 않는다.

### 값과 변수의 표현

위의 코드에서 두 번째 명령으로 나오는 x는 변수 x 값을 표시하라는 뜻이다. 이때 표시되는 것을 그 값의 표현(representation)이라고 한다.  
변수 이름을 입력했을 때 표현이 나오는 것은 REPL에서만 가능하고 이후에 설명할 스크립트 실행시에는 표시되지 않는다. 

이 방식이 REPL이라고 불리우는 것은 이렇게 명령을 하나 하나 입력하고(Read) 실행하면서(Evaluate) 변수의 값을 출력하여(Print) 살펴보는 것을 반복(Loop)하면서 코드를 만들기 때문이다.

변수 이름을 지정해서 변숫값을 살펴보는 것은 셀의 마지막 행(line)에서만 가능하다.  
즉 아래 그림의 8번 셀에서 중간에 있는 x 등은 아무런 의미가 없으므로 8번 셀의 코드는 실제로 9번 셀과 같다.

![jpt02](https://datascienceschool.net/_images/jupyter_notebook_7.png)

노트북 사용이 끝나면 `File` > `Rename` 으로 노트북의 이름을 다른 이름으로 바꾼 뒤, `File` > `Close and Halt` 명령으로 파이썬 탭을 닫는다.  
이 명령을 사용하지 않고 그냥 웹 브라우저를 닫으면 파이썬 콘솔이 배경에서 계속 실행된다.  
**반드시 Close and Halt 명령을 사용해 닫자**

## 스크립트 실행 방식

코드를 모두 완성한 후 전체 코드를 한 번에 실행하고 싶을 때는 코드를 .py 확장자 파일로 만든다. 이렇게 만든 코드 파일을 스크립트(script)라고 한다. 
스크립트는 주피터 노트북이나 아이파이썬(IPython) 콘솔을 실행하지 않고 터미널에서 직접 실행할 수 있다.

다만 스크립트에서는 변수 이름만 입력해서 변수의 값, 즉 표현(representation)이 표시되게 하는 것은 불가능하고 표시하려면 반드시 print 명령을 사용해야 한다.

`New` > `Text File` 을 실행하여 파일 입력 탭을 생성, `File` > `Rename` 으로 이름을 바꾼다.

![jpt03](https://github.com/sudaltokki/TIL/blob/main/Machine_Learning/img/jpt03.PNG)  

코드를 타이핑하고 `File` > `Save` 명령을 선택해 저장한다.

스크립트 방식은 애플리케이션(application)이나 반복하여 실행해야 하는 코드를 만들 때 주로 사용된다.

이제 아나콘다 프롬프트를 실행해 터미널을 열고 test.py가 저장된 폴더로 이동한 후 다음 명령을 입력한 후 엔터를 치자.   
```
python test.py
```
파이썬 스크립트가 실행되고 결과가 출력되는 것을 볼 수 있다.
>폴더는 cd + 경로 를 입력해 이동한다.

![jpt04](https://github.com/sudaltokki/TIL/blob/main/Machine_Learning/img/jpt04.PNG)


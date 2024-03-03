## 1.0 개요

컴퓨터 시스템 (SW + HW) => 함께 작동하여 응용프로그램을 실행
시스템의 구현방법은 시간에 따라 바뀔 수 있지만, 근본 개념들은 변하지 않음

</br>

#### 책의 목적
> **프로그래머들이 프로그램을 더욱 제대로 개발할 수 있도록,**
> 
> ***각 컴포넌트들이 어떻게 동작하며 프로그램의 성능과 정확성에 어떤 영향을 주는지 이해할 수 있게하는 것***

</br>

#### 앞으로 만나게 될 기술들

- ***이상한 숫자 에러*** : 컴퓨터가 숫자를 어떻게 표시할까
- ***C코드를 최적화 하는 방법*** : 최신 프로세서와 메모리 시스템의 설계를 활용하자
- ***컴파일러가 어떻게 프로시저 호출을 구현*** 할까
- ***버퍼 오버플로우 위험성*** 으로 부터 어떻게 시스템을 보호할 수 있을까
- ***링커 과정에서 발생하는 심각한 에러를 이해하여 어떻게 회피*** 할 수 있을지
- ***나만의 유닉스 쉘, 동적 메모리 할당 패키지, 그리고 웹서버를 작성하는 방법*** 은
- ***동시성의 가능성과 위험성*** : 멀티 프로세서 코어들이 한개의 칩에 집적되었을 때는

</br></br>

## 1.1 정보는 비트와 컨텍스트로 이루어진다

``` c
#include <stdio.h>

int main(){
    printf("Hello, world!\n");
    return 0;
}
```

| Code(txt) | `#` | `i` | `n` | `c` | `l` | `u` | `d` | `e` | `SP` | `<` | `s` | `t` | `d` | `i` | `o` | `.` | `h` | `>` | `\n` |
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|----------|
| **ASCII** | <div align="center">35</div> | <div align="center">105</div> | <div align="center">110</div> | <div align="center">99</div> | <div align="center">108</div> | <div align="center">117</div> | <div align="center">100</div> | <div align="center">101</div> | <div align="center">32</div> | <div align="center">60</div> | <div align="center">115</div> | <div align="center">116</div> | <div align="center">100</div> | <div align="center">105</div> | <div align="center">111</div> | <div align="center">46</div> | <div align="center">104</div> | <div align="center">62</div> | <div align="center">10</div> |
| **Byte**  | <div align="center">00100011</div> | <div align="center">01101001</div> | <div align="center">01101110</div> | <div align="center">01100011</div> | <div align="center">01101100</div> | <div align="center">01110101</div> | <div align="center">01100100</div> | <div align="center">01100101</div> | <div align="center">00100000</div> | <div align="center">00111100</div> | <div align="center">01110011</div> | <div align="center">01110100</div> | <div align="center">01100100</div> | <div align="center">01101001</div> | <div align="center">01101111</div> | <div align="center">00101110</div> | <div align="center">01101000</div> | <div align="center">00111110</div> | <div align="center">00001010</div> |

- 소스프로그램은 0 또는 1로 표시되는 비트들의 연속이며, 바이트라는 8비트 단위로 구성됨
- 아스키 문자들로만 이루어진 파일들은 **텍스트 파일**, 다른 모든 파일은 **바이너리 파일**이라 함

</br></br>

## 1.2 프로그램은 다른 프로그램에 의해 다른 형태로 번역된다

![컴파일 시스템](https://github.com/fsm12/Dev-Book/assets/74345771/004d52fb-f7d3-4126-9167-6a945f9c51c4)

- ***전처리 단계*** : 전처리기(cpp)는 본래의 C 프로그램을 #문자로 시작하는 디렉티브에 따라 수정
- ***컴파일 단계*** : 컴파일러(cc1)는 hello.i를 hello.s로 번역하며, 이 파일에는 어셈블리어 프로그램이 저장
- ***어셈블리 단계*** : 어셈블러(as)가 hello.s를 기계어 인스트럭션으로 번역하고, 재배치가능 목적프로그램의 형태로 묶어서 hello.o라는 목적 파일에 저장. 이 파일은 main 함수의 인스트럭셔들을 인코딩하기 위한 17바이트를 포함하는 바이너리 파일
- ***링크 단계*** : hello 프로그램에서 호출하는 printf 함수는 표준 C 라이브러리에 포함되어 있으며, 이미 컴파일된 별도의 목적파일인 printf.o 에 들어있음. 링커는 print.o 파일과 hello.o파일을 연결. 이 결과 실행가능 목적파일로 메모리에 적재되어 시스템에 의해 실행됨

</br></br>

## 1.3 컴파일 시스템이 어떻게 동작하는지 이해하는 것은 중요하다





</br>

## 1.4 프로세스는 메모리에 저장된 인스트럭션(명렁어)를 읽고 해석한다




</br>

## 1.5 캐시가 중요하다




</br>

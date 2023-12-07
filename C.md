
- [C언어](#c언어)
  - [특징](#특징)
  - [프로그래밍 언어 분류](#프로그래밍-언어-분류)
  - [C언어의 탄생](#c언어의-탄생)
  - [C언어 표준화 과정](#c언어-표준화-과정)
- [데이터 출력](#데이터-출력)
  - [데이터 출력 방법](#데이터-출력-방법)
    - [프로그램과 main 함수 구조](#프로그램과-main-함수-구조)
    - [문자열 출력](#문자열-출력)
    - [정수와 실수 출력](#정수와-실수-출력)
  - [상수와 데이터 표현 방법](#상수와-데이터-표현-방법)
    - [실수 상수 표현법](#실수-상수-표현법)
    - [문자와 문자열 상수 표현법](#문자와-문자열-상수-표현법)
    - [컴파일 된 데이터 크기](#컴파일-된-데이터-크기)
    - [정수가 컴파일 된 후의 비트 형태](#정수가-컴파일-된-후의-비트-형태)
    - [실수가 컴파일 된 후의 비트 형태](#실수가-컴파일-된-후의-비트-형태)
- [변수와 데이터 입력](#변수와-데이터-입력)
  - [정수 자료형](#정수-자료형)
  - [char형 변수](#char형-변수)
  - [unsigned 정수 자료형](#unsigned-정수-자료형)
  - [문자열 저장](#문자열-저장)
    - [문자열 복사](#문자열-복사)
  - [const 변수](#const-변수)
    - [예약어와 식별자](#예약어와-식별자)
  - [데이터 입력](#데이터-입력)
    - [문자와 문자열의 입력](#문자와-문자열의-입력)
- [연산자](#연산자)
    - [산술 연산자](#산술-연산자)
    - [논리 연산자](#논리-연산자)
    - [형 변환 연산자](#형-변환-연산자)
    - [sizeof 연산자](#sizeof-연산자)
    - [sizeof 연산자 괄호 주의](#sizeof-연산자-괄호-주의)
    - [콤마 연산자](#콤마-연산자)
    - [조건 연산자](#조건-연산자)
    - [비트 연산자](#비트-연산자)
    - [연산자 우선순위와 연산 방향](#연산자-우선순위와-연산-방향)
  - [if문](#if문)
  - [switch ~ case 문](#switch--case-문)
    - [break 생략](#break-생략)
- [반복문](#반복문)
  - [while](#while)
  - [for](#for)
  - [do ~ while](#do--while)
  - [분기문](#분기문)
- [함수](#함수)
  - [함수 정의](#함수-정의)
  - [재귀호출 함수](#재귀호출-함수)
- [배열](#배열)
  - [배열 초기화](#배열-초기화)
  - [sizeof 연산자를 활용한 배열 처리](#sizeof-연산자를-활용한-배열-처리)
  - [문자 배열](#문자-배열)
    - [문자열 대입](#문자열-대입)
    - [문자열 전용 입출력 함수](#문자열-전용-입출력-함수)
- [포인터](#포인터)
  - [주소 연산자](#주소-연산자)
    - [포인터와 간접 참조 연산자](#포인터와-간접-참조-연산자)
    - [const를 사용한 포인터](#const를-사용한-포인터)
  - [주소와 포인터](#주소와-포인터)
  - [포인터의 대입 규칙](#포인터의-대입-규칙)
- [배열과 포인터](#배열과-포인터)

```c
#include

/*
지정한 파일을 추가하는 지시자
```
## 특징

- 절차지향
- 컴파일 기반 (완전한 소스코드)
- 프로그래머가 메모리 관리
- 변수 유형 선언이 필요함

## 프로그래밍 언어 분류

- 기계어 : 2진법으로 구성 된 컴퓨터가 사용하는 언어
- 어셈블리어 : 사람이 조금 더 쉬운 명령어로 바꾼 언어
    
    어셈블리어와 기계어는 1:1 매핑관계
    
- 고급 언어 : 저급언어 보다 높은 언어

## C언어의 탄생

- 데니스 리치가 **유닉스** 시스템에 사용하기 위해 켄 톰슨의 B언어를 발전시켜 만든 언어
- 시스템 프로그래밍이 가능
- 이식성을 갖춘 프로그램
- 함수를 사용해 개별 프로그래밍이 가능

## C언어 표준화 과정

`K&R C` → `ANSI C` → `C99`

# 데이터 출력

## 데이터 출력 방법

### 프로그램과 main 함수 구조

- 머리 : int main(void)
- 몸통 : { ````
    
    return 0;
    
    }
    

### 문자열 출력

문자열 str : “ ”

문자  c : ‘ ’

→ \n : 줄바꿈

| \n | 줄바꿈 |
| --- | --- |
| \t | 탭 |
| \b | 한 칸 왼쪽으로 이동 |
| \r | 맨 앞으로 이동 |
| \a | 벨소리를 낸다 (bel) |

```c
#include <stdio.h>

int main(void)
{
    printf("Be happy\n");
    printf("12345\n");
    printf("Goot\bd\tchance\n");
    printf("Cow\rW\a\n");

    return  0 ;
}
/* 
Be happy
12345
Good	chance
Wow
*/
```

### 정수와 실수 출력

| %d | 정수 |
| --- | --- |
| %lf | 실수 |

```c
#include <stdio.h>

int main(void) {
    printf("%d\n", 10); // %d에 10
    printf("%lf\n", 3.4); // %lf 위치에 3.4를 소수점 이하 6까지
    printf("%.1lf\n", 3.45); // 첫째 자리까지 (반올림해서) 5부터 반올림
    printf("%.10lf\n", 3.4); // 10자리

    return 0;
}
/* 
10
3.400000
3.5
3.4000000000
*/
포맷 형식으로 생각하면된다. 
printf("%d 더하기 %d = %d", 10, 10, 20);
```

## 상수와 데이터 표현 방법

- 정수 상수
- 실수 상수

### 실수 상수 표현법

- 소수점 앞이나 뒤의 무의미한 0은 생략 가능
- 지수를 표현할 때 *10 을 e로 표현

정규화 : 한 자리수로 나타낸 실수형태

```c
#include <stdio.h>

int main(void) {
    printf("%.1lf\n", 1e6);
    printf("%.7lf\n", 3.14e-5);
    printf("%le\n", 0.0000314);
    printf("%.2le\n", 0.0000314);

    return 0;
}

/*
1000000.0
0.0000314
3.140000e-05
3.14e-05
*/
```

### 문자와 문자열 상수 표현법

- 문자는 ‘ ‘ , 문자열은 “ “

```c
#include <stdio.h>

int main(void)
{
    printf("%c\n", 'A');
    printf("%s\n", "A");
    printf("%c은 %s입니다.\n", '1', "first");

    return 0;
}

/* 
A
A
1은 first입니다.
*/
```

### 컴파일 된 데이터 크기

| 정수 | 4바이트 |
| --- | --- |
| 실수 | 8바이트 |
| 문자 상수(c) | (아스키코드값) 4바이트 |

### 정수가 컴파일 된 후의 비트 형태

음수는 절대값을 2의 보수로 바꾸어 변환

→ 2의 보수로 변환 시 양수와 음수를 더하는 데에 쉽다.

| 비트수  | 표현 범위 |
| --- | --- |
| 1비트 | 0 ~ 2^1-1 |
| 8비트 | 2^8 -1  |
| 32비트 | 2^32 - 1 |

### 실수가 컴파일 된 후의 비트 형태

- 64비트

IEEE 754 표준의 **double** (8*8) 형식에 따라 변환

부호비트(1개) → 지수부(11개) → 소수부(52개)

부호비트 : 0 → 양수 , 1 → 음수

ex) -6.5

부호비트 → -

지수부 → 6

소수부 → 5

- 소수부에 곱하기 2를 했을 때 10을 넘기면 1 넘기지 못하면 0

# 변수와 데이터 입력

## 정수 자료형

| 자료형 | 크기 | 범위 |
| --- | --- | --- |
| char | 1바이트 | -128 ~ 127 (아스키 코드와 동일) |
| short | 2바이트 |  |
| int | 4바이트 |  |
| long | 4바이트 |  |
| long long | 8바이트 |  |

## char형 변수

```c
#include <stdio.h>

int main(void)

{
    char ch1 = 'A';
    char ch2 = 65;

    printf("문자 %c의 아스키 코드 값 :  %d\n", ch1, ch1);
		printf("아스키 코드 값이 %d인 문자 : %c\n", ch2, ch2);

    return 0 ;
}

/*
문자 A의 아스키 코드 값 :  65
아스키 코드 값이 65인 문자 : A
*/
```

char는 정수로 표현 가능 → 아스키 코드 값

변수를 값을 채워 넣어줘야 함 (초기화)

값이 안채워 준다면 쓰레기 값(이상한)이 임의로 채워짐

## unsigned 정수 자료형

- 양수 전용
- %u 로 표기

```c
#include <stdio.h>

int main(void)

{
    unsigned  int a ;

    a = 4294967295;
    printf("%d\n", a);
    printf("%u\n", a);

    return 0;
}

/*
-1
4294967295
*/
```

- -1
4294967295

이 둘은 메모리 내에 저장된 형태가 같다

그냥 %d를 쓰게 되면 저장할 수 있는 범위가 작지만

unsigend를 써서 %u를 쓰면 양수만을 저장하기 때문에 두배 더 넓은 범위의 값을 저장한다.

## 문자열 저장

- char 배열명[문자열길이 + 1] = 문자열;
    
    이 때 문자열길이 + 1는 최소를 뜻한다. → 이것 보다 크면 됨.
    

컴파일러가 문자열의 끝에 \0(널 문자)를 자동적으로 추가하기 때문에 +1을 해준다.

```c
char fruit[6] = "apple";
```

```c
#include <stdio.h>

int main(void)

{
    char fruit[20] = "strawberry";

    printf("딸기 : %s\n", fruit);
    printf("딸기잼 : %s %s\n", fruit, "jam");

    return 0;
}
```

### 문자열 복사

- 문자열을 다룰 수 있는 헤더 파일
    
    string.h → strcpy 함수(복사 함수) 사용 가능
    

```c
#include <stdio.h>
#include <string.h>

int main(void)
{
    char fruit[20] = "strawberry";

    printf("%s\n", fruit);
    strcpy(fruit, "banana");
    printf("%s\n", fruit);

    return 0;
}

/*
strawberry
banana
*/
```

## const 변수

- 선언과 동시에 초기화를 해야함
- 초기화 하지 않으면 변수의 쓰레기 값이 계속 사용 됨.
- 변수 앞에 const를 붙이면 초기화된 값을 바꿀 수 없다.
- 초기화 이후에 바꾸게 되면 에러 메세지가 뜬다.

### 예약어와 식별자

```c
int age;
예약어 식별자
		 (변수)
```

## 데이터 입력

- scanf(”%d”, &a)
- & : 앰퍼샌드

```c
#include <stdio.h>

int main(void)
{
    int a;

    scanf("%d", &a);
    printf("입력된 값 : %d\n", a);

    return 0;
}

/*
10
입력된 값 : 10
```

%d 즉 int형 변환 문자를 사용했는데, 변환 문자와 맞지 않는 데이터를 입력하게 된다면 쓰레기 값이 나온다.

```c
#include <stdio.h>

int main(void)
{
    int a;
    double b;

    scanf("%d%lf", &a, &b);
    printf("%d, %lf", a, b);
    return 0;
}
```

### 문자와 문자열의 입력

- char형 변수에 문자를 입력할 때는 스페이스 도 문자로 전달하기 때문에 문자열을 입력받는 scanf에서는 배열(변수명)에 &기호를 사용하지 않는다.

```c
#include <stdio.h>

int main(void)
{
    char grade;
    char name[20];

    printf("학점 입력 : ");
    scanf("%d", &grade);

    printf("이름 입력 : ");
    scanf("%s", name); // name 앞에 & 없음

    printf("%s의 학점은 %d 입니다.", name, grade);

    return 0;
}

/*
학점 입력 : 100
이름 입력 : 황시훈
황시훈의 학점은 100 입니다.
```

- 둘 이상의 데이터를 입력할 때는
    
    스페이스바, 탭, 엔터
    
- 문자열 입력은 char 배열을 이용하며 배열명 앞에 &기호를 사용하지 않는다.

```c
#include <stdio.h>

int main(void)
{
    char ch;

    printf("문자 입력 : ");
    scanf("%c", &ch);
    printf("%d", ch);

    return 0;
}

/*
문자 입력 : A
65
```

# 연산자

### 산술 연산자

- = : 대입 연산자

| 산술 연산자 | 기호 |
| --- | --- |
| 더하기 | + |
| 빼기 | - |
| 곱하기 | * |
| 나누기 | / |
| 나머지 | % |

| 증감 연산자 | 기호 |
| --- | --- |
| 1씩 증가 | ++ |
| 1씩 감소 | -- |

++a → 전위형 : 연산 전 증가

a++ → 후위형 : 연산이 끝난 후 증가

### 논리 연산자

| 논리 연산자 | 기호 |
| --- | --- |
| AND | && |
| OR | ㅣㅣ |
| NOT | ! |

논리 연산자의 결과값은 1 또는 0으로 나타난다.

- 숏 서킷 룰
    
    좌항만으로 연산의 결과를 판별하는 기능이다.
    
    ex : 좌항이 거짓이면 우항은 거짓
    

### 형 변환 연산자

```c
(자료형)피연산자
```

- 정수를 실수로 바꾸는 경우
    - (double)피연산자정수
- 실수를 정수로 바꾸는 경우
    - (int)피연산자실수

```c
#include <stdio.h>

int main(void)
{
   int a = 10;
   double res;

   res = (double)a;

   printf("%lf", res);

    return 0;
}

/* 10.000000
```

실수를 정수로 바꾸게 되면 ************************************버림************************************이 일어난다.(반올림 X)

- 자동 형 변환
    - 크기가 작은 값이 크기가 큰 값으로 바뀌는

### sizeof 연산자

함수가 아니다 **연산자**다.

- sizeof(피연산자)
    - 피연산자 : 변수, 상수, 수식, 자료형 등

```c
#include <stdio.h>

int main(void)
{
   int a = 10;
    printf("a 변수 크기는 : %d", sizeof(a));

    return 0;
}

/*
a 변수 크기는 : 4
```

### sizeof 연산자 괄호 주의

```c
printf("수식의 결과값의 크기 : %d\n", sizeof 1.5 + 3.4);

// sizeof 1.5를 먼저 연산 하고 이 값을 가지고 + 3.4를 연산한다.
```

### 콤마 연산자

- 콤마 연산자(,)는 나열의 기능도 있지만 **가장 오른쪽의 피연산자가 최종 결과값이 된다.**
- 콤마 연산자는 우선순위가 대입 연산자 보다 낮다.
- 결과적으로 괄호를 붙여야 함.

✏️✏️✏️✏️✏️✏️✏️✏️✏️✏️✏️✏️✏️✏️✏️✏️✏️

```c
res = (++a, ++b);
// res = ++a이후 ++b의 연산 수행
// 결과로 res에 증가된 b의 값 저장

res = ++a, ++b;
// 결과로 res에 증가된 a의 값 저장
// res = ++a; ++b;와 같다.
```

- 괄호 주의

```c
#include <stdio.h>

int main(void)
{
   int a = 1;
   int b = 2;

   int res;

   res = (++a, ++b);

   printf("%d", res);

   return 0;
}
// 3
-------------------------
#include <stdio.h>

int main(void)
{
   int a = 1;
   int b = 2;

   int res;

   res = ++a, ++b;

   printf("%d", res);

   return 0;

}
// 2
```

### 조건 연산자

```c
res = (a > b) ? a : b
// a>b라는 조건이 참이라면? a 선택, res에 a 대입
// 거짓이라면? b선택, res에 b 대입

(a > b) ? (res = a) : (res = b);
//동일
```

- 첫 번째 피연산자가 참이면 두 번째 피연산자가 결괏값이 되고
- 첫 번째 피연산자가 거짓이면 세 번째 피연산자가 결괏값이 된다.

### 비트 연산자

| 기호 | 설명 |
| --- | --- |
| & | 비트 논리 곱 연산 |
| ^ | 비트 배타적 논리합 |
| || | 비트 논리 합 연산 |
| ~ | 비트 반전 |
| << | 비트 왼쪽으로 이동 |
| >> | 비트 오른쪽으로 이동 |
- 비트 왼쪽 이동연산자 에서,

왼쪽으로 이동 시 오른쪽은 0으로 채워 준다.

- 비트 오른쪽 이동연산자 에서,

양수라면 오른쪽으로 이동 시 왼쪽의 남는 비트는 0으로 채워주고

- 비트 왼쪽 이동연산자 에서,

음수라면 오른쪽으로 이동 시 왼쪽의 남는 비트는 1로 채워준다.

만약 unsigned라면 무조건 0으로 채움

### 연산자 우선순위와 연산 방향

- 단항 연산자(++, --, !, sizeof) > 이항 연산자(산술, 비교, 논리, 비트, 시프트) > 삼항 연산자(?)
- 산술 연산자(+) > 비트 이동 연산자(>>) > 관계 연산자(>) > 논리 연산자(&&)

## if문

```c
if (조건식 1)
{
	실행문1;
}
else if (조건식 2)
{
	실행문2;
}
else
{
	실행문3;
}
```

## switch ~ case 문

```c
switch (조건식)
{
case 상수식1:
	실행문1;
	break;
case 상수식2:
	실행문2;
	break
default:
	실행문3;
	break;
}
```

- 조건식은 정수식만 사용한다.
- 기본적으로 case와 break 포함한다.
- 조건식을 만족하지 않으면, default로 넘어간다. 생략가능

### break 생략

switch case 문에 break가 없다면

모든 case들을 거쳐서 결과를 낸다.

# 반복문

## while

```c
while (조건식)
{
	실행문;
}

//조건식에 벗어날 때 까지 계속 반복
```

## for

```c
for (초기식; 조건식; 증갑식) // 모두 i에 대한 것이다.
{
	실행문; // i 유무 상관 없음
}
```

## do ~ while

- while과 조건식의 위치가 다르다.

```c
do
{
	반복할 문장;

} while (조건식);

// do 이후에 중괄호 부분을 한 후 while 조건식을 판별. 반복
```

## 분기문

| 분기문 | 설명 |
| --- | --- |
| break | 반복을 끝내고 싶을 때 사용 |
| continue | 반복문의 일부를 건너 뛴다. |
- break는 무한루프에서 빠져나오고 싶을 때 사용한다.
- continue의 사용

```c
for (i = 1; i <= 100; i++)
{
	if ((i%3) ==0)
		{
				continue;
		}
	sum += i;
}
// 3의 배수를 뺀 1부터 100까지의 합
```

# 함수

- 함수 중요 3가지
    - 함수 정의 : 함수를 실제 코드로 만드는 것이며 기능을 구현
    - 함수 호출
    - 함수 선언

## 함수 정의

1. 함수명 : 함수의 기능에 맞는 이름은 무엇인가?
2. 매개변수 : 함수가 기능을 수행하는 데 필요한 데이터는 무엇인가?
3. 반환형 : 함수가 수행된 이후의 결과는 무엇인가?

```c
반환형 함수명(매개변수1, 매개변수2)
{
명령
}
```

- sum함수 작성

```c
#include <stdio.h>

int sum(int x , int y); // 함수 선언

int main(void)
{
    int a, b;
    int result;

    scanf("%d%d", &a, &b);

    result = sum(a, b); // 함수 호출

    printf("%d", result);

    return 0;
}

int sum(int x, int y) // 함수 정의
{
    int temp;

    temp = x + y;

    return temp; // temp는 잠시 저장하는 역할이지만 없이 서도 무관
}
```

- 함수가 호출된면 main함수의 실행은 멈추고 sum함수 정의 부분에 있는 코드가 실행
- sum함수 내부에 입력값을 받는 변수를 만든다면, sum함수 매개변수 란에 void(값x) 사용 가능 → 호출할 땐 sum() 빈 란
- 매개변수와 반환값이 모두 없는 함수는 반환형에 모두 void를 쓴다.

## 재귀호출 함수

```c
# include <stdio.h>

void fruit(int count);

int main(void)
{
    fruit(1);

    return 0;
}

void fruit(int count)
{
    printf("apple\n");
    if (count ==3)
  	 return; // count 3이면 반환, 끝냄
    fruit(count + 1);
}
```

```c
# include <stdio.h>

void fruit(int count);

int main(void)
{
    fruit(1);

    return 0;
}

void fruit(int count)
{
    printf("apple\n");
    if (count ==3) return;
    fruit(count + 1);
    printf("jan\n");
}

/*
apple
apple
apple
jan
jan
*/
```

나의 생각으론

apple

jan

apple

jan

apple

이 출력될 것이라고 생각했다.

하지만 → 재귀호출은

최초에 호출했던 곳이 아닌 직전에 호출했던 곳으로 간다.

# 배열

`자료형 배열명[요소개수];`

`ary, [2] : 배열명, 첨자`

- 각각 변수를 선언하면 각 변수는 독립적인 저장공간을 갖는다. 하지만 배열은 나누어서 갖게 된다.

## 배열 초기화

```c
int ary[5] = {1, 2, 3, 4, 5}; // 5개의 요소에 값들을 추가

int ary[5] = {1, 2, 3}; // 1, 2, 3를 저장하고 나머지 0으로 저장

int ary[1000] = {0}; // 모두 0으로 저장

int ary[] = {1, 2, 3, 4, 5} // 자동으로 저장공간 생성 후 초기화
```

## sizeof 연산자를 활용한 배열 처리

`sizeof(배열명) / sizeof(배열 요소)`

- 배열 전체 크기를 구할 때 사용

```c
count = sizeof(배열명) / sizeof(배열요소)
```

## 문자 배열

- char형 배열 선언에서 문자열의 길이보다 최소한 하나 이상 크게 배열을 선언해야 한다.
    - → NULL(\0)을 저장하기 위함.
        - NULL은 끝 값을 표기하는 용도
- printf 함수는 char형 배열에서 널 문자가 나올 때까지만 출력
- 배열에 값을 직접 문자로 초기화 할 때는 마지막에 널 문자를 대입해야 한다.

### 문자열 대입

char형 배열이 초기화 된 이후, 새로운 문자열을 대입 하려면 strcpy함수를 사용해야 한다.

`strcpy()`

→ 사용하려면 `#include <string.h>`

```c
#include <stdio.h>
#include <string.h>

int main(void)
{
    char str1[80] = "cat"; // str1변수 초기화
    char str2[80];

    strcpy(str1, "tiger"); //tiger을 str1에 대입
    strcpy(str2, str1);
    printf("%s, %s\n", str1, str2);

    return 0;
}

// tiger, tiger
```

### 문자열 전용 입출력 함수

`gets()`, `puts()`

gets 함수는 빈칸을 포함한 새로운 문자열 입력 방식이다.

puts 함수는 gets의 이용으로 출력을 하는 함수이다.

- scanf 함수는 하나의 단어만 입력
- gets 함수는 한 줄 입력
- printf 함수는 문자열 출력
- puts 함수는 문자열 출력 후 줄 바꿈

```c
#include <stdio.h>

int main(void)
{
    char str[80];

    printf("문자열 입력 : ");
    fgets(str, 80, stdin);
    puts("입력된 문자열 : ");
    puts(str);

    return 0;
}

/*
문자열 입력 : abc d e
입력된 문자열 : 
abc d e
*/
```

# 포인터

포인터는 물감과 같다.

메모리는 팔레트.

```c
int main(void)
{
	int a ;
}

int ex(void)
{
	int a ;
}
```

- 여기서의 a는 서로 다른 변수이다. (서로다른 공간)

## 주소 연산자

`&a`

주소 : 변수가 할당된 메모리 공간의 시작 주소를 의미한다.

주소는 주소연산자 &을 사용해 구한다.

주소는 보통 16진수로 표기한다. 그래서 주소를 출력할 때는 전용 변환문자인 %p를 사용하는 것을 권장

`printf(”%p”, &a)`

### 포인터와 간접 참조 연산자

포인터 : 변수의 메모리 주소를 저장하는 변수

주소를 저장할 포인터도 변수처럼 선언하고 사용한다.

사용할 때는 변수 앞에 *만 붙여주면 됨

`int *pa`

`pa = &변수`

- 포인터는 주소를 나타낸다.

```c
#include <stdio.h>

int main(void)
{
    int a ;
    int *pa;

    pa = &a; // 포인터에 a의 주소 대입 // pa -> a를 가르킨다.
    *pa = 10; // 포인터로 변수 a 에 10 대입

    printf("포인터로 a 값 출력 : %d\n", *pa);
    printf("변수명으로 a 값 출력 : %d\n", a);

    return 0 ;
}

10
10
```

* ← 간접 참조 연산자 or 포인터 연산자

- 변수 a의 저장 공간 찾기
    - `scanf(”%d”, &a)`
    - `scanf(”%d”, pa)`

---

- ex : 포인터를 사용한 두 정수의 합과 평균 계산

### const를 사용한 포인터

- 가리키는 변수의 값을 바꿀 수 없다는 의미

```c
#include <stdio.h>

int main(void)
{
    int a = 10, b = 20;
    const int *pa = &a; // 포인터 pa는 변수 a를 가리킨다.

    printf("변수 a의 값 : %d\n", *pa);
    pa = &b; // 포인터pa가 변수 b를 가리킨다.
    printf("변수 b의 값 : %d\n", *pa);
    pa = &a; // 포인터pa가 변수 a를 가리킨다.
    a = 20; // 변수 a의 값을 20으로 지정
    printf("변수 a의 값 : %d\n", *pa);

    return 0 ;
}

/*
변수 a의 값 : 10
변수 b의 값 : 20
변수 a의 값 : 20
*/
```

`*pa = 20` 처럼 직접적으로 값을 변경한다면 에러 메세지가 출력된다.

## 주소와 포인터

주소 : 변수에 할당된 메모리 저장공간의 시작 주소 값 자체이다., 상수

포인터 : 그 값을 저장하는 또 다른 메모리 공간이다., 변수

```c
int a, b;
int *p;
p = &a;
p = &b;
```

p는 변수처럼 유동적이다.

하지만 a와 b같은 주소의 경우 상수이다.

## 포인터의 대입 규칙

같은 자료형에 대해서만 포인터 끼리의 대입이 가능하다.

# 배열과 포인터

`주소 + 정수 → 주소 + ( 정수 * 주소를 구한 변수의 크기 )`

```c
#include <stdio.h>

int main(void)
{
    int ary[3];
    int i ;

    *(ary + 0) = 10;
    *(ary + 1) = *(ary + 0) + 10;

    printf("세 번째 배열 요소에 키보드 입력 : ");
    scanf("%d", ary + 2);

    for (i = 0; i < 3; i++)
    {
        printf("%5d", *(ary + i));

    }
    return 0 ;
}

/*
세 번째 배열 요소에 키보드 입력 : 30
   10   20   30
*/
```


# C

# 배열과 포인터

ary[n] = k → 값임.

## 배열과 포인터의 관계

배열은 자료형이 같은 변수를 메모리에 연속으로 할당한다.

따라서 각 배열 요소는 일정한 간격으로 주소를 갖게 된다. 응 맞아

### 배열명으로 배열 요소 사용하기

주소는 정수처럼 보이지만 자료형에 관한 정보를 갖고 있는 특별한 값이다.

`주소 + 정수 → 주소 + (정수 * 주소를 구한 변수의 크기)`

### 배열명에 정수 연산을 수행해 배열 요소 사용

```c
#include <stdio.h>

int main(void)
{
    int ary[3];
    int i;

    *(ary + 0) = 10;
    *(ary + 1) = *(ary + 0) + 10;

    printf("세 번째 배열 요소에 키보드 입력 : ");
    scanf("%d", ary + 2);
    
    for (i = 0; i < 3; i++)
    {
        printf("%5d", *(ary + i));
    }

    return 0;
}
```

### 배열명 역할을 하는 포인터

배열명은 주소여서 포인터에 저장할 수 있다.

### 배열명처럼 사용되는 포인터

```c
#include <stdio.h>

int main(void)
{
    int ary[3];
    int *pa = ary;
    int i;

    *pa = 10;
    *(pa + 1) = 20;
    pa[2] = pa[0] + pa[1];

    for(i=0; i<3; i++)
    {
        printf("%5d", pa[i]);
    }
    return 0;
}
```

### 배열명과 포인터의 차이

- sizeof 연산의 결과가 다름
- 변수와 상수의 차이

```c
int ary[3];
int *pa = ary;

sizeof(ary) // 12바이트, 배열 전체 크기
sizeof(pa) // 4바이트, 포인터 하나의 크기
```

```c
pa = pa + 1
pa ++ // 가능

ary = ary + 1
ary ++ // 불가능
```

괄호를 간접 참조 연산자에 먼저 사용하면 안된다.

### 포인터의 뺄셈과 관계 연산

`포인터 - 포인터 → 값의 차 / 가리키는 자료형의 크기`

`printf(”pb - pa : %u\n”, pb - pa);` → 간격을 알 수 있다.

## 정리

- 배열명은 첫 번째 요소의 주소다.
- 포인터에 배열명을 저장하면 포인터를 배열명처럼 사용할 수 있다.
- 배열명의 정수 덧셈은 가리키는 자료형의 크기를 곱해서 더한다.
- 포인터의 뺄셈 결과는 배열 요소 간의 간격 차이를 의미한다.

## 배열을 처리하는 함수

### 배열의 값을 출력하는 함수

```c
#include <stdio.h>

void print_ary(int *pa);
int main(void)
{
    int ary[5] = {1, 2, 3, 4, 5};

    print_ary(ary);

    return 0;
}

void print_ary(int *pa)
{
    int i;

    for(i=0; i<5; i++)
    {
        printf("%d ", pa[i]);
    }
}
```

### 배열 요소의 개수가 다른 배열도 출력하는 함수

```c
#include <stdio.h>

void print_ary(int *pa, int size);
int main(void)
{
    int ary[5] = {1, 2, 3, 4, 5};

    print_ary(ary);

    return 0;
}

void print_ary(int *pa, int size)
{
    int i;

    for(i=0; i<size; i++)
    {
        printf("%d ", pa[i]);
    }
}
```

### 배열에 값을 입력하는 함수와 최댓값을 찾는 함수 ⁉️

```c
#include <stdio.h>

void input_ary(double *pa, int size);
double find_max(double *pa, int size);

int main(void)
{
    double ary[5];
    double max;
    int size = sizeof(ary) / sizeof(ary[0]);

    input_ary(ary, size);
    max = find_max(ary, size);
    printf("배열의 최댓값 : %.1lf\n", max);

    return 0;
}
void input_ary(double *pa, int size)
{
    int i;
    for(i=0; i<size; i++)
    {
        scanf("%lf", &pa[i]);
    }
}
double find_max(double *pa, int size)
{
    int i;
    double max = pa[0];
    for(i=0; i<size; i++)
    {
        if (max <= pa[i])
        {
            max = pa[i];
        }
    }
    return max;
}
```

### 도전 실전 예제

로또 번호

```c
/* 1~45 중에 6개의 서로 다른 수를 입력하고 출력 입력한 수가 이미 저장된 수와 같으면 에러메세지를 출력하고 다시 입력 */

#include <stdio.h>

void input_nums(int *lotto_nums);
void print_nums(int *lotto_nums);

int main(void)
{
    int lotto_nums[6];

    input_nums(lotto_nums);
    print_nums(lotto_nums);
    return 0;
}
void input_nums(int *lotto_nums)
{
    int i;
    int j;
    for(i=0; i<6; i++)
    {
        printf("번호 입력 : ");
        scanf("%d", &lotto_nums[i]);
        for(j=0; j<i; j++)
        {
            if(lotto_nums[i] == lotto_nums[j])
            {
                printf("같은 번호가 있습니다!\n");
                printf("번호 입력 : ");
                scanf("%d", &lotto_nums[i]);
            }
        }
    }
}
void print_nums(int *lotto_nums)
{
    int i;

    printf("로또 번호 : ");

    for(i=0; i<6; i++)
    {
        printf("%d ", lotto_nums[i]);
    }
}
```

# 문자

## 아스키 코드 값과 문자 입출력 함수

- 알파벳과 숫자는 각각 연속된 아스키 코드 값을 갖는다.
- 소문자가 대문자보다 아스키 코드 값이 크다.
- 제어 문자는 백슬래시와 함께 표시하며 출력할 때 그 기능을 수행한다.

### 대문자를 소문자로 변경

```c
#include <stdio.h>

int main(void)
{
    char small, cap = 'G';

    if ((cap >= 'A') && (cap <= 'Z'))
    {
        small = cap + ('a' - 'A');
    }
    printf("대문자 : %c %c", cap, '\n');
    printf("소문자 : %c", small);

    return 0 ;
}
```

### 공백이나 제어 문자의 입력

- %c 변환 문자는 공백, 탭, 개행 문자도 입력한다.

```c
#include <stdio.h>

int main(void)
{
    char ch1, ch2;

    scanf("%c%c", &ch1, &ch2);

    printf("[%c%c]", ch1, ch2);

    return 0 ;
}
```

### getchar, putchar

- `int getchar(void);` : 매개변수 x, 입력한 문자를 반환 // int형인 이유 : 문자 이외의 값도 반환
- `int putchar(int);` : 출력할 문자를 인수로 준다.

```c
#include <stdio.h>

int main(void)
{
    int ch;

    ch = getchar();
    printf("입력한 문자 : ");
    putchar(ch);
    putchar('\n');

    return 0;

}
```

## 버퍼를 사용하는 입력 함수

### 버퍼를 사용하는 문자 입력

```c
#include <stdio.h>

int main(void)
{
    char ch;
    int i;

    for (i=0; i<3; i++)
    {
        scanf("%c", &ch);
        printf("%c", ch);
    }

    return 0;

}
```

### scanf 함수 반환값 활용

```c
#include <stdio.h>

int main(void)
{
    char ch;

    int res;

    while (1)
    {
        res = scanf("%c", &ch);
        if (res == -1) break;
        {
            printf("%d ", ch);
        }
    }

    return 0;

}
```

### getchar() 를 이용한 문자열 입력

```c
#include <stdio.h>

void my_gets(char *str, int size);

int main(void)
{
    char str[7];

    my_gets(str, sizeof(str));
    printf("입력한 문자열 : %s\n", str);

    return 0;
}

void my_gets(char *str, int size)
{
    int i = 0;
    int ch;
    ch = getchar();

    while ((ch != '\n') && (i < size-1))
    {
        str[i] = ch;
        i++;
        ch = getchar();
    }
    str[i] = '\0';
}
```

### 입력 버퍼 지우기

```c
#include <stdio.h>

int main(void) {
    int num, grade;

    printf("학번 입력 : ");
    scanf("%d", &num);
    **getchar();       // <- 이 함수를 사용해 초기화 개행문자 \n을 없앰**
    printf("학점 입력 : ");
    grade = getchar();
    printf("학번 : %d, 학점 : %d", num, grade);

    return 0;
}
```

# 문자열

## 문자열과 포인터

- 문자열 (상수)는 값을 바꿀 수 없다! ⁉️

---

이 부분 중요함.⁉️

```c
#include <stdio.h>
 
int main(void) {
    char str[80];

    printf("문자열 입력 : ");
    scanf("%s", str);
    printf("첫 번째 단어 : %s\n", str);
    scanf("%s", str);
    printf("버퍼에 남아 있는 두 번째 단어 : %s\n", str);

    return 0;
}

/*
문자열 입력 : apple jam
첫 번째 단어 : apple
버퍼에 남아 있는 두 번째 단어 : jam
*/
```

버퍼에 저장되는 처음 scanf경우 → apple jam\n

엔터를 누르게 되면 apple\0이 str에 저장이 됨. (\0 널 문자는 자동으로 붙여짐)

그러면 버퍼에 jam\0이 저장됨. (\0 널 문자는 자동으로 붙여짐)

### gets 함수를 사용한 문자열 입력

- 공백이 포함된 문자열을 한 번에 입력할 수 없다.

apple jam\0이 저장됨.

- gets함수는 엔터만 눌러도 입력을 끝낸다.

### fgets 함수를 사용한 문자열 입력

`fgets(str, sizeof(str), stdin);` // 배열명, 배열의 크기 확인, 표준 입력

```c
#include <stdio.h>

int main(void) {

    char str[80];

    printf("공백이 포함된 문자열 입력 : ");
    fgets(str, sizeof(str), stdin);
    printf("입력된 문자열은 %s입니다\n", str);

    return 0 ;
}

/*
공백이 포함된 문자열 입력 : apple jam
입력된 문자열은 apple jam
입니다
*/
```

### puts

- puts : 문자열을 출력하고 자동 줄 바꿈
- fputs : 문자열을 출력하고 줄을 바꾸지 않음

## 문자열 연산 함수

- `strcpy(str1, str2)` : str2를 복사해 str1에 복사
- `strncpy(str1, str2, n)` : str2를 n개만큼 복사해 str1에 저장
- `strcat(str, “문자열”)` : str에 문자열을 붙임
- `strncat(str, “문자열”, n)` : str에 문자열을 n개만큼 붙임
- `strlen(str1)` : str1의 길이를 구함
- `strcmp(str1, str2)`  : str1과 str2의  사전순으로 비교 ; 1 → str1이 나중에 나온다. 0 → 동일 -1 → str2가 우선
- `strncmp(str1, str2, n)` : 앞에서부터 n개만큼 비교

# 변수의 영역과 데이터 공유

`auto 자료형 변수명;` = `자료형 변수명;`

- auto : 지연변수를 뜻한다.

## 변수 사용 영역

### 지역변수

지금까지 사용했던 변수

- 지역 변수는 사용 범위가 블록 내부로 제한되므로 다른 함수에서는 사용할 수 없다.

### 지역 변수 사용의 장점

- 메모리를 효율적으로 사용
- 디버깅에 유리

### 블록 안에서 사용하는 지역변수

- 특정 블록 안에 변수를 선언하면 사용 범위가 블록 내부로 제한된다.
- 사용 가능한 변수가 둘 이상이면 가장 가까운 블록에 선언된 변수를 사용한다.

### 전역변수

```c
#include <stdio.h>

void assign10(void); // 함수 선언
void assign20(void); // 함수 선언

int a; // a변수 선언

int main(void)
{
    printf("함수 호출 전 a 값 : %d\n", a);

    assign10(); // 함수 호출
    assign20(); // 함수 호출

    printf("함수 호출 후 a 값 : %d\n", a);

    return 0;
}

void assign10(void)
{
    a = 10; // a의 값 초기화
}

void assign20(void)
{
    int a; // a를 선언. 그러나 전역변수가 있어서 사용 불가

    a = 20; // a의 값을 초기화
}
```

함수 밖에 변수를 선언하면 전역 변수가 된다.

- 프로그램이 끝날 때 까지 존재한다.

a를 전역변수를 20으로 값을 할당 후 void temp() 함수에서 10으로 값을 초기화를 한다면 void temp()함수에서는 a의 값을 10으로 초기화 후 사용이 가능하고 그 외의 함수에서는 모두 값이 20이다.

- 전역 변수는 0으로 자동 초기화 된다.

### 전역 변수의 문제점

- 전역 변수의 이름을 바꾸면 그 변수를 사용하는 모든 함수를 찾아 수정해야 한다.
- 전역 변수의 값이 잘못된 경우 접근 가능한 모든 함수를 의심해야 한다.
- 코드블록 내에 같은 이름의 지역 변수를 선언하면 거기서는 전역 변수를 사용할 수 없다.

### 정적 지역 변수

`static` : 함수가 끝나도 메모리를 반납하지 않음, 사용 범위가 블록 내로 제한

```c
#include <stdio.h>

void auto_func(void);
void static_func(void);

int main(void)
{
    int i;

    printf("일반 지역 변수(auto)를 사용한 함수...\n");
    for(i = 0; i < 3; i ++)
    {
        auto_func();
    }

    printf("정적 지역 변수(static)를 사용한 함수...\n");
    for(i = 0; i < 3; i ++)
    {
        static_func();
    }

    return 0;
}

void auto_func(void)
{
    auto int a = 0;

    a++;
    printf("%d\n", a);
}

void static_func(void)
{
    static int a;
    a++;
    printf("%d\n", a);

}
```

### 레지스터 변수

- 처리속도가 빠름
- CPU안에 있는 레지스터를 이용
- CPU 자원을 잠깐 빌리는 것

```c
#include <stdio.h>

int main(void)
{
    register int i; // 레지스터 변수 선언
    auto int sum = 0; // auto 지역 변수

    for (i = 1; i <= 10000; i++) // 반복
    {
        sum += i; // i 누적
    }
    printf("%d\n", sum);

    return 0;
}
```

## 함수의 데이터 공유 방법

### 값을 복사해서 전달하는 방법

```c
// 인공지능학과 2023240043 황시훈
#include <stdio.h>

void add_ten(int a);

int main(void)
{
    int a = 10;

    add_ten(a);
    printf("a : %d\n", a);

    return 0;
}

void add_ten(int a)
{
    a = a +10;
}

// a : 10
```

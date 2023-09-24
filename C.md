# C언어

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

K&R C → ANSI C → C99

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
| OR | || |
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

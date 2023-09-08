# C언어

# 상수와 데이터 출력

## 데이터 출력 방법

### 프로그램과 main 함수 구조

- 머리 : int main(void)
- 몸통 : { ````
    
    return 0;
    
    }
    

### 문자열 출력

문자열 str : “ ”

문자  c : ‘ ’

```c
#include <stdio.h> // stdio : standard input, output

int main(void)
{
    printf("Be happy");
    printf("My friend");

    return 0 ;
}

// Be happyMy friend
```

이처럼 문자열이 붙여져서 출력된다.

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

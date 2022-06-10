# C_study

|자료형|비트|범위|
|------|---|---|
|short|16비트|-32768~32767|
|int|32비트|-2137483648~2147483647|
|long|32비트|-2137483648~2147483647|
|long long|64비트|-9,223,372,036,854,775,808~9,223,372,036,854,775,807|
|unsigned short|16비트|0~65535|
|unsigned int|32비트|0~4294967295|
|unsigned long|32비트|0~4294967295|
|unsugned long long|64비트|0~18,446,744,073,709,551,615|


- 기호상수
    - 보통의 상수에는 변수와는 달리 이름이 없다. 그러나 상수에도 이름을 붙일 수 있는 방법이 있다. 그러나 상수에도 이름을 붙일 수 있는 방법이 있다. 기호 상수(symbolic constat)는 기호에 의하여 상수를 표현한 것이다. 달러에 환율을 곱하여 달러를 원하로 변경하는 아래의 두 문장은 같은 의미이며 EXCHANGE_RATE가 기호 상수이다.

```
won = 1120 * dollar;  (1) 실제의 값을 사용
won = EXCHANGE_RATE * dollar; (2) 기호상수 사용
```

기호 상수는 실제 값을 그대로 쓰는 방법에 비하여 몇 가지의 장점을 지닌다. 첫 번째 장점은 기호 상수를 사용하면 프로그램을 읽기가 쉬워진다는 것이다. 문자 (1)에서는 1120이 무엇을 의미하는지 쉽게 알 수 없다. 그러나 문장 (2)에서는 1120이 환율이라는 것을 쉽게 알 수 있다.

기호 상수의 두 번째 장점은 상수 값을 변경하려고 하는 경우에, 쉽게 할 수 있다는 것이다. 위에 예에서 환율이 1050으로 변경되었다고 가정하자. 만약 숫자를 사용했다면 프로그램에서 그 숫자가 사용된 모든 곳을 찾아서 값을 변경하여야 한다. 그러나 기호 상수를 사용했다면 기호 상수의 정의만 변경하면 된다.
```
#include <stdio.h>

int main(void)
{
 won1 = 1120 * dollar1;
 won2 = 1120 * dollar2;
}
```
리터럴 상수를 사용하는 경우:
등장하는 모든 곳을 수정하여야 한다.
```
#include <stdio.h>
#define EXCHANGE_RATE 1120

int main(void)
{
 won1 = EXCHANGE_RATE * dollar1;
 won2 = EXCHANGE_RATE * dollar2;
}
```
기호 상수를 사용하는 경우:
기호 상수가 정의된 곳만 수정하며 한다.

기호 상수를 선언하는 방법에는 다음과 같이 2가지가 있다.

① #define 문장 사용
```
Syntax: 기호상수선언
예) #define EXCHANGE_RATE 1120
```
위의 문장의 의미는 EXCHANGE_RATE라는 기호를 1120으로 정의한다는 의미이다. #define이 들어가는 문장은 보통 컴파일러가 동작하기 전에 전처리기(preprocessor)가 처리한다. 전처리기는 소스에서 EXCHANGE_RATE를 모두 찾아서 1120으로 바꾼다.

일반적으로 기호 상수 이름은 다른 이름과의 구별을 위하여 대문자로 만든다. 이것은 꼭 그래야 하는 것은 아니고 소문자로 하여도 전혀 문제는 없다. 또한 이 문장은 세미콜론으로 끝나지 않음을 주의하라. 이것은 문장이 아니고 단순히 기호를 값으로 대체하는 하라는 명령을 전처리기에 알려주는 역할만 하기 떄문이다. 즉 전처리기 문장은 정식 문장이 아닌 것이다.
② const 키워드 사용
```
Syntax: 기호상수선언
예) const int EXCHANGE_RATE = 1120;
```
const를 변수 선언 앞에 붙이면 상수가 된다. 선언 시에 const가 붙여진 변수는 일단 초기화된 후에 그 값이 변경될 수 없다. 이 문장은 변수 선언과 같이 세미콜론으로 끝남을 주의하라.

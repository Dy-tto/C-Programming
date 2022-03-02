C-Programming
=============
C- Programming 요약
------------------


```c
#include <stdio.h>

int main(){
  printf("Hello world!\n");
  return 0;
}
```
# 변수와 상수

```c
#include <stdio.h>
int main(){
  int a=10; // 4bytes
  short sh=10; // 2bytes
  long ln=10; // 4bytes
  long long lln=10; // 8bytes
  double db=3.141592; // 8bytes
  char ch='A'; // 1byte
  
  char name[20]="apple"; // 배열, 문자열 선언은 초기화만 가능, 문자열 끝에 \n 문자 붙음
  strcpy(name, "banana"); // 문자열 복사 후 데이터 변경
}
```
# 데이터 입력

```c
#define _CRT_SECURE_NO_WARNINGS // VS에서 오류 메세지 생길 때 넣어줌
#include <stdio.h>

int main(){
  int a;
  scanf("%d",&a); // a의 주소에 할당
  
}
```


# 연산자

```c

```

# 조건문

```c

```

# 반복문

```c

```

# 함수
```c

```

# 배열


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
* \+, \-, \*, /, %
```c
#include <stdio.h>

int main(void){
	int a, b;
	int sum, sub, mul, inv;

	a = 10;        
	b = 20;        
	sum = a + b;   
	sub = a - b;   
	mul = a * b;   
	inv = -a;      

	return 0;
}
```

* 비트 연산자
  + ~ : 부정
  + & : and
  + | : or
  + ^ : 배타적
  + << : 왼쪽 시프트

# 조건문

```c
#include <stdio.h>

int main(void){
	int a = 20;
	int b = 0;

	if (a > 10){                        
		b = a;                         
	}
	printf("a : %d, b : %d\n", a, b);  
	return 0;
}
```

```c
#include <stdio.h>

int main(void){
	int rank = 2, m = 0;

	switch (rank){
	case 1:            
		m = 300;       
		break;         
	case 2:            
		m = 200;       
		break;         
	case 3:          
		m = 100;       
		break;         
	default:         
		m = 10;        
		break;         
	}

	printf("m : %d\n", m);

	return 0;
}
```


# 반복문

```c
#include <stdio.h>
int main(){
  for(int i=0; i<10; i++){
    printf("%d\n",i);
  }
  return 0;
}
```

```c
#include <stdio.h>

int main(void){
	int a = 1;
	while (a < 10){
		a = a * 2;
	}
	printf("a : %d\n", a);

	return 0;
}
```


# 함수
```c
#include <stdio.h>

int add(int x, int y);   

int main(void){
	int a = 10, b = 20;
	int res;

	res = add(a, b);  
	printf("result : %d\n", res);

	return 0;
}                        

int add(int x, int y){
	int temp;            

	temp = x + y;        

	return temp;         
}                        
```

# 배열

```c
#include <stdio.h>

int main(void){
	int ary[5];                

	ary[0] = 10;               
	ary[1] = 20;               
	ary[2] = ary[0] + ary[1];  
	scanf("%d", &ary[3]);      

	printf("%d\n", ary[2]);    
	printf("%d\n", ary[3]);
	printf("%d\n", ary[4]);    

	return 0;
}
```

```c
#include <stdio.h>

int main(void){
	int ary1[5] = {1, 2, 3, 4, 5};               
	int ary2[5] = {1, 2, 3};                     
	int ary3[] = {1, 2, 3};                      
	double ary4[5] = {1.0, 2.1, 3.2, 4.3, 5.4};  
	char ary5[5] = {'a', 'p', 'p', 'l', 'e'};    

	ary1[0] = 10;
	ary1[1] = 20;
	ary1[2] = 30;
	ary1[3] = 40;
	ary1[4] = 50;

	return 0;
}
```

```c
#include <stdio.h>
#include <string.h>

int main(void){
	char str1[80] = "cat";
	char str2[80];

	strcpy(str1, "tiger");           
	strcpy(str2, str1);              
	printf("%s, %s\n", str1, str2);

	return 0;
}
```


```c
#include <stdio.h>

int main(void){
	char str[80];

	gets(str);                 
 
	puts(str);                 

	return 0;
}
```

```c
#include <stdio.h>

int main() {
    char arr[10];
    scanf("%s",arr);
    printf(arr);
    return 0;
}
```

# 포인터
```c
#include <stdio.h>

int main(void){
	int ary[3];
	int *pa = ary;
	int i;

	*pa = 10; // ary[0]=10;
	*(pa + 1) = 20; // ary[1]=20;
	pa[2] = pa[0] + pa[1]; // ary[3]=ary[0]+ary[1]

	for (i = 0; i < 3; i++){
		printf("%5d", pa[i]);
	}

	return 0;
}

```

```c
#include <stdio.h>

int main(void){
	int ary[3];
	int i;

	*(ary + 0) = 10;                // ary[0] = 10
	*(ary + 1) = *(ary + 0) + 10;   // ary[1] = ary[0] + 10

	scanf("%d", ary + 2);           // &ary[2]

	for (i = 0; i < 3; i++){
		printf("%5d", *(ary + i));  // ary[i]
	}

	return 0;
}
```
```c
#include <stdio.h>
int main(){
  int a=5;
  int *b=&a;
  int **c=&b;
  printf("%d\n",**c); // ptr b가 가리키는 값 반환
}
```
```c
#include <stdio.h>
int main(){
  int a[]={1,2,3,4,5,6,7};
  int *b=a; // b=&a[0]
  printf("%d\n", b[2]); // 배열의 이름은 주소이다.
}
```

```c
#include <stdio.h>
void swap1(int pa, int pb){
  int temp;
  temp=pa;
  pa=pb;
  pb=temp;
}
void swap2(int *pa, int *pb){
  int temp;
  temp=*pa;
  *pa=*pb;
  *pb=temp;
}

int main(){
  int a=10;
  int b=20;
  swap1(a,b); // 안 바뀜
  swap2(&a,&b); // 바뀜
}
```

# 문자열 포인터
* 문자열 상수는 주소이다.

```c
#include <stdio.h>
int main(){
  char str[80];
  
  scanf("%s",str); 
  // getchar() // getchar로 버퍼를 없애준다.
  scanf("%s",str); // 버퍼에 문자열이 남아 있으면 문자열을 새로 입력받지 않고 버퍼에 남아있는 문자열을 가져온다.
  
}
```

```c
#include <stdio.h>
int main(){
  char str[80];
  
  gets(str); // 공백 포함된 문자열 입력, 개행문자를 널문자로 바꿔서 저장한다.
  // fgets 함수는 개행문자까지 배열에 저장하고 널문자를 붙여서 문자열을 완성한다.
}
```

* strcpy 함수
  - 문자열의 첫 번째 문자부터 널 문자가 나올 때까지 문자를 하나씩 배열에 옮겨 저장한다.
```c
#include <stdio.h>
#include <string.h> // 문자열 관련 함수 사용 시 포함해야한다.

int main(){
  char str1[80]="strawberry";
  char str2[80]="apple";
  strcpy(str1,str2);

}
```

```c
// 문자열을 입력받고 문자열에 포함된 모든 공백을 삭제하는 함수
void del(char *f);

int main(){
  char wri[100];
  
  gets(wri);
  del(wri);
  return 0;
}
void del(char *f){
  int i,j;
  for i=0;f[i]!='\0';i++){
    if(f[i]==' '){
      for(j=1;f[j]!='\0';j++)
        f[j]=f[j+1];
      i--;
      
    }
  }
}
```

# 변수 사용 및 함수데이터
* 지역변수(local variable)
  - 메모리의 스택 영역에 기록
  - 블록 안에 사용 가능한 지역 변수가 둘 이상일 경우 가장 가까운 블록 안에 있는 변수 사용한다.
```c
#include <stdio.h>

void assign();
int main(){
  int a=0;
  assign();
  return 0;
}

void assign(){
  int a=10; // local variable
}
```

```c
#include <stdio.h>
int main(){
  int a=10, b=20;
  print("%d, %d\n",a,b);
  {
    int temp;
    temp=a;
    a=b;
    b=temp;
  }
  print("%d, %d\n",a,b); // 바로 위 블록이 가장 가까워서 값이 바뀐다.
}
```

* 전역 변수(global variable)
  - 프로그램의 어디서든 접근 가능한 변수
  - 전역 변수와 지역 변수의 이름이 같으면 지역 변수를 먼저 사용한다.
  - 전역 변수의 이름을 바꾸면 그 변수를 사용하는 모든 함수를 찾아 수정해야한다.
  - 전역 변수의 값이 잘못된 경우 접근 가능한 모든 함수를 의심해야한다.
  - 코드 블록 내에 이름의 지역변수를 선언하면 그 영역에서는 전역 변수를 사용할 수 없습니다.
  
```c
#include <stdio.h>

int a=0; // 전역 변수, 초기화 해줘야한다.
int main(){}
```

* 정적 지역 변수(static)
  - 특정한 블록에서만 접근할 수 있는 변수
  - 정적 변수는 데이터 영역에 저장된다.
  - 선언된 함수가 반환되더라도 그 저장 공간을 계속 유지한다.

```c
#include <stdio.h>

void a(){
  static int a=0; // 함수 실행 후에도 값 남아있다.
}
int main(){}
```

* 레지스터 변수(Register)
  - 메인 메모리 대신 CPU의 레지스터를 사용하는 변수
  - low level에서만 다룬다.

* 함수의 데이터 공유
```c
#include <stdio.h>

int *sum(int a, int b); // 반환 값이 주소

int main(){
  int *resp;
  resp=sum(10,20);
  return 0;
}
int *sum(int a, int b){
  static int res;
  res=a+b;
  return &res;
}
```

# 다차원 배열과 포인터 배열
* 2차원 배열은 1차원 배열이 중첩되었다는 의미로 대괄호를 두 번 연속하여 쓴다.
* 일부 초깃값을 생략하는 것도 가능
* 2차원 배열을 초기화 하면서 행의 수를 생략하고 선언할 수 있다.
* 1차원 배열을 초기화하는 방식처럼 할 수 있다.

```c
#include <stdio.h>

int main(){
	int score[3][4];
	
	for(int i=0;i<3;i++)
		for(int j=0;j<4;j++)
			scanf("%d",&score[i][j]);
	return 0;
}
```

```c
#include <stdio.h>

int main(){
	int score[2][3][4]={
		{{72,80,95,60},
		 {90,80,95,90},
		 {80,80,95,85}},
		{{80,97,88,85},
		 {72,78,55,77},
		 {72,80,95,60}}
	 };
	 
	 int i,j,k;
	 for(i=0;i<2;i++)
	 	for(j=0;j<3;j++)
			for(k=0;k<4;k++)
				printf("%d ", score[i][j][k]);
			printf("\n");
			
	return 0;
}
```

* 포인터 배열
  - 배열은 포인터와 동일한 방식으로 동작한다.
  - 배열의 이름은 배열의 원소의 첫 번째 주소가 된다.
  - 포인터는 변수이며 배열의 이름은 상수이다.
  - 데이터가  여기저기 흩어져 있더라도 그 주소만 따로 모아놓으면 데이터를 쉽게 처리할 수 있다.
  
```c
#include <stdio.h>

int main(){
	char *pray[3];
	int i;
	
	pary[0]="dog"; // pary[i] 각각이 배열로 취급된다.
	pary[1]="elphant";
	pary[2]="horse";
	
	for(i=0;i<3;i++)
		printf("%s\n",pary[i]);
}
```

# 여러가지 포인터
* 더블 포인터
  - 포인터도 메모리에 저장공간을 갖는 하나의 변수이다.
  - 주소 연산으로 포인터의 주소도 구할 수 있다.
  - 포인터의 주소를 저장한 이중 포인터에 간접 참조 연산을 수행하면 가리키는 대상인 포인터를 쓸 수 있다.
 
```c
#include <stdio.h>

int main(){
	int a=10;
	
	int *pi;
	int **ppi;
	
	pi=&a;
	ppi=&pi;
}
```

* 이중 포인터의 형태
  - 포인터가 가리키는 것의 형태와 포인터의 자신의 형태를 구분해야한다.
  - int형 변수의 주소를 저장하는 포인터는 가리키는 자료형이 int형이고 자신의 형태는 (int *)형이 된다.
  - 단일 포인터도 가리키는 자료형에 따라 다양하게 선언하듯이 이중포인터도 가리키는 포인터의 형태에 맞춰 선언해야한다.
 
* 응용 포인터
  - 포인터는 변수이므로 주소 연산자를 사용하여 그 주소를 구할 수 있습니다.
  - 상수인 주소에는 주소 연산자를 쓸 수 없다.
  
```c
// 이중 포인터를 사용한 포인터 교환
#include <stdio.h>

void swap_ptr(char **ppa, char **ppb){ // 포인터의 주소를 가리키는 이중 포인터
	char *pt;
	pt=*ppa;
	*ppa=*ppb;
	*ppb=pt;
}
int main(){
	char *pa="success";
	char *pb="failure";
	
	swap_ptr(&pa,&pb); // 포인터 자신의 주소를 넘겨 준다.
	return 0;
}
```
* 2차원 배열과 배열 포인터
  - 2차원 배열은 1차원 배열로 만든 배열이므로 논리적인 배열 요소가 1차원 배열이다.
  - 또한 배열명은 첫 번째 요소의 주소이므로 2차원 배열의 이름은 1차원 배열의 주소이며 배열을 가리키는 포인터에 저장된다.

```c
// 배열 포인터로 2차원 배열의 값 출력
#include <stdio.h>
int main(){
	int arr[3][4]={
		{1,2,3,4},
		{5,6,7,8},
		{9,10,11,12}
	   }
	int (*pa)[4];
	pa=arr;
	for (int i=0;,i<3;i++)
		for(int j=0;j<4;j++)
			printf("%d ",pa[i][j]);
		printf("\n");
	return 0;
}
```
* 함수 포인터
  - 함수 포인터를 사용하기 위해서는 함수명의 의미를 파악하는 것이 중요하다.
  - 함수명은 함수 정의가 있는 메모리의 시작 위치이다.
  - 함수명이 주소이므로 포인터에 저장하면 함수를 다양한 방식으로 호출 할 수 있다.

```c
#include <stdio.h>
int sum(int a, int b){
	return a+b;
}
int main(){
	int (*fp)(int, int);
	int res;
	
	fp=sum;
	res=fp(10,20);
	printf("result: %d\n", res);
	return 0;
}
```

```c
#include <stdio.h>

void func(int (*fp)(int, int)){
	int a,b;
	int res;
	scanf("%d %d",&a,&b);
	res=fp(a,b);
	printf("%d\n", res);
}
int sum(int a, int b);

int main(){
	func(sum);
	return 0;
}
```

# 동적할당



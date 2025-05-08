1. 알고리즘 자료구조란?
   - 자료구조 :  자료를 저장하기 위한 구조(공간), 대표적으로 배열이 있음
   - 알고리즘 : 자료구조 내부의 자료들을 효율적으로 정리하는 방법, 정렬 알고리즘 등이 있음
2. 시간 복잡도란?
   - 시간 복잡도 : 코드가 실행되는 시간을 예측하는 함수
     1) 코드 1줄 당 O(1)
     2) n번 반복 for문인 경우 O(n)
     3) n번, m번 반복 이중 포문인 경우 O(nm)
     4) 배열 크기가 n인 sort 함수 정렬인 경우 O(n log n)
3. 브루트포스 알고리즘이란? 
   - 브루트포스 알고리즘 : 모든 경우의 수를 전부 탐색하는 알고리즘
   - 가장 간단하고 쉽지만 효율이 좋지 않다는 단점이 있음
4. sort 함수 사용법 정리
   - \#include \<algorithm> 헤더 사용
   - 기본적으로 오름차순 정렬 수행
   - sort( 배열,배열 이름+크기)
   - compare() 함수를 사용하면 내림차순 정렬 등 다양한 정렬을 만들 수 있음
```C++
// 내림차순 정렬 예시
#include <iostream>
#include <algorithm>

using namespace std;

bool compare(int a, int b){
	return a > b; // >의 방향을 반대로 바꾸면 오름차순
}
int main(void){
	int arr[5]={2,4,6,1,3};
	sort(arr,arr+5,compare)
	for (int i=0; i<5;i++){
		cout << arr[i] << ' ';
	}
}
```

5. 새싹 문제 3개 풀고 시간 복잡도 계산
   - 10872 팩토리얼
![[Pasted image 20250404150753.png]]
```C++
#include <iostream>

using namespace std;

int main()
{
	long n;
	cin >> n;
	long res = 1;
	for (int i = 2;i <= n;i++) {
		res *= i;
	}
	cout << res;
}
// 시간 복잡도 : O(n)
```

   - 2752 세 수 정렬
![[Pasted image 20250404150915.png]]
```C++
#include <iostream>
#include <algorithm>

using namespace std;

int main()
{
	int arr[3];
	for (int i = 0;i < 3;i++) {
		cin >> arr[i];
	}
	sort(arr, arr + 3);
	for (int i = 0;i < 3;i++) {
		cout << arr[i] << ' ';
	}

}
// 시간 복잡도 O(3+3log3+3)=O(3log3+6)
```

   - 15964 이상한 기호
![[Pasted image 20250404145400.png]]
```C++
#include <iostream>

using namespace std;

long cal(long a, long b) { // O(1)
    long res = (a + b) * (a - b);
    return res;
}

int main()
{
    long num1, num2;
    cin >> num1;
    cin >> num2; // O(2)
    cout << cal(num1, num2); // O(1)
}
```

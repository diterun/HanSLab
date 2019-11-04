# Merge Sort
시간 복잡도|공간 복잡도
:-:|:-:
$O(nlogn)$|$2n$

 가장 즐겨쓰는 sort이다. 개인적 의견이지만 nlogn의 시간 복잡도를 가지는 여타 sort 알고리즘과 비교하여 가장 간단하고 직관적인 코드를 사용한다고 생각한다.  

 정렬하고 싶은 list의 처음과 끝을 분할하여 정복하는  
 **`분할 정복(Divide & Conquer)`** 알고리즘을 사용한다.

 다음은 C++ 예시코드이다.

<details>
<summary>c++</summary>
<div markdown="1">

```cpp
#include <iostream>
using namespace std;

#define MAX 10

void merge(){

}

void mergeSort(int left, int right){
    if(left > right){
        return;
    }

    int mid = (left + right) / 2;
}


```

</div>
</details>




# Merge Sort
시간 복잡도|공간 복잡도
:-:|:-:
$O(nlogn)$|$2n$

 가장 즐겨쓰는 sort이다. 개인적 의견이지만 nlogn의 시간 복잡도를 가지는 여타 sort 알고리즘과 비교하여 가장 간단하고 직관적인 코드를 사용한다고 생각한다.  

 정렬하고 싶은 list의 처음과 끝을 분할하여 정복하는  
 **`분할 정복(Divide & Conquer)`** 알고리즘을 사용한다.

 그림으로 설명되어 있는 것은 여러 블로그에 이미 많을 것이다. 그림 설명이 좋은 분은 다른 곳에서 보길 바란다. ~~사실은 내가 그리기 귀찮았다.~~ 다음의 예시코드는 매우 기니 아래쪽에서 설명을 봐도 좋다.
<details>
<summary>c++</summary>
<div markdown="1">

```cpp
#include <iostream>
using namespace std;

#define MAX 10

int numbers[MAX] = {36, 12, 4, 75, 34, 22, 1, 48, 89, 6};
int temp[MAX];

void merge(int left, int mid, int right){
    int l = left;
    int r = mid + 1;
    int t = left;

    while(l <= mid && r <= right){
        if(numbers[l] > numbers[r]){
            temp[t++] = numbers[r++];
        } else {
            temp[t++] = numbers[l++];
        }
    }

    for(;l <= mid; l++){
        temp[t++] = numbers[l];
    }
    for(;r <= right; r++){
        temp[t++] = numbers[r];
    }

    for(int i = left; i <= right; i++){
        numbers[i] = temp[i];
    }
}

void mergeSort(int left, int right){
    if(left >= right){
        return;
    }

    int mid = (left + right) / 2;

    mergeSort(left, mid);
    mergeSort(mid + 1, right);
    merge(left, mid, right);
}

int main(void){
    cout << "Not Sort : ";
    for(int i = 0; i < MAX; i++){
        cout << numbers[i] << " ";
    }
    cout << endl;

    mergeSort(0, MAX - 1);

    cout << "Sorted : ";
    for(int i = 0; i < MAX; i++){
        cout << numbers[i] << " ";
    }
    cout << endl;

    return 0;
}
```

</div>
</details>

먼저 분할하는 부분이다.
```cpp
void mergeSort(int left, int right){
    if(left >= right){
        return;
    }

    int mid = (left + right) / 2;

    mergeSort(left, mid);
    mergeSort(mid + 1, right);
    merge(left, mid, right);
}
```
 여기서 가장 중요한 점은



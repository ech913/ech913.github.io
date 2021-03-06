---
title: 단순 삽입 정렬
excerpt: Doit 자료구조와 알고리즘 입문_6장
category: Data_Structure
---

## 개념

배열의 정렬되지 않은 부분의 맨 앞 원소를 정렬된 부분에서 적절한 위치에 삽입하는 정렬 방법이다.

## 알고리즘 (파이썬)

~~~python
a = [6,4,3,7,1,9,8]  #입력 배열

n=len(a)

for i in range(1,n):    #배열의 두번째 원소부터 시작
    j=i
    tmp=a[i]    #정렬되지 않은 배열의 맨 앞 원소
    while j>0 and a[j-1]>tmp: 
        a[j] = a[j-1]   #배열 원소들을 한칸씩 뒤로 이동
        j-=1
    a[j]=tmp
~~~

1.
![삽입정렬1](/assets/images/pages/2022-01-11-insertion/insertion1.png)
2.
![삽입정렬2](/assets/images/pages/2022-01-11-insertion/insertion2.png)

## 장단점

- 장점 : 안정적인 정렬 방법이다.
- 단점 : 원소 수가 많아지면 (입력값이 많아지면) 원소끼리 비교와 교환 비용이 많이 든다.

## 시간복잡도

삽입정렬의 시간복잡도는 **O(n^2)**이다.

## 이진 삽입 정렬

삽입정렬은 원소 수가 많아지면 원소 비교와 교환 비용이 많아진다.  
이진 삽입 정렬은 단순 삽입정렬의 단점을 해결하기 위한 방법이다.  

아이디어.  
삽입해야 할 원소의 위치를 이진 검색을 사용하여 찾아낸다.  
단순 삽입정렬은 삽입 위치를 찾을 때 까지 원소들을 하나씩 뒤로 이동해야 하지만,  
이진 삽입 정렬은 원소가 들어가야 할 위치를 찾은 후 그 위치부터 정렬된 부분의 끝까지만 원소를 이동시키면 되기 때문에
비용면에서 절감이 있다.  

파이썬에서는 bisect 모듈의 insor() 함수로 이진 삽입정렬을 제공해준다.  
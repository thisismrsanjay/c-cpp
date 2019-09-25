## insertion sort
```cpp
#include<stdio.h>

void insertionSort(int arr[],int length){
  int key,i;
  

  for(int j=1;j<length;j++){

    //keeping  value in hand for comaprison
    key = arr[j];
    i=j-1;
    //shifting technique
    while(i>=0 && key<arr[i]){
      arr[i+1]=arr[i];
      i=i-1;
    }
    arr[i+1]=key;
  }
  
}


void printArray(int arr[],int length){
  for(int i=0;i<length;i++){
    printf("%d ",arr[i]);
  }
  printf("\n");
}

int main(){
  int arr[]= {9,6,5,2,1,3,4,7,8};
  int size_of_array = sizeof(arr)/sizeof(arr[0]);

  printf("before insertion sort:- ");
  printArray(arr,size_of_array);

  insertionSort(arr,size_of_array);

  printf("after insertion sort :- ");
  printArray(arr,size_of_array);
  return 0;
}
```

# Merge Sort
```cpp
#include<stdio.h>
#include<limits.h>

void printArray(int arr[],int length){
  for(int i=0;i<length;i++){
    printf("%d ",arr[i]);
  }
  printf("\n");
}

void merge(int *a,int left,int mid, int right){
  
  int n1= mid-left+1;
  int n2= right-mid;

  //array declaration
  int L[n1+1];
  int R[n2+1];
  
  //copying arrays
  for(int i=0;i<n1;i++)
    L[i]=a[left+i];
  for(int j=0;j<n2;j++)
    R[j]=a[mid+1+j];

  L[n1+1] = INT_MAX;
  R[n2+1] = INT_MAX;


  int i=0,j=0;
  for(int k=left;k<=right;k++){
    if(L[i]<=R[j]){
      a[k]=L[i];
      i++;
    }else{
      a[k]=R[j];
      j++;
    }
  }

  

}

void mergeSort(int *a,int left,int right){
  if(left<right){
    int mid = (left+right)/2;
    mergeSort(a, left,mid);
    mergeSort(a,mid+1,right);
    merge(a,left,mid,right);
  }
  

}

int main(){
  int a[] = {10,9,8,7,6,5,4,3,2,1};
  
  int length = sizeof(a)/sizeof(a[0]);
  

  printf("Before Merging:");
  printArray(a, length);
  mergeSort(a,0,length-1);
  printf("After Merging :");
  printArray(a,length);
  
  

  return 1;
}
```

# Quick Sort
```cpp
#include<stdio.h>


void printArray(int arr[],int length){
  for(int i=0;i<length;i++){
    printf("%d ",arr[i]);
  }
  printf("\n");
}
void swap(int *a,int i,int j){
  int temp = a[i];
  a[i]=a[j];
  a[j]=temp;
}

int partition(int *a,int left,int right){
  int pivot = a[right];
  int i = left-1;             //keep track of less than pivot

  for(int j=left;j<right;j++){
    if(a[j]<=pivot){
      i=i+1;
      swap(a,i,j);
    }
  }
  //swap pivot
  swap(a,i+1,right);
  return i+1;
}

void quickSort(int *a,int left,int right){
  if(left<right){
    int q = partition(a,left,right);
    quickSort(a,left,q-1);
    quickSort(a,q+1,right);
  }
}


int main(){
  int a[] = {13,19,9,5,12,8,7,4,21,2,6,11};
  
  int length = sizeof(a)/sizeof(a[0]);
  
  printf("Before  Sorting :");
  printArray(a,length);
  
  quickSort(a,0,length-1);

  printf("After   Sorting :");
  printArray(a,length);
  return 1;
}
```
#heap sort
```cpp
#include <stdio.h>

void swap(int *a,int i,int j){
  int temp = a[i];
  a[i]=a[j];
  a[j]=temp;
}
void printArray(int arr[],int length){
  for(int i=0;i<length;i++){
    printf("%d ",arr[i]);
  }
  printf("\n");
}
void max_heapify(int *a,int i,int length){
    int left = 2*i+1;
    int right= 2*i+2; 
    int largest;
    if(left<length && a[left]>a[i])
        largest=left;
    else largest=i;
    
    if(right<length && a[right]>a[largest])
        largest=right;
        
    if(largest!=i){
        swap(a,i,largest);
        max_heapify(a,largest,length);
    }
}
void build_max_heap(int *a,int length){
    
    for(int i=(length)/2-1;i>=0;i--){
        max_heapify(a,i,length); 
        printf("intermidiate   :");
        printArray(a,length);
    }
    
}
int heap_extract_max(int *a,int length){
    
    int max = a[0];
    a[0]=a[length-1];
    max_heapify(a,0,length);
    return max;
}
int main()
{
    int a[] ={4,9,6,5,0,8,2,1,3,7};
    int length = sizeof(a)/sizeof(a[0]);
    
    
    int i=0;
    printf("Before  Heapify:");
    printArray(a,length);
    
    build_max_heap(a,length);
    
    printf("After  Heapify :");
    printArray(a,length);
    
    printf("Sorting Heapify:");
    for(int i =0 ;i<length;i++){
        printf("%d ",heap_extract_max(a,length-i));
    }
    return 0;
}

```
//queue shift  static 
```cpp
#include <stdio.h>
#include <stdlib.h>


#define CAPACITY 5
int queue[CAPACITY];


int front =0,rear=0;

void insert(){
  if(CAPACITY== rear  ){
    printf("Queue is full\n");
  }else{
    int element;
    printf("Enter element :");
    scanf("%d",&element);
    queue[rear]=element;
    rear++;
  }

}
void del(){
  if(front==rear){
    printf("Queue is Empty\n");
  }else{
    printf("deleted item : %d ",queue[front]);
    for(int i=1;i<rear;i++){
      queue[i-1]=queue[i+1];
    }
    rear--;
  }
}
void traverse(){
  if(front==rear){
    printf("Queue is empty");
  }else{
    printf("Queue elements are:");
    for(int i= front;i<rear;i++){
      printf("%d->",queue[i]);
    }
  }
}

int main(){
  int choice;
  while(1){
    printf("\nEnter choce:\n1.insert\n2.delete\n3.traverse\n");
    scanf("%d",&choice);
    switch(choice){
      case 1:
        insert();
        break;
      case 2: 
        del();
        break;
      case 3:
        traverse();
        break;
      default: 
        exit(1);
    }
  }
  return 0;
}
```
//circular queue
```js
//incomplete stack implementation
#include <stdio.h>
#define CAPACITY 5 

void push(int );

int top=-1;
int stack[CAPACITY];//you cannot pass variable here

int main(){
  while(1){
      printf("1.Push \n");
      printf("5.Quit\n");

      int choice ;
      printf("Enter choice: ");
      scanf("%d",&choice);
      switch(choice){
        case 1:
          printf("Enter element to push ");
          int element;
          scanf("%d",&element);
          push(element);
          break;
        case 2:
          if(pop()==NULL){
            printf("stack underflow");
          }else{
            
          }
        default:
          printf("Wrong choice");
      }

  }
 
  return 0;
}
int isFull(){
  if(top==CAPACITY-1){
    return 1;
  }else{
    return 0;
  }
}

//push 
void push( int element){
  if(isFull()){
    printf("Can't push stack overflow");
  }else{
    top++;
    stack[top]=element;
    printf("\n Element Inserted %d",element);
  }
}
//pop 
isEmpty(){
  
}
pop(){
  if(isEmpty()){
    printf("stack underflow\n");
  }
}
```
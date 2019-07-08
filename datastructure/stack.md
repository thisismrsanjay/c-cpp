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
      printf("2.Pop \n");
      printf("3.Traverse \n");
      printf("4.Peek\n");
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
            printf("stack underflow \n");
            break;
          }else{
            printf("Popped element from %d \n",top+1);
            break;
          }
        case 3:
            traverse();
            break;
        case 4:
            printf("Top element is %d \n",peek());
            break;
        case 5:
            exit(0);
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
    printf("\n Element Inserted %d \n",element);
  }
}
//pop 
isEmpty(){
  if(top==-1){
    return 1;
  }else{
    return 0;
  }
}
int pop(){
  int element;
  if(isEmpty()){
    return 0;
  }else{
    element = stack[top];
    top--;
  }
  return top;
}

//traverse 
void traverse(){
    if(isEmpty()){
        printf("No Elements in stack \n");
    }else{
        printf("elements are");
        for(int i=0;i<=top;i++){
            printf("->%d",stack[i]);
        }
        printf("\n");
    }
}
//Peeek
int peek(){
    if(isEmpty()){
        return 0 ;
    }else{
        return stack[top];
    }
}
```
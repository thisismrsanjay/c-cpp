//linked list awesome program
```cpp
#include<stdio.h>
#include<stdlib.h>

struct node{
  int data;
  struct node * link;
};

struct node * root=NULL;


void insert(){
  //creating a node 
  struct node * temp;
  temp = (struct node *) malloc(sizeof(struct node));

  printf("Enter data to insert: ");
  scanf("%d",&temp->data);
  //important?
  temp->link= NULL;

  if(root == NULL){
    root = temp;
  }else{
    //connect the right link first
    //insert set root -temp temp->link =root
    temp->link = root;
    root = temp;
  }
}


void append (){
  struct node * temp;
  temp = (struct node *) malloc(sizeof(int));
  printf("Enter data to append:");
  scanf("%d",&temp->data);
  temp->link=NULL;

  if(root==NULL){
    root = temp;
  }else{
    //go to end 
    struct node * p;
    p=root;
    while(p->link != NULL){
      p=p->link;
    }
    p->link = temp;
  }
}

int length(){
  int length = 0;
  struct node * i;

  i= root;// i don't want to disturb root

 
    while(i !=NULL){
      i=i->link;
      length++;
    }
    return length;
  

}

void display(){
  struct node *p;
  p= root ;
  if(p==NULL){
    printf("LIST IS EMPTY\n");
  }else{
      while(p!=NULL){
      printf("%d-->",p->data);
      p=p->link;
    }
    printf("\n\n");
  }
  
}
void addAfter(){

  //location 
  int location;
  printf("Enter location : ");
  scanf("%d",&location);

  if(location > length()){
    printf("there is no between: ");
  }else{
    struct node * temp;
    int val;
    temp = (struct node *) malloc(sizeof(struct node ));
    printf("Enter value to be inserted");
    scanf("%d",&val);
    temp->data = val;
    temp->link = NULL;

    

    //interator 
    struct node * p ;
    p=root;
  
    for(int i=1;i<location;i++){
      p=p->link;
    }
    
    temp->link = p->link;
    p->link = temp;
    
  }
  
}


void del(){

  struct node * temp,* nextTemp;
  int location;
  printf("enter location : ");
  scanf("%d",&location);

  if(location > length()){
    printf("Invalid location ");
  }else if(location ==1 ){
    temp = root;
    root = temp->link;
    temp->link =NULL;
    free(temp);
  }else{
    temp = root;
    for( int i=1;i<location-1;i++){
      temp = temp->link;
    }

    nextTemp = temp->link;
    temp->link = nextTemp->link;

    nextTemp->link= NULL;
    free(nextTemp);

  }


}

int main(){
  printf("Single Linked List\n");

  while(1){
    printf("1.Append\n");
    printf("2.Insert\n");
    printf("3.Add After\n");
    printf("4.Length\n");
    printf("5.Show All\n");
    printf("6.Delete Node\n");
    printf("7.Quit\n");

    int choice;
    printf("Enter your choice:");
    scanf("%d",&choice);
    switch(choice){
      case 1:
        append();
        break;
      case 2:
        insert();
        break;
      case 3:
        addAfter();
        break;
      case 4:
        printf("%d\n",length());
        break;
      case 5:
        display();
        break;
      case 6:
        del();
        break;
      case 7:
        exit(1);
      default:
        printf("Invalid case");
    }
  }





  return 0;
}
```
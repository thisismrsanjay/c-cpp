# Tree

## Traversing algorithm



IN-ORDER (L-Root-R)
```c
#include <stdio.h>

struct node{
    int data;
    struct node *left,*right;
}
void Inorder(struct node* t){
    //altering the order of root process results different ordering
    if(t){
        Inorder(t->left);               // left child 
        printf("%d",t->data);           // Given Pointer print
        Inorder(t->right);              // Right child
    }
}

int main()
{
    printf("Hello World");

    return 0;
}

```

BINARY SEARCH TREE
```c
#include <stdio.h>
#include <stdio.h>

struct node{
    int data;
    struct node *left,*right;
};

struct node *root=NULL;

void insert( int d){
    //temp is used to hold current value
    
    struct node *temp,*parent;
    temp=(struct node *)malloc(sizeof (struct node));
    
    temp->data= d;
    temp->left=NULL;
    temp->right=NULL;
    
    
    if(root==NULL){
        root=temp;
    }else{
        
        struct node *current;
        parent=root;    //initially root is parent
        current =root;  //current is to keep track of current node
    
        while(current){
            //parent is used to set parent of current node
            parent = current;
            if(temp->data>current->data){
                current=current->right;
            }else{
                current=current->left;
            }
        }
        //parent is set by now
        if(temp->data>parent->data){
            parent->right= temp;
        }else{
            parent->left= temp;
        }
    }
    
}

void Inorder(struct node *t){
    //altering the order of root process results different ordering
    if(t){
        Inorder(t->left);               // left child 
        printf("%d->",t->data);           // Given Pointer print
        Inorder(t->right);              // Right child
    }
}

int main()
{
    insert(20);
    insert(50);
    insert(39);
    insert(60);
    Inorder(root);  //20->39->50->60
    return 0;
}
```

## BST 
* Given PreOrder We can find Post Order and vice versa As we know in order is sorted elements   
* Also PreOrder The left most element is root  
* Post Order the right most element is root
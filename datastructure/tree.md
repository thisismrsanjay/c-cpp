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

## BST 
* Given PreOrder We can find Post Order and vice versa As we know in order is sorted elements   
* Also PreOrder The left most element is root  
* Post Order the right most element is root
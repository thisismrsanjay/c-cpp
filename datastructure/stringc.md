```cpp
//concat 
#include <stdio.h>

char * strcatf(char * ,char *);

int main()
{
  char   c[]= "dante";
  char * t  = "nero";
  
  strcatf(c,t);
 
  
  printf("%s",c);  
  return 0;
}

 char * strcatf(char * c,char  * t){
  
  printf("%c\n",c[0]);
  printf("%c\n",*t);

  int i=0,j=0;
  
  while(*c!='\0')
    c++;

  //printf("%d\n",i);

  while(*t!='\0'){
    *c=*t;
    c++;
    t++;
  }
  printf("%d\n",j);
    
  
  return c;
}
```

//string compare
```cpp
int strsan(char c[],char t[]){
  
  while(*c==*t){
    c++;
    t++;
    if(*c=='\0')return 0;
  }

  return *c-*t;
}
```
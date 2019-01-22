```cpp
//strong
#include <iostream>
using namespace std ;
int main(){
  int number;
  cin>>number;

  int i =number,j=0,sum=0;
  while(i>0){
    j=i%10;
    i/=10;
    int fact=1;
    while(j>1){
      fact *= j;
      j--;
    }
    sum+=fact;
  }
  if(sum==number) 
    cout<<"strong nubmer";
  else
    cout<<"no no no ";
  
  return 0;
}

```
//armstrong number

```cpp
#include <iostream>
using namespace std ;
int main(){
  
  int number ;
  cin>> number;

  int n=0;
  int store = number;
  while(store>0){
    store /=10;
    n++;
  }
  cout<<"no of terms:"<<n<<"\n";

  store = number;

  int  sum =0;
   int multiplier;
  while(store >0){
    int r = store%10;
    store/= 10;


    multiplier = 1;
    for(int i=0;i<n;i++)
      multiplier  *= r;
    

    sum+= multiplier;
  }
 cout<<sum;

  if(sum==number) cout<<"\narmstrong";
  else cout<<"\nnot armstrong";
  return 0;
}
```
// factors of number using recursion
```cpp
#include <iostream>
using namespace std ;

int isPrime(int val){
  for(int i=2;i<val;i++){
    if(val%i==0) return 0;
  }
  return 1;
}

void factors(int value){
  int store = value;
  while (value>0){
    for(int i=2;i<value;i++){
      if(store%i==0){
        store = store/i;
        if(isPrime(i)){
          cout<<"factor:"<<i<<"\n";
        }else{
          factors(i);
        }
        
      }
    }
    

    value--;
  }
}
int main(){

  int value ;
  cin>>value;

  factors(value);
  return 0;
}
```
//prime factors of number 
```cpp
#include <iostream>
using namespace std ;

int isPrime(int val){
  for(int i=2;i<val;i++){
    if(val%i==0) return 0;
  }
  return 1;
}

int main(){

  int value ;
  cin>>value;

  for(int i=2;i<=value;i++){
    if(value%i==0){
      if(isPrime(i)){
        cout<<i<<": is the prime factor of "<<value<<"\n";
      }
    }
  } 
  return 0;
}
```
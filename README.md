#include<stdio.h>
int sum(int *num){
   int total=0,digit,temp=*num;
   while(temp>0){
    digit=temp%10;
    total+=digit*digit;
    temp/=10;
   }
   return total;
}
int happy(int *num){
   int one,two;
   one =two= *num;
   do{
     one=sum(&one);
     two=sum(&two);
     two=sum(&two);
   }while(one != two);
   return(one==1);
}
int main(){
   int num;
   printf("Enter the value of num : ");
   scanf("%d",&num);
   if(happy(&num))
      printf("\nHappy Number");
   else
      printf("\nNot");
   return 0;
}

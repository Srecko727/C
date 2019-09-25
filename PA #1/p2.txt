#include <stdio.h>
#include <stdlib.h>
int adder(int howMany,int add1,int add2) //adder is before main so it gets compiled first 
{
    if (howMany == 1)//if the input is only 1
    {
        return add1;//returns the first number, no recursion 
    }
    if (howMany == 2)//if the input is 2
    {
        return add2;//returns the second input, no recursion
    }
    else //recursion happens if the howMany is greater then 2
    {
        return adder(howMany-1,add1,add2) + adder(howMany-2,add1,add2);//the recursion that does the work of the program
    }   
}
int main()
{
int add1,add2,howMany; //initializing the inputs
scanf("%d", &add1);    //taking the first input in
scanf("%d", &add2);    //taking the second input in
scanf("%d", &howMany); //decides how many times the recursion happens. howMany - 2
printf("%d\n",adder(howMany,add1,add2)); //does the adder method then prints the result
return 0;
}
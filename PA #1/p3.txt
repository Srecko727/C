#include <stdio.h>
int main()
{       //amountOfSacredNumbers is initialized to 0 to start keeping traack of how many scared numbers we have to start with
    int amountOfSacredNumbers = 0,howManyNumbers,inputs,isItSacred,sumOfInput;//initializing all inputs
    scanf("%d",&howManyNumbers);//inputs the amount of numbers we will be using
    for(int i=0;i<howManyNumbers;i++)//loops through for the amount of numbers given
    {           //< is used over <= because it can only be done that many number of times no more
        scanf("%d",&inputs);//scans in the number to test if its Sacred
        
        isItSacred = inputs;//creates a temp variable to test the divisibility later
        sumOfInput = 0;//variable for the sum of the digits
        while (inputs > 0)//this does the adding untill the number is 0
        {
            sumOfInput = sumOfInput + (inputs%10); //every loop it adds the remainder of the number divided by 10 to sumOfInput
            inputs = inputs / 10;//divides by 10 to make sure it loops correctly with the sumOfInput without wasting memory
        }
        if (sumOfInput%2 == 0 && isItSacred%7 == 0)//if its even and divisible by 7
        {
            ++amountOfSacredNumbers;//adds 1 to the counter.
        }   //++before because it increments before the expression is evaluated.
        else if (sumOfInput%2 != 0 && isItSacred%13 == 0)//it not being odd because of the first if statement and divisible by 13
        {
            ++amountOfSacredNumbers;//adds 1 to the counter.
        }   //++before because it increments before the expression is evaluated.
    }
    printf("%d\n",amountOfSacredNumbers);//prints the number of Sacred Numbers found within the problem.
    return 0;
}
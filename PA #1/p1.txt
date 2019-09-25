#include <stdio.h>
#include <stdlib.h>
//TODO1: extend it to 8 registers.
unsigned long long int r0,r1,r2,r3,r4,r5,r6,r7 = 0;

unsigned long long int read_register(unsigned int register_num){
    switch(register_num){
        case 0:
            return r0;
        case 1:
            return r1;
        case 2:
            return r2;
        case 3:
            return r3;
        case 4:
            return r4;
        case 5:
            return r5;
        case 6:
            return r6;
        case 7:
            return r7;
    }
    return r0; //default, should be used with care.
}
int write_register(unsigned int register_num, unsigned long long int value){
    switch(register_num){
        case 0:
            r0 = value;
            return 0;
        case 1:
            r1 = value;
            return 0;
        case 2:
            r2 = value;
            return 0;
        case 3:
            r3 = value;
            return 0;
        case 4:
            r4 = value;
            return 0;
        case 5:
            r5 = value;
            return 0;
        case 6:
            r6 = value;
            return 0;
        case 7:
            r7 = value;
            return 0;
        //TODO: extend it to 8 registers.
    }
    return -1;
}
int main(){
    //TODO: implement the logic to read input and respond appropriately.
    /*
    example use case:
    input line: 2 2 3 0
    assume you have put them in variables a, b, c, d
    a == 2 means ADD and hence b, c and d are register numbers
    unsigned int a = 2, b = 2, c = 3, d = 0;
    unsigned long long int value = read_value(c) + read_value(d);
    if (write_register(b, value) == -1){
        //if here it means error. It should not happen as the inputs are going to be as expected.
    }
    */
    r0 = r1 = r2 = r3 = r4 = r5 = r6 = r7 = 0;
    unsigned int a,b,c,d;
    for ( ;; )
    {
        scanf("%u",&a);
        switch (a)
        {
                case 0:
                    exit(0);
                    break;
                case 1:
                    printf("%llu %llu %llu %llu %llu %llu %llu %llu\n", r0, r1, r2,r3,r4, r5 ,r6 ,r7);
                    break;
                case 2:
                    scanf("%u %u %u",&b,&c,&d);
                    write_register(b,read_register(c)+read_register(d));
                    break;
                case 3:
                    scanf("%u %u %u",&b,&c,&d);
                    write_register(b,read_register(c)+d);
                    break;
                case 4:
                    scanf("%u %u %u",&b,&c,&d);
                    write_register(b,read_register(c)*read_register(d));
                    break;
                case 5:
                    scanf("%u %u %u",&b,&c,&d);
                    write_register(b,read_register(c)*d);
                    break;
                case 6:
                    scanf("%u %u %u",&b,&c,&d);
                    if (read_register(d) != 0)
                        write_register(b,read_register(c)/read_register(d));
                    break;
                case 7:
                    scanf("%u %u %u",&b,&c,&d);
                    if (d != 0)
                        write_register(b,read_register(c)/d);
                    break;
                case 8:
                    scanf("%u %u %u",&b,&c,&d);
                    if (read_register(d) != 0)
                        write_register(b,read_register(c)%read_register(d));
                    break;
                case 9:
                    scanf("%u %u %u",&b,&c,&d);
                    if (d != 0)
                        write_register(b,read_register(c)%d);
                    break;
        }
    }
    return 0;
}
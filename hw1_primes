//
//  main.c
//  primes
//
//  Created by Charan Srinivasan on 10/12/14.
//  Copyright (c) 2014 Charan Srinivasan. All rights reserved.
//

#include <stdio.h>

int prime [1000];
int count = 0;

void print_matrix()
{
        printf("\n Count %d", count);
        printf("\n");
        for (int col = 0; col <count; col++)
        {
            printf("%01d ", prime[col]);
        }
    

}

int main(){
    int a;

    printf("Enter value: ");
    scanf("%d",&a);
    printf("Value=%d",a);    //%f is used for floats instead of %d
    for(int x=2; x< a; x++)
    {
        int flag = 0;
        for (int i=2; i< x; i++)
        {
        
            if ((x%i)==0) flag =1;
        }
        if (flag ==0)
        {
            prime [count] = x;
            count++;
        }
    }
    print_matrix();
    
    return 0;
}

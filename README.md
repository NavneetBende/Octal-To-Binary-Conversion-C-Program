# Octal-To-Binary-Conversion-C-Program

Octal to Binary Conversion in C
 Here, on this page we will discuss octal to binary conversion in C. There are 2 approaches to converting an octal number into a binary number:

First, convert Octal to Decimal and then Decimal to Binary.
Write 3 digit binary number for all the digits of a number from left to right.
We will discuss the algorithm for both approaches.

Example: 
Octal : 12
Decimal : 10
Binary : 001010
Octal to binary conversion in C
While loop in C
Method 1:-
Accept octal number
Convert it into decimal Equivalent
Convert this decimal value into Binary
Make sure you have visited these two pages before moving ahead with the code –

Octal to Decimal conversion
Decimal to Binary Conversion
Method 1 Code in C
Run
// this program converts octal to binary
// by converting octal->decimal->binary
#include<stdio.h>
#include<math.h>

void convert(int octal)
{
    int i = 0, decimal = 0;
    
    //converting octal to decimal
    while (octal!=0)
    {
        int digit = octal % 10;
        decimal += digit * pow(8, i);

        octal /= 10;
        i++;
    }
    
    printf("Decimal Value: %d\n",decimal);
    
    long long binary = 0;
    int rem;
    i = 1;
    
    // converting decimal to binary here
    while(decimal!=0)
    {
        rem = decimal % 2;
        decimal /= 2;
        binary += rem * i;
        
        // moving to next position ex: units -> tens
        i *= 10;
    }
    
    printf("Binary Value: %d",binary);
}
 
int main()
{
    int octal;
    
    printf("Octal Value: "); 
    scanf("%d", &octal);
 
    convert(octal);
 
    return 0;
}
Output
Octal Value: 12
Decimal Value: 10
Binary Value: 1010
Related Pages
Decimal to Binary conversion

Decimal to Octal Conversion

Decimal to Hexadecimal Conversion

Permutations in which n people can occupy r seats in a classroom 

Octal to Binary conversion

Quadrants in which a given coordinate lies

Method 2
Each digit of an octal number can be converted into its binary Equivalent (see image)

Binary Representation for Octal digit:
0 => 000
1 => 001
2 => 010
3 => 011
4 => 100
5 => 101
6 => 110
7 => 111
Octal to Binary in C Program
Method 2 Code in C:
Run
include<stdio.h>
#define MAX 1000

void convert(char octalnum[]){
    int i = 0;
    
    printf("Equivalent Binary Number: ");
    while (octalnum[i])
    { 
       //use switch case for multiple condition
        switch (octalnum[i])
        {
          case '0':
               printf("000"); break;
          case '1':
               printf("001"); break;
          case '2':
               printf("010"); break;
          case '3':
               printf("011"); break;
          case '4':
               printf("100"); break;
          case '5':
               printf("101"); break;
          case '6':
               printf("110"); break;
          case '7':
               printf("111"); break;
         //for invalid case 
          default:
               printf("\n Invalid octal digit %c ", octalnum[i]);
               return;
        }
        i++;
    }
    return;
    
}
int main()
{
    char octalnum[MAX];

    printf("Insert an octal number: ");
    scanf("%[^\n]", octalnum);
    
    convert(octalnum);
    
}
Output
Insert an octal number: 347
Equivalent Binary Number: 011100111

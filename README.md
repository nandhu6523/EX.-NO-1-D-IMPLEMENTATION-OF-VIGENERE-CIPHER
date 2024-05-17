# EX.-NO-1-D-IMPLEMENTATION-OF-VIGENERE-CIPHER

## AIM:
  To implement the Vigenere Cipher substitution technique using C program.
  
## ALGORITHM:
  STEP-1: Arrange the alphabets in row and column of a 26*26 matrix.
  
  STEP-2: Circulate the alphabets in each row to position left such that the first letter is attached to last.
 
  STEP-3: Repeat this process for all 26 rows and construct the final key matrix.
  
  STEP-4: The keyword and the plain text is read from the user.
  
  STEP-5: The characters in the keyword are repeated sequentially so as to match with that of the plain text.
  
  STEP-6: Pick the first letter of the plain text and that of the keyword as the row  indices and column indices respectively.
  
  STEP-7: The junction character where these two meet forms the cipher character.
  
  STEP-8: Repeat the above steps to generate the entire cipher text.
  
## PROGRAM:
```
#include <stdio.h>
#include<conio.h>
#include <ctype.h>
#include <string.h>
void encipher();
void decipher();
int main()
{
int choice;
while(1)
{
printf("\n1. Encrypt Text");
printf("\n2. Decrypt Text");
printf("\n3. Exit");
printf("\n\nEnter Your Choice : ");
scanf("%d",&choice);
if(choice == 3)
exit(0);
else if(choice == 1)
encipher();
else if(choice == 2)
decipher();
else
printf("Please Enter Valid Option.");
}
}
void encipher()
{
unsigned int i,j;
char input[50],key[10];
printf("\n\nEnter Plain Text: ");
scanf("%s",input);
printf("\nEnter Key Value: ");
scanf("%s",key);
printf("\nResultant Cipher Text: ");
for(i=0,j=0;i<strlen(input);i++,j++)
{
if(j>=strlen(key))
{ j=0;
}
printf("%c",65+(((toupper(input[i])-65)+(toupper(key[j])-
65))%26));
}}
void decipher()
{
unsigned int i,j;
char input[50],key[10];
int value;
printf("\n\nEnter Cipher Text: ");
scanf("%s",input);
printf("\n\nEnter the key value: ");
scanf("%s",key);
for(i=0,j=0;i<strlen(input);i++,j++)
{
if(j>=strlen(key))
{ j=0; }
value = (toupper(input[i])-64)-(toupper(key[j])-64);
if( value < 0)
{ value = value * -1;
}
printf("%c",65 + (value % 26));
}
return 0;
}
```

## OUTPUT:
![Screenshot 2024-05-17 102933](https://github.com/nandhu6523/EX.-NO-1-D-IMPLEMENTATION-OF-VIGENERE-CIPHER/assets/123856724/78a34579-c559-4b2e-9758-d01dd6c02683)


## RESULT:
  Thus the Vigenere Cipher substitution technique had been implemented successfully.

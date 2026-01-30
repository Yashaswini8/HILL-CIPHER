# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
#include <stdio.h>
#include <string.h>

int main()
{
    int key[3][3], text[3], cipher[3];
    char plaintext[100];
    int i, j, k;

    printf("Enter the plaintext (3 letters): ");
    scanf("%s", plaintext);

    printf("Enter the 3x3 key matrix:\n");
    for(i = 0; i < 3; i++)
        for(j = 0; j < 3; j++)
            scanf("%d", &key[i][j]);

    // Convert plaintext to numbers
    for(i = 0; i < 3; i++)
        text[i] = plaintext[i] - 'A';

    // Matrix multiplication
    for(i = 0; i < 3; i++)
    {
        cipher[i] = 0;
        for(j = 0; j < 3; j++)
            cipher[i] += key[i][j] * text[j];

        cipher[i] = cipher[i] % 26;
    }

    printf("Cipher Text: ");
    for(i = 0; i < 3; i++)
        printf("%c", cipher[i] + 'A');

    return 0;
}

## OUTPUT
<img width="1687" height="771" alt="image" src="https://github.com/user-attachments/assets/f279e726-e508-471e-90f1-71854c5e158c" />

## RESULT
Thus, the C program to implement the Hill Cipher encryption technique was successfully written, compiled, and executed.

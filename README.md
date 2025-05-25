# Ex-5 Rail-Fence-Program
## Name: LISIANA T
## Reg no: 212222240053

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:
To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

1.Write the plaintext downwards and diagonally across multiple "rails" of an imaginary fence.

2.Once the bottom rail is reached, move upwards diagonally until the top rail is reached.

3.Continue writing the message in this zigzag pattern until the entire plaintext is written out.

4.After completing the message, read it off row by row, starting from the top rail.

5.The result from reading the rows forms the encrypted ciphertext.

6.To decrypt, reverse the process by reconstructing the rails and placing the characters back in the zigzag pattern.


# PROGRAM
```
#include <stdio.h> 
#include <string.h> 
int main() 
{
    int i, j, k, l;
    char a[20], c[20], d[20];
    printf("\n\t\tRAIL FENCE TECHNIQUE\n");
    printf("\nEnter the input string: ");
    fgets(a, sizeof(a), stdin);
    a[strcspn(a, "\n")] = '\0';
    l = strlen(a); 
    for (i = 0, j = 0; i < l; i++) 
    {
       if (i % 2 == 0) 
        {
            c[j++] = a[i];
            
        }
        
    }
    for (i = 0; i < l; i++) 
    { 
        if (i % 2 == 1) 
        {
            c[j++] = a[i];
            
        }
        
    }
    c[j] = '\0'; 
    printf("\nCipher text after applying rail fence: %s\n", c);
    if (l % 2 == 0) 
    {
        k = l / 2;
        
    }
    else 
    {
        k = (l / 2) + 1;
        
    }
    for (i = 0, j = 0; i < k; i++) 
    {
        d[j] = c[i]; 
        j += 2;
        
    }
    for (i = k, j = 1; i < l; i++) 
    {
        d[j] = c[i]; 
        j += 2;
        
    }
    d[l] = '\0'; 
    printf("\nText after decryption: %s\n", d); 
    return 0; 
}
```
# OUTPUT
![image](https://github.com/user-attachments/assets/4ccbe005-4e4b-40d5-bbd3-5bbcd07dd16c)


# RESULT
The program is executed successfully.

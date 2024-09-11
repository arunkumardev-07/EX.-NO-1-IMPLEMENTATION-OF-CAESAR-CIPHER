# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char plain[100], cipher[100];
    int key, i, length;

    printf("\nEnter the plain text: ");
    scanf("%s", plain);

    printf("\nEnter the key value: ");
    scanf("%d", &key);

    length = strlen(plain);

    printf("\n\n\tPLAIN TEXT: %s", plain);

    printf("\n\n\tENCRYPTED TEXT: ");
    for (i = 0; i < length; i++) {
        // Encrypt each character
        cipher[i] = plain[i] + key;

        // Handle wrap-around for uppercase letters
        if (isupper(plain[i]) && (cipher[i] > 'Z')) {
            cipher[i] = cipher[i] - 26;
        }
        // Handle wrap-around for lowercase letters
        if (islower(plain[i]) && (cipher[i] > 'z')) {
            cipher[i] = cipher[i] - 26;
        }
        printf("%c", cipher[i]);
    }
    cipher[length] = '\0'; // Null-terminate the encrypted string

    printf("\n\n\tAFTER DECRYPTION: ");
    for (i = 0; i < length; i++) {
        // Decrypt each character
        plain[i] = cipher[i] - key;

        // Handle wrap-around for uppercase letters
        if (isupper(cipher[i]) && (plain[i] < 'A')) {
            plain[i] = plain[i] + 26;
        }
        // Handle wrap-around for lowercase letters
        if (islower(cipher[i]) && (plain[i] < 'a')) {
            plain[i] = plain[i] + 26;
        }
        printf("%c", plain[i]);
    }
    printf("\n");

return 0;
}


## OUTPUT:
![Screenshot 2024-09-11 093428](https://github.com/user-attachments/assets/eb65568a-e3a5-4951-867d-0a2cb3f98b31)



## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.

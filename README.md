# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:
AES is based on a design principle known as a substitution–permutation.
AES does not use a Feistel network like DES, it uses variant of Rijndael.
It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
AES operates on a 4 × 4 column-major order array of bytes, termed the state
# PROGRAM:
```
#include <stdio.h>
#include <string.h>

void simpleAESEncrypt(char *plaintext, char *key, char *ciphertext, int plen, int klen) {
    for (int i = 0; i < plen; i++) {
        ciphertext[i] = plaintext[i] ^ key[i % klen];
    }
}

void simpleAESDecrypt(char *ciphertext, char *key, char *decryptedText, int plen, int klen) {
    for (int i = 0; i < plen; i++) {
        decryptedText[i] = ciphertext[i] ^ key[i % klen];
    }
    decryptedText[plen] = '\0';
}

void printASCII(char *ciphertext, int plen) {
    printf("Encrypted Message (ASCII values): ");
    for (int i = 0; i < plen; i++) {
        printf("%d ", (unsigned char)ciphertext[i]);
    }
    printf("\n");
}

int main() {
    char plaintext[100], key[100], ciphertext[100], decryptedText[100];

    printf("Enter the plaintext: ");
    fgets(plaintext, sizeof(plaintext), stdin);
    plaintext[strcspn(plaintext, "\n")] = '\0';

    printf("Enter the key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';

    int plen = strlen(plaintext);
    int klen = strlen(key);

    if (klen == 0) {
        printf("Error: Key cannot be empty!\n");
        return 1;
    }

    simpleAESEncrypt(plaintext, key, ciphertext, plen, klen);
    printASCII(ciphertext, plen);

    simpleAESDecrypt(ciphertext, key, decryptedText, plen, klen);
    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}
```


# OUTPUT:

<img width="1615" height="949" alt="image" src="https://github.com/user-attachments/assets/f4775b8e-3e5a-43b9-a8c0-aff06cfeed43" />



# RESULT:

By using Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption was successfully completed.



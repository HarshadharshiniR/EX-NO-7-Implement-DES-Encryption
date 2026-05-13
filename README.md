# EX-NO-7-Implement-DES-Encryption


## Program:


```
#include <stdio.h>
#include <string.h>

void encrypt(char *message, char *key, char *encryptedMessage, int messageLength) {
    int keyLength = strlen(key);
    for (int i = 0; i < messageLength; i++) {
        encryptedMessage[i] = message[i] ^ key[i % keyLength];
    }
    encryptedMessage[messageLength] = '\0';
}

void decrypt(char *encryptedMessage, char *key, char *decryptedMessage, int messageLength) {
    int keyLength = strlen(key);
    for (int i = 0; i < messageLength; i++) {
        decryptedMessage[i] = encryptedMessage[i] ^ key[i % keyLength];
    }
    decryptedMessage[messageLength] = '\0';
}

int main() {
    char message[100];
    char key[100];

    printf("Simulation of DES encryption and decryption\n");

    printf("Enter the message to encrypt: ");
    fgets(message, sizeof(message), stdin);
    message[strcspn(message, "\n")] = '\0';

    printf("Enter the encryption key: ");
    fgets(key, sizeof(key), stdin);
    key[strcspn(key, "\n")] = '\0';

    int messageLength = strlen(message);

    char encryptedMessage[100];
    char decryptedMessage[100];

    encrypt(message, key, encryptedMessage, messageLength);

    printf("\nOriginal Message: %s\n", message);
    printf("Encrypted Message (Hex): ");
    for (int i = 0; i < messageLength; i++) {
        printf("%02X ", (unsigned char)encryptedMessage[i]);
    }
    printf("\n");

    decrypt(encryptedMessage, key, decryptedMessage, messageLength);

    printf("Decrypted Message: %s\n", decryptedMessage);

    return 0;
}
```

## Output:

<img width="1919" height="1007" alt="image" src="https://github.com/user-attachments/assets/9d5a8bb0-bc94-4ace-80ff-fb64e3f71195" />



## RESULT
  The program is executed successfully


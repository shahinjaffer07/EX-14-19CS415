# EX-NO14-HASH-ALGORITHM

## AIM:
To implement HASH ALGORITHM

## ALGORITHM:

1. Hash Algorithm is used to convert input data (message) into a fixed-size string, typically a hash value, which uniquely represents the original data.

2. Initialization:
   - Choose a hash function \( H \) (e.g., SHA-256, MD5, etc.).
   - The message \( M \) to be hashed is input.

3. Message Preprocessing:
   - Break the message \( M \) into fixed-size blocks. If necessary, pad the message to make it compatible with the block size required by the hash function.
   - For example, in SHA-256, the message is padded to ensure that its length is a multiple of 512 bits.

4. Hash Calculation:
   - Process the message block by block, applying the hash function \( H \) iteratively to produce an intermediate hash value.
   - For SHA-256, each block is processed through a series of logical operations, bitwise manipulations, and modular additions.

5. Output:
   - After all blocks are processed, the final hash value (digest) is produced, which is a fixed-size output (e.g., 256-bit for SHA-256).
   - The resulting hash is unique to the input message, meaning even a small change in the message will result in a completely different hash.

6. Security: The strength of the hash algorithm lies in its collision resistance, ensuring that it is computationally infeasible to find two different messages that produce the same hash value.


## Program:

```
#include <stdio.h>
#include <string.h>

void caesar(char *in, int s, char *out, int enc){
    for(int i=0; in[i]; i++){
        char c=in[i];
        if(c>='A' && c<='Z') out[i]=(c-'A'+ (enc?s:26-s))%26+'A';
        else if(c>='a' && c<='z') out[i]=(c-'a'+ (enc?s:26-s))%26+'a';
        else out[i]=c;
    }
    out[strlen(in)] = '\0';
}

int main(){
    char text[100], enc[100], dec[100];
    int shift;

    printf("Enter text: ");
    fgets(text,100,stdin);
    text[strcspn(text,"\n")] = 0;

    printf("Shift (1–25): ");
    scanf("%d",&shift);

    caesar(text,shift,enc,1);
    printf("Encrypted: %s\n", enc);

    caesar(enc,shift,dec,0);
    printf("Decrypted: %s\n", dec);

    return 0;
}

```

## Output:

<img width="670" height="408" alt="Screenshot 2025-11-18 205616" src="https://github.com/user-attachments/assets/a2c2a0ff-6408-49e6-958c-76ba44641134" />

## Result:
The program is executed successfully.

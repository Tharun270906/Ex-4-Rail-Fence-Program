# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[1000];
    int rails, len;

    printf("Enter message: ");
    scanf(" %[^\n]", str);

    printf("Enter rails: ");
    scanf("%d", &rails);

    len = strlen(str);

    for (int r = 0; r < rails; r++) {
        int i = r, down = 1;

        while (i < len) {
            printf("%c", str[i]);

            if (r == 0 || r == rails - 1)
                i += 2 * (rails - 1);
            else {
                if (down)
                    i += 2 * (rails - r - 1);
                else
                    i += 2 * r;
                down = !down;
            }
        }
    }

    return 0;
}
```

# OUTPUT
![alt text](<Screenshot 2026-05-06 111118 crypto-5.png>)

# RESULT

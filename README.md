#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *fp;
    char filename[30], ch;
    int words = 0, lines = 0, chars = 0;

    printf("Enter file name: ");
    scanf("%s", filename);

    fp = fopen(filename, "r");
    if (fp == NULL) {
        printf("Error! Cannot open file.\n");
        exit(0);
    }

    while ((ch = fgetc(fp)) != EOF) {
        chars++;

        if (ch == ' ' || ch == '\n' || ch == '\t')
            words++;

        if (ch == '\n')
            lines++;
    }
    fclose(fp);

    printf("\n--- File Statistics ---\n");
    printf("Characters: %d\n", chars);
    printf("Words     : %d\n", words);
    printf("Lines     : %d\n", lines);

    return 0;
}# Function-pointer
Function pointer calculator 

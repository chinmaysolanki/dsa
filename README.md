#include <stdio.h>

#define MAX_SIZE 100

void findCommonElements(int arr1[], int arr2[], int size1, int size2) {
    int i, j;
    printf("Common elements: ");
    for (i = 0; i < size1; i++) {
        for (j = 0; j < size2; j++) {
            if (arr1[i] == arr2[j]) {
                printf("%d ", arr1[i]);
                break; // Break inner loop if a common element is found
            }
        }
    }
    printf("\n");
}

int main() {
    int arr1[MAX_SIZE], arr2[MAX_SIZE];
    int size1, size2, i;

    printf("Enter the size of the first array: ");
    scanf("%d", &size1);

    printf("Enter elements of the first array: ");
    for (i = 0; i < size1; i++) {
        scanf("%d", &arr1[i]);
    }

    printf("Enter the size of the second array: ");
    scanf("%d", &size2);

    printf("Enter elements of the second array: ");
    for (i = 0; i < size2; i++) {
        scanf("%d", &arr2[i]);
    }

    findCommonElements(arr1, arr2, size1, size2);

    return 0;
}

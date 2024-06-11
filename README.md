#include <stdio.h>

#define MAX_SIZE 10

void print_spiral(int matrix[MAX_SIZE][MAX_SIZE], int rows, int cols) {
    int top = 0, bottom = rows - 1, left = 0, right = cols - 1;
    int i;

    while (top <= bottom && left <= right) {
        // Print top row
        for (i = left; i <= right; i++)
            printf("%d ", matrix[top][i]);
        top++;

        // Print rightmost column
        for (i = top; i <= bottom; i++)
            printf("%d ", matrix[i][right]);
        right--;

        // Print bottom row
        if (top <= bottom) {
            for (i = right; i >= left; i--)
                printf("%d ", matrix[bottom][i]);
            bottom--;
        }

        // Print leftmost column
        if (left <= right) {
            for (i = bottom; i >= top; i--)
                printf("%d ", matrix[i][left]);
            left++;
        }
    }
}

int spiral_sum(int matrix[MAX_SIZE][MAX_SIZE], int rows, int cols) {
    int top = 0, bottom = rows - 1, left = 0, right = cols - 1;
    int sum = 0;
    int i;

    while (top <= bottom && left <= right) {
        // Sum top row
        for (i = left; i <= right; i++)
            sum += matrix[top][i];
        top++;

        // Sum rightmost column
        for (i = top; i <= bottom; i++)
            sum += matrix[i][right];
        right--;

        // Sum bottom row
        if (top <= bottom) {
            for (i = right; i >= left; i--)
                sum += matrix[bottom][i];
            bottom--;
        }

        // Sum leftmost column
        if (left <= right) {
            for (i = bottom; i >= top; i--)
                sum += matrix[i][left];
            left++;
        }
    }

    return sum;
}

int main() {
    int matrix[MAX_SIZE][MAX_SIZE];
    int m, n, i, j;

    printf("Enter the number of rows: ");
    scanf("%d", &m);
    printf("Enter the number of columns: ");
    scanf("%d", &n);

    printf("Enter the elements of the matrix row-wise:\n");
    for (i = 0; i < m; i++) {
        for (j = 0; j < n; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }

    printf("Matrix elements in spiral form: ");
    print_spiral(matrix, m, n);
    printf("\n");

    printf("Sum of elements in spiral order: %d\n", spiral_sum(matrix, m, n));

    return 0;
}

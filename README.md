-#include <stdio.h>
// Function to swap two integers
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
// Function to perform bubble sort
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                swap(&arr[j], &arr[j+1]);
            }
        }
    }
}
int main() {
    int n;
    printf("Enter the number of integers: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter %d integers: \n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    // Sorting the array
    bubbleSort(arr, n);

    printf("Sorted Array: ");
    for(int i = 0; i < n; i++){
    printf("%d  ", arr[i]);
    }

    // Finding products of every two odd position elements
    printf("\nProducts of every two odd position elements: ");
    for (int i = 0; i < n; i += 2) {
        if (i + 1 < n - 1) {
            printf("%d ", arr[i] * arr[i + 2]);
        }
    }
    printf("\n");
    // Finding sum of every two even position elements
    printf("Sum of every two even position elements: ");
    for (int i = 1; i < n - 2 ; i += 2) {
        if (i + 1 < n) {
            printf("%d ", arr[i] + arr[i + 2]);
        }
    }
    printf("\n");

    return 0;
}

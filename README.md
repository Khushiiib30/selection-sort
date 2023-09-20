# selection-sort
#include <stdio.h>

void selectionSort(int arr[], int n) {
    int i, j, minIndex, temp;
    for (i = 0; i < n - 1; i++) {
        // Find the index of the minimum element in the unsorted part of the array
        minIndex = i;
        for (j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        
        // Swap the found minimum element with the first element in the unsorted part
        temp = arr[minIndex];
        arr[minIndex] = arr[i];
        arr[i] = temp;
    }
}

int main() {
    int n;
    
    printf("Enter the number of elements in the array: ");
    scanf("%d", &n);
    
    int arr[n]; // Declare an array of size n
    
    printf("Enter the elements of the array:\n");
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]); // Input each element of the array
    }

    // Call the selectionSort function to sort the array
    selectionSort(arr, n);

    printf("Sorted array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]); // Output the sorted array
    }

    return 0;
}

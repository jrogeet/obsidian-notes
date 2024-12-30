![[Pasted image 20221109202610.png]]
# Sorting
**Sorting** refers to arranging data in a particular format. Sorting algorithm specifies the way to arrange data in a particular order. Most common orders are in numerical and lexicographical order.

The important soring lies in the fact that data searching can be optimized to a very high level if data is stored in a sorted manner. Sorting is also used to present data in more readable formats. Following are some of the examples of sorting in real-life scenarios:

**Telephone Directory** – The telephone directory stores the telephone number of people sorted by their names, so that the names can be searched easily.

**Dictionary** – The dictionary stores words in alphabetical order so that searching for any word becomes easy.

**In-placing Sorting and Not-in-place Sorting**

Sorting algorithms may require some extra space for comparison and temporary storage of a few data elements. These algorithms do not require any extra space and sorting is said to happen in-place, or for example, with the array itself. This is called **in-place sorting**. Bubble sort is an example of in-place sorting.

However, In some sorting algorithms, the program requires space which is more than or equal to the elements being sorted. Sorting which uses equal or more space is called **not-in-place sorting**. Merge sort is an example of not-in-place sorting.

**Stable and Not Stable Sorting**

If a sorting algorithm, after sorting the contents, does not change the sequence of similar content in which they appear, it is called stable sorting.

![[Pasted image 20221110060949.png]]

If a sorting algorithm, after sorting the contents, changes the sequence of similar content in which they appear, it is called unstable sorting.

![[Pasted image 20221110061009.png]]

**Adaptive and Non-Adaptive Sorting Algorithm**

A sorting algorithm is said to be adaptive. If it takes advantage of already ‘sorted’ elements in the list that is to be sorted.  This is while sorting if the source list has some element already sorted, adaptive algorithms will take this into account and will try not to re-order them.

A non-adaptive algorithm is one which does not take into account the elements which are already sorted. They try to force every single element to be re-ordered to confirm their sortedness.

**Increasing Order**

A sequence of values is said to be in increasing order if the successive element is greater than the previous one. For example 1, 3, 4, 6, 8, 9 are in increasing order, as every next element is greater than the previous element.

**Decreasing Order**

A sequence of value is said to be in decreasing order if the successive element is less than the current one. For example, 9, 8, 6, 4, 3, 1 are in decreasing order, as every next element is less than the previous element.

**Non-Increasing Order**

A sequence of values is said to be in non-increasing order if the successive element is less than or equal to its previous element in the sequence. This order occurs when the sequence contains duplicate values. For example, 9, 8, 6, 3, 3, 1 are in non-increasing order, as every next element is less than or equal to(in case of 3) but not greater than any previous element.

**Non-Decreasing Order**

A sequence of values is said to be in non-decreasing order if the successive element is greater than or equal to its previous element in the sequence. This order occurs when the sequence contains duplicate values. For example, 1, 3, 3, 6, 8, 9 are in non-decreasing order, as every next element is greater than or equal to (in case of 3) but not less than the previous one.

# Bubble Sort

**Bubble sort** may be defined as the sorting algorithm that follows the approach of replacing the value in the first index with the smallest value in the array and keep it repeating until the list is sorted. It is a very simple way of performing sorting. In this way to sort the array, the value has to be assigned to the array in the beginning before starting the sorting.

The first smallest value found in the array has been moved to the first index of the array and then the search begins again to find the other smallest number. Once the next smallest number is found, it replaces the value in the second index and the process keeps on repeating until the array consists of a sorted list of values.

SAMPLE CODE:
![[Pasted image 20221110093856.png]]
![[Pasted image 20221110101313.png]]
```C++
// C++ program for implementation
// of Bubble sort
#include <bits/stdc++.h>
using namespace std;

// A function to implement bubble sort
void bubbleSort(int arr[], int n)
{
	int i, j;
	for (i = 0; i < n - 1; i++)

		// Last i elements are already
		// in place
		for (j = 0; j < n - i - 1; j++)
			if (arr[j] > arr[j + 1])
				swap(arr[j], arr[j + 1]);
}

// Function to print an array
void printArray(int arr[], int size)
{
	int i;
	for (i = 0; i < size; i++)
		cout << arr[i] << " ";
	cout << endl;
}

// Driver code
int main()
{
	int arr[] = { 5, 1, 4, 2, 8};
	int N = sizeof(arr) / sizeof(arr[0]);
	bubbleSort(arr, N);
	cout << "Sorted array: \n";
	printArray(arr, N);
	return 0;
}
// This code is contributed by rathbhupendra

```
# Insertion Sort

**Insertion sort** picks elements one by one and places it to the right position where it belongs in the sorted list of elements. A  simple sorting algorithm that works the way we sort playing cards in our hands.

![[Pasted image 20221110073428.png | 390]]
![[Pasted image 20221110101740.png]]
```C++
// C++ program for insertion sort

#include <bits/stdc++.h>
using namespace std;

// Function to sort an array using
// insertion sort
void insertionSort(int arr[], int n)
{
	int i, key, j;
	for (i = 1; i < n; i++)
	{
		key = arr[i];
		j = i - 1;

		// Move elements of arr[0..i-1],
		// that are greater than key, to one
		// position ahead of their
		// current position
		while (j >= 0 && arr[j] > key)
		{
			arr[j + 1] = arr[j];
			j = j - 1;
		}
		arr[j + 1] = key;
	}
}

// A utility function to print an array
// of size n
void printArray(int arr[], int n)
{
	int i;
	for (i = 0; i < n; i++)
		cout << arr[i] << " ";
	cout << endl;
}

// Driver code
int main()
{
	int arr[] = { 12, 11, 13, 5, 6 };
	int N = sizeof(arr) / sizeof(arr[0]);

	insertionSort(arr, N);
	printArray(arr, N);

	return 0;
}
// This is code is contributed by rathbhupendra

```
# Selection Sort

**Selection sort** may be defined as another algorithm for sorting the list in which the array is bifurcated into two arrays where the first array is supposed to be empty while the second array consists of the unsorted list of values. The program searches for the smallest values in the second array and when the value is found, it has been moved to the beginning of the first array that was empty. The approach is repeated again and the next smallest values will be shifted to the second index of the first array. The processes will keep on repeating until the second array became empty.

The processes will be repeated until the first list is full of the sorted list. Meanwhile, the programs keep its primary focus to check if the second array is having value and if it is found positive, the program runs the sorting algorithm again. Though it sorts the list in an easy manner, it may take a bit more time as compared to the other algorithms. But by the end, the result it will generate will be the same as the other sorting algorithms.
![[Pasted image 20221110101837.png]]
```C++
// C++ program for implementation of
// selection sort
#include <bits/stdc++.h>
using namespace std;

//Swap function
void swap(int *xp, int *yp)
{
	int temp = *xp;
	*xp = *yp;
	*yp = temp;
}

void selectionSort(int arr[], int n)
{
	int i, j, min_idx;

	// One by one move boundary of
	// unsorted subarray
	for (i = 0; i < n-1; i++)
	{
	
		// Find the minimum element in
		// unsorted array
		min_idx = i;
		for (j = i+1; j < n; j++)
		if (arr[j] < arr[min_idx])
			min_idx = j;

		// Swap the found minimum element
		// with the first element
		if(min_idx!=i)
			swap(&arr[min_idx], &arr[i]);
	}
}

//Function to print an array
void printArray(int arr[], int size)
{
	int i;
	for (i=0; i < size; i++)
		cout << arr[i] << " ";
	cout << endl;
}

// Driver program to test above functions
int main()
{
	int arr[] = {64, 25, 12, 22, 11};
	int n = sizeof(arr)/sizeof(arr[0]);
	selectionSort(arr, n);
	cout << "Sorted array: \n";
	printArray(arr, n);
	return 0;
}
// This is code is contributed by rathbhupendra

```
# Merge Sort

**Merge sort** may be defined as another sorting algorithm that performs the sorting by segregating the array till last when it turns into an individual value and then aggregating them in a manner so that it could turn into a sorted array.

The process consumes a bit much time as compared to the other rival algorithms but it is considered pretty efficient as compared to others. When it comes to sorting a large list, this algorithm works very fine and hence preferred in developing the application that has to process the large list


![[Pasted image 20221110073634.png]]
```C++
// C++ program for Merge Sort
#include <iostream>
using namespace std;

// Merges two subarrays of array[].
// First subarray is arr[begin..mid]
// Second subarray is arr[mid+1..end]
void merge(int array[], int const left, int const mid,
		int const right)
{
	auto const subArrayOne = mid - left + 1;
	auto const subArrayTwo = right - mid;

	// Create temp arrays
	auto *leftArray = new int[subArrayOne],
		*rightArray = new int[subArrayTwo];

	// Copy data to temp arrays leftArray[] and rightArray[]
	for (auto i = 0; i < subArrayOne; i++)
		leftArray[i] = array[left + i];
	for (auto j = 0; j < subArrayTwo; j++)
		rightArray[j] = array[mid + 1 + j];

	auto indexOfSubArrayOne
		= 0, // Initial index of first sub-array
		indexOfSubArrayTwo
		= 0; // Initial index of second sub-array
	int indexOfMergedArray
		= left; // Initial index of merged array

	// Merge the temp arrays back into array[left..right]
	while (indexOfSubArrayOne < subArrayOne
		&& indexOfSubArrayTwo < subArrayTwo) {
		if (leftArray[indexOfSubArrayOne]
			<= rightArray[indexOfSubArrayTwo]) {
			array[indexOfMergedArray]
				= leftArray[indexOfSubArrayOne];
			indexOfSubArrayOne++;
		}
		else {
			array[indexOfMergedArray]
				= rightArray[indexOfSubArrayTwo];
			indexOfSubArrayTwo++;
		}
		indexOfMergedArray++;
	}
	// Copy the remaining elements of
	// left[], if there are any
	while (indexOfSubArrayOne < subArrayOne) {
		array[indexOfMergedArray]
			= leftArray[indexOfSubArrayOne];
		indexOfSubArrayOne++;
		indexOfMergedArray++;
	}
	// Copy the remaining elements of
	// right[], if there are any
	while (indexOfSubArrayTwo < subArrayTwo) {
		array[indexOfMergedArray]
			= rightArray[indexOfSubArrayTwo];
		indexOfSubArrayTwo++;
		indexOfMergedArray++;
	}
	delete[] leftArray;
	delete[] rightArray;
}

// begin is for left index and end is
// right index of the sub-array
// of arr to be sorted */
void mergeSort(int array[], int const begin, int const end)
{
	if (begin >= end)
		return; // Returns recursively

	auto mid = begin + (end - begin) / 2;
	mergeSort(array, begin, mid);
	mergeSort(array, mid + 1, end);
	merge(array, begin, mid, end);
}

// UTILITY FUNCTIONS
// Function to print an array
void printArray(int A[], int size)
{
	for (auto i = 0; i < size; i++)
		cout << A[i] << " ";
}

// Driver code
int main()
{
	int arr[] = { 12, 11, 13, 5, 6, 7 };
	auto arr_size = sizeof(arr) / sizeof(arr[0]);

	cout << "Given array is \n";
	printArray(arr, arr_size);

	mergeSort(arr, 0, arr_size - 1);

	cout << "\nSorted array is \n";
	printArray(arr, arr_size);
	return 0;
}

// This code is contributed by Mayank Tyagi
// This code was revised by Joshua Estes

```

# Quick Sort

**Quick sort** can be defined as the other algorithm for sorting the list in which the approach is to divide the array in terms of greater than and less than values until the entire values if divided into individuals forms. In this algorithm, the value of the last index of the array has been selected as a pivot and all the values smaller than pivot has been shifted to the array that is expected to occur in the left of the value and the elements having a higher value than the pivot are shifted to the right array. Again one pivot is selected from the newly formed array that had the values less than the last pivot value. Similarly, the values smaller than the new pivot will be shifted to the array that will be left and the values more than the new pivot will be shifted in the right array.

 Quicksort is the only algorithm that leads to dividing the array until all the values are separated into the individual arrays. They will be then added or aggregated in a single array which is considered as the sorted list.

```C++
/* C++ implementation of QuickSort */
#include <bits/stdc++.h>
using namespace std;

// A utility function to swap two elements
void swap(int* a, int* b)
{
	int t = *a;
	*a = *b;
	*b = t;
}

/* This function takes last element as pivot, places
the pivot element at its correct position in sorted
array, and places all smaller (smaller than pivot)
to left of pivot and all greater elements to right
of pivot */
int partition(int arr[], int low, int high)
{
	int pivot = arr[high]; // pivot
	int i
		= (low
		- 1); // Index of smaller element and indicates
				// the right position of pivot found so far

	for (int j = low; j <= high - 1; j++) {
		// If current element is smaller than the pivot
		if (arr[j] < pivot) {
			i++; // increment index of smaller element
			swap(&arr[i], &arr[j]);
		}
	}
	swap(&arr[i + 1], &arr[high]);
	return (i + 1);
}

/* The main function that implements QuickSort
arr[] --> Array to be sorted,
low --> Starting index,
high --> Ending index */
void quickSort(int arr[], int low, int high)
{
	if (low < high) {
		/* pi is partitioning index, arr[p] is now
		at right place */
		int pi = partition(arr, low, high);

		// Separately sort elements before
		// partition and after partition
		quickSort(arr, low, pi - 1);
		quickSort(arr, pi + 1, high);
	}
}

/* Function to print an array */
void printArray(int arr[], int size)
{
	int i;
	for (i = 0; i < size; i++)
		cout << arr[i] << " ";
	cout << endl;
}

// Driver Code
int main()
{
	int arr[] = { 10, 7, 8, 9, 1, 5 };
	int n = sizeof(arr) / sizeof(arr[0]);
	quickSort(arr, 0, n - 1);
	cout << "Sorted array: \n";
	printArray(arr, n);
	return 0;
}

// This code is contributed by rathbhupendra

```
# Heap Sort

**Heap sort** can be defined as the sorting algorithm that works by searching the maximum element in the list and place it to the last. The algorithm performs the action recursively until the array gets sorted into the ascending way.

It is very time taking the process to choose the maximum value and move it to the last and hence it is considered as a less efficient sorting approach when it comes to sorting the large list. However, it works fine with the list that has a limited number of values.
```C++
// C++ program for implementation of Heap Sort

#include <iostream>
using namespace std;

// To heapify a subtree rooted with node i
// which is an index in arr[].
// n is size of heap
void heapify(int arr[], int N, int i)
{

	// Initialize largest as root
	int largest = i;

	// left = 2*i + 1
	int l = 2 * i + 1;

	// right = 2*i + 2
	int r = 2 * i + 2;

	// If left child is larger than root
	if (l < N && arr[l] > arr[largest])
		largest = l;

	// If right child is larger than largest
	// so far
	if (r < N && arr[r] > arr[largest])
		largest = r;

	// If largest is not root
	if (largest != i) {
		swap(arr[i], arr[largest]);

		// Recursively heapify the affected
		// sub-tree
		heapify(arr, N, largest);
	}
}

// Main function to do heap sort
void heapSort(int arr[], int N)
{

	// Build heap (rearrange array)
	for (int i = N / 2 - 1; i >= 0; i--)
		heapify(arr, N, i);

	// One by one extract an element
	// from heap
	for (int i = N - 1; i > 0; i--) {

		// Move current root to end
		swap(arr[0], arr[i]);

		// call max heapify on the reduced heap
		heapify(arr, i, 0);
	}
}

// A utility function to print array of size n
void printArray(int arr[], int N)
{
	for (int i = 0; i < N; ++i)
		cout << arr[i] << " ";
	cout << "\n";
}

// Driver's code
int main()
{
	int arr[] = { 12, 11, 13, 5, 6, 7 };
	int N = sizeof(arr) / sizeof(arr[0]);

	// Function call
	heapSort(arr, N);

	cout << "Sorted array is \n";
	printArray(arr, N);
}

```
# STACK ADT
It is an ordered group of homogeneous items of elements.

Elements are added to and removed from the top of the stack (the most recently added items are at the top of the stack).

The last element to be added is the first to be removed (LIFO: Last In, First Out).
![[Pasted image 20221110091212.png]]

## Applications of stack adt
**`Direct Applications`**

Balancing of symbols
Infix-to-postfix conversion
Evaluation of postfix conversion
Implementing function calls (including recursion)
Finding of spans (finding spans in stock markets)
Page-visited history in a Web browser (Back Buttons)
Undo sequence in a text editor
Matching tags in HTML and XML

**`Indirect Applications`**
Auxiliary data structure for other algorithms
Component of other data structures

## IMPLEMENTATION OF STACK ADT
These are the methods of implementing stack ADT:

**`Simple Array Implementation`**
It uses an array then add elements from left to right and use a variable to keep track of the index of the top element. A push operation will then throw a full stack exception and deleting an element from an empty stack it will throw stack empty exception.

**`Dynamic Array Implementation`**
Took one index variable top which points to the index of the most recently inserted element in the stack. To push an element, increment top index and then place the new element at that index. To pop an element, take the element at top index and then decrement the top index.

**`Linked List Implementation`**
Push operation is implemented by inserting element at the beginning of the list. Pop operation is implemented by deleting the node from the beginning.

# QUEUE ADT
It is an ordered group of homogeneous items of elements.

**`Queues`** have two ends:
	Elements are added at one end.
	Elements are removed from the other end.

The element added first is also removed first (FIFO: First In, First Out).

![[Pasted image 20221110091448.png]]

## APPLICATIONS OF QUEUE ADT
**`Direct Applications`**
Operating system schedule jobs in the order of arrival
Simulation of real-world queues
Multiprogramming
Asynchronous data transfer
Waiting times of customers at call center
Determining number of cashiers to have at supermarket

**`Indirect Applications`**
Auxiliary data structure for algorithms
Component of other data structures
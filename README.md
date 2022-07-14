# Sorting
## Introduction
* We have learned Bubble Sort, Insertion Sort (Binary Insertion Sort), Selection Sort
  - They all work at O(n^2) complexity level
* Are there faster sorting algorithms?
  - We may have heard there are O(nlogn) level algorithms, or even O(n) level ones
* We will learn some new sorting algorithms
  - Implement those algorithms based on an ADT Sortable: similar as list
  - We will focus on contiguous implementations
* Focus on array-based implementations
  - <img width="558" alt="Screen Shot 2022-07-14 at 5 33 04 PM" src="https://user-images.githubusercontent.com/89602311/179099523-9465dcb5-16c8-4f33-9e7f-afc8ae526319.png">
## Outline
* Comparison-based sorting
  - Mergesort
  - Quicksort
* Non-comparison sorting
  - Radixsort
## Mergesort
* Main idea
  - Divide the array into two sub-arrays of sizes as close as possible
  - Sort them seperately 
  - Merge the two sorted sub-arrays into a single sorted array
  - Pseudocode
  - <img width="486" alt="Screen Shot 2022-07-14 at 5 28 07 PM" src="https://user-images.githubusercontent.com/89602311/179098975-7f323eab-93cd-4996-9728-fd3533a04d2e.png">
* <img width="692" alt="Screen Shot 2022-07-14 at 5 28 58 PM" src="https://user-images.githubusercontent.com/89602311/179099073-996aeda2-165d-4f36-ac52-61ff6a990cf8.png">
* <img width="577" alt="Screen Shot 2022-07-14 at 5 29 21 PM" src="https://user-images.githubusercontent.com/89602311/179099114-c45e9996-614b-4f51-98a4-3e5cc9d950dd.png">
* <img width="676" alt="Screen Shot 2022-07-14 at 5 29 32 PM" src="https://user-images.githubusercontent.com/89602311/179099133-54bab69d-a93b-496d-aca2-ff7e7fa00471.png">
* Time complexity 
  - Recurrence relation 
  - <img width="265" alt="Screen Shot 2022-07-14 at 5 30 06 PM" src="https://user-images.githubusercontent.com/89602311/179099194-c0a2f389-dfb4-4890-b6b7-bcfe115e638e.png">
  - where theta(n) is the merge cost
  - Therefore, the running time is O(nlogn)
  - <img width="444" alt="Screen Shot 2022-07-14 at 5 30 47 PM" src="https://user-images.githubusercontent.com/89602311/179099262-385b16d7-2bc0-428a-9ab7-7af5f8ec3a7d.png">
## Quicksort
* Main idea
  - To partition the array, some key is first chosen from is
    - The key is called pivot
    - We hope that about half the keys will come before and half after the pivot
    - There could be different pivot strategies: we will choose the left center in this lecture
  - The array is then partitioned so that all those keys less than the pivot come in one sub-array, and all those with greater keys come in another
  - Finally, the two sub-arrays are sorted separately and put together, and the whole list will be in order
    - The same method is repeated in sorting the sub-arrays
* Pseudocode
  - <img width="753" alt="Screen Shot 2022-07-14 at 6 06 11 PM" src="https://user-images.githubusercontent.com/89602311/179115827-395337a5-0eb7-4491-be38-f2ce486633d3.png">
* How to efficiently perform the partition? 
  - <img width="655" alt="Screen Shot 2022-07-14 at 6 22 20 PM" src="https://user-images.githubusercontent.com/89602311/179117326-4b3618a5-a050-4216-9fab-c155f1897fa3.png">
* <img width="656" alt="Screen Shot 2022-07-14 at 6 22 34 PM" src="https://user-images.githubusercontent.com/89602311/179117351-bc1b28b4-c41a-486b-af65-82b512532f41.png">
* <img width="695" alt="Screen Shot 2022-07-14 at 6 22 51 PM" src="https://user-images.githubusercontent.com/89602311/179117374-78aff508-03b1-42cf-856c-d69b65abaf99.png">
* <img width="714" alt="Screen Shot 2022-07-14 at 6 23 06 PM" src="https://user-images.githubusercontent.com/89602311/179117402-e1637d37-048e-4b06-8752-4f4fdd98bb69.png">
* Time complexity
  - Average: O(nlogn) (needs complete mathematical proof: skip)
  - Worst: O(n^2) (when does this happen?)
  - Best: O(nlogn)
* Choice of Pivot
  - The first entry is often a poor choice for pivot
    - If the list is already sorted, then the first key will have no others less than it
  - The function partition choose a pivot near the center of the list
    - Hope that the choice will partition the kets so that about half come on each side of the pivot
    - Not always good
      - 2 4 6 7 5 3 1 (Downgraded to insertion sort, and thus O(n^2))
## Radixsort

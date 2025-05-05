# Rishikesh_AP_MultiThreading

1. Multi-threaded Merge Sort

Objective:
Implement merge sort in multi-threaded fashion. Divide the array into two halves and sort them concurrently in separate threads, then merge the results. Finally, compare its runtime with a standard single-threaded merge sort.

Approach:
-Divide and Conquer:
    - The merge sort algorithm works by recursively splitting the array until subarrays of size one (or zero) remain and then merging them back in sorted order.
- Introducing Threads:
    - When you split the list into two halves, create two threads:
        - One for sorting the left half.
        - One for sorting the right half.
        - Both threads run concurrently.
        - Once both threads complete their sorted subarrays, use a merging function to merge the sorted halves.
=> Thread Management:
- Use Python's built-in threading module.
- Create a thread for each half, start them, and then use the join() method to wait until they finish

---------------------------------------------------------------------------------------------------------------------------------------------------------

2. Multi-threaded Quicksort

Objective:
Implement a multi-threaded quicksort algorithm that concurrently sorts subarrays. Keep control over the number of threads so you don’t spawn too many.

Approach:
=> Quicksort Overview:
- Choose a pivot and partition the array into two subarrays—elements less than the pivot and elements greater than or equal to the pivot.
- Recursively sort the subarrays.
=> Applying Threads:
- After partitioning, create threads to sort each subarray concurrently.
- To avoid thread explosion, you can:
    - Set a threshold for small subarrays to be sorted sequentially.
    - Use a global thread counter or a threading semaphore to limit maximum concurrent threads.
    - Alternatively, consider using ThreadPoolExecutor (from the concurrent.futures module) for easier pool management.

---------------------------------------------------------------------------------------------------------------------------------------------------------------

3. Concurrent File Downloader
Objective:
Download multiple files concurrently using threads and compare the time taken with sequential downloads.
Approach:
- Accept List of URLs:
    - Either prompt the user for URLs or read them from a text file.
- Download Functionality:
    - Use a library like requests to fetch the file contents.
    - Save the file locally once downloaded
- Concurrent Downloading:
    - Create one thread for each file download.
    - Optionally use ThreadPoolExecutor from the concurrent.futures module for cleaner thread management.
- Performance Measurement:
    - Capture start and end times for both the threaded and sequential download processes.


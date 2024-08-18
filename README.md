Longest Consecutive subsequence in C
Here, in this page we will discuss the program to find the longest consecutive subsequence in C. We are Given with an array of integers, we need to find the length of the longest sub-sequence such that elements in the sub-sequence are consecutive integers, the consecutive numbers can be in any order.

Longest Consecutive subsequence
Algorithm :
First sort the given input array.
Remove the multiple occurrences of elements, run a loop and keep a length and longestConsecutiveSeq (both initially zero).
Run a loop from 0 to N and if the current element is not equal to the previous (element+1) then set the count to 1 else increase the count.
Update longestConsecutiveSeq  with a maximum of length and longestConsecutiveSeq.
Time and Space Complexity :
Time – complexity : O(n log n)
Space – complexity : O(1)
Code in C
Run
#include <stdio.h>
#include <stdlib.h>

//call back function
int compare(const void * a, const void * b)
{
    return ( *(int*)a - *(int*)b );
}

int findLongestConseqSeq(int arr[], const int n)
{
    int length = 1;
    int longestConsecutiveSeq = 1;
    int i =0;
    
    //sort arr elements using qsort inbuilt function
    qsort( arr,n, sizeof(int), compare);
    for ( i = 0; i < n - 1; i++) {
        if(arr[i] == arr[i+1]) { 
           continue; 
        }
        else if (arr[i] + 1 == arr[i + 1]) { 
           length++; 
        } 
        else {
           length = 1; 
        } 
       longestConsecutiveSeq = (longestConsecutiveSeq > length)? longestConsecutiveSeq: length;
    }
    return longestConsecutiveSeq;
}
int main()
{
    int arr[] = {2,5,7,7,8,8,9,4,10,12,3,6};
    
    const int N = sizeof(arr)/sizeof(arr[0]);
    const int longestConsecutiveSeq = findLongestConseqSeq(arr, N);
    
    printf("Longest Consecutive Sequence is %d",longestConsecutiveSeq);
    return 0;
}
Output :
Longest contiguous Sequence is 9
Related Pages
Find factorial of a Large Number 

Merge 2 sorted arrays without using extra space.

Find all pairs on integer array whose sum is equal to given number 

Kadane’s Algorithm

Find longest consecutive subsequence 

Prime Course Trailer

Related Banners
Get PrepInsta Prime & get Access to all 200+ courses offered by PrepInsta in One Subscription

Get Prime
While loop in C

# blind-7-75
Minimum in rotated sorted array

key things :

All elements are unique

min(nums) will take O(1).

But we are asked to solve in O(logn) , which is binary search.

When it comes to binary search, important thing is to think in terms of how it ends.

like when u narrow down sample to size 3/2/1 ,what can be the possible element combinations and how to get the desired result out of that.

Here we start with l=0 and r=n-1.

while l<r : (i.e single element lists are already eliminated out of main logic)

we try to check if middle element is greater than right element.

This condition indicates that rotation has been done considerably more times(i.e >=n/2 times) 

and hence indicates that minimum element is pushed to the right side of middle element.

here we update l=mid+1

(why mid+1 , means there is already one element to right which is smaller than middle element ,so no chance for middle element to be the minimum element in the list)

else case,

even though rotation has been done , it wasn't enough number of times to push the minimum element to right subarray.

It still exists in left subarray.

Now ,clearly note that the middle element can also be the minimum of the list in this case , so we update r= mid .



The only way this logic comes to end is when both left and right become equal ,that is our required minimum element .

hence return nums[left] or nums[right] either is fine,after we complete loop.
Time complexity: O(logn)
Space complexity : O(1)

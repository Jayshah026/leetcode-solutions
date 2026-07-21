```C++

26. Remove Duplicates from Sorted Array

Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same.

Consider the number of unique elements in nums to be k​​​​​​​​​​​​​​. After removing duplicates, return the number of unique elements k.

The first k elements of nums should contain the unique numbers in sorted order. The remaining elements beyond index k - 1 can be ignored.

Custom Judge:

The judge will test your solution with the following code:

int[] nums = [...]; // Input array
int[] expectedNums = [...]; // The expected answer with correct length

int k = removeDuplicates(nums); // Calls your implementation

assert k == expectedNums.length;
for (int i = 0; i < k; i++) {
    assert nums[i] == expectedNums[i];
}
If all assertions pass, then your solution will be accepted.
 


Example 1:

Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
Example 2:

Input: nums = [0,0,1,1,1,2,2,3,3,4]
Output: 5, nums = [0,1,2,3,4,_,_,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
 

Constraints:

1 <= nums.length <= 3 * 104
-100 <= nums[i] <= 100
nums is sorted in non-decreasing order.




Solution : 

class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int i = 1; 
        for(int j = 1; j < nums.size(); j++){ 
            if(nums[j] != nums[j - 1]){ 
                nums[i] = nums[j];
                i++; 
            }
        }
        return i;
    }
};


Runtime
0 ms, Beats - 100.00%

Memory
22.68 MB, Beats - 52.71%



Explanation : 

- Here first the problem is asking to put the unique elements in the first k positions. Means here we don't have to delete the elements. We just have to change the nums vector with the unique elements only means we have to shift the elements not one by one until the first k elements are becomeing unique, the other last elements which are repeated will be ingnored like they never existed. 

- Now here first we have taken i = 1 means we taken 0th index value as it is so to change the value we will be starting it from the 1st index itself.

- After that we will start a loop from the j = 1 to nums.size() means we will go from the 1st index to the last valid index of the vector. 

- Then we will start comparing the current index and the previous index with the help of this..
nums[j] != nums[j - 1] by this j = 1 then j - 1 = 0. 

- If the values are the same then nothing will happens and nothing will change into the vector. 

- If the values are not the same then we will store the value with the help of i variable. 
nums[i] = nums[j] By this we can easily  store the value of nums[j] into the nums[i]. 

- Here i is starting from the 1st index which means whatever value at the 0th index we will accept it and start modifying the value from the 1st index. 

- When there is a different value in the nums[j] we will change it to the nums[i] from the 1st index and i will increases too because of the different value. and then we will start modifiying the value from the 2nd index like wise.. 
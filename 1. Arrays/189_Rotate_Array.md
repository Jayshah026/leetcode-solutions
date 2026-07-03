```C++ 

189. Rotate Array

Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

 

Example 1:

Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
Example 2:

Input: nums = [-1,-100,3,99], k = 2
Output: [3,99,-1,-100]
Explanation: 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]
 

Constraints:

1 <= nums.length <= 105
-231 <= nums[i] <= 231 - 1
0 <= k <= 105
 

Follow up:

Try to come up with as many solutions as you can. There are at least three different ways to solve this problem.
Could you do it in-place with O(1) extra space?




Solution : 

class Solution {
public:
    void rotate(vector<int>& nums, int k) {
        reverse(nums.begin(), nums.end());

        k %= nums.size();
        
        reverse(nums.begin(), nums.begin() + k);

        reverse(nums.begin() + k, nums.end());
    }
};



Explanation : 

- Here first we have reverse the whole array with the inbuilt function.

- Here we have given the value of k already to use. So here first we will check weather the value of k 
is smaller then the size of the vector. 

- After that we will reverse the array up to k elemenets. 
Ex: If k = 3 then we will first reverse the first 3 elements of the reverse vector. 

With the help of reverse(nums.begin(), nums.begin() + k) -> This means that we will only reverse the vector
from the 0th index to 0 + k'th index. if k = 3 then this will reverse form the 0 to 2nd index.

- After doing that we will take care of elements at the end.

- Here for that we will start wil the k + 1 index to end of the index. 

- By this we can easily rotate the array. 



Runtime
0 ms, Beats - 100.00%

Memory
29.60 MB, Beats - 68.58%
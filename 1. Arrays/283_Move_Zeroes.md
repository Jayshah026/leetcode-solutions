```python

283. Move Zeroes
Solved
Easy

Hint
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

 

Example 1:

Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
Example 2:

Input: nums = [0]
Output: [0]
 

Constraints:

1 <= nums.length <= 104
-231 <= nums[i] <= 231 - 1
 

Follow up: Could you minimize the total number of operations done?




Code 1 : But the problem was it is O(n^2) which is worst case and we don't want this... 

class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        for(int i = nums.size() - 1; i >= 0; i--){
            if(nums[i] == 0){
                int index_to_remove = i;
                nums.erase(nums.begin() + index_to_remove);
                nums.push_back(0);
            }
        }
    }
};

Runtime
8 ms, Beats - 7.96%

Memory
23.88 MB, Beats - 56.59%


Code 2 : This code will have O(n) complexity as per the question

class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n = 0;

        for(int i = 0; i < nums.size(); i++){
            if(nums[i] != 0){
                swap(nums[i], nums[n]);
                n++;
            }
        }
    }
};

Runtime
0 ms, Beats - 100.00%

Memory
23.95 MB, Beats - 19.75%
```python

152. Maximum Product Subarray
Solved
Medium

Given an integer array nums, find a subarray that has the largest product, and return the product.

The test cases are generated so that the answer will fit in a 32-bit integer.

Note that the product of an array with a single element is the value of that element.

 

Example 1:

Input: nums = [2,3,-2,4]
Output: 6
Explanation: [2,3] has the largest product 6.
Example 2:

Input: nums = [-2,0,-1]
Output: 0
Explanation: The result cannot be 2, because [-2,-1] is not a subarray.
 

Constraints:

1 <= nums.length <= 2 * 104
-10 <= nums[i] <= 10
The product of any subarray of nums is guaranteed to fit in a 32-bit integer.



Code :

class Solution {
public:
    int maxProduct(vector<int>& nums) {
        int max_product = nums[0];
        int min_product = nums[0];
        int result = nums[0];

        for(int i = 1; i < nums.size(); i++){
            int current_product = nums[i];

            if(current_product < 0){
                swap(max_product, min_product);
            }

            max_product = max(current_product, current_product * max_product);
            min_product = min(current_product, current_product * min_product);

            result = max(max_product, result);
        }
        return result;
    }
};



Runtime
0 ms, Beats - 100.00% 


Memory
17.80 MB, Beats - 23.79%
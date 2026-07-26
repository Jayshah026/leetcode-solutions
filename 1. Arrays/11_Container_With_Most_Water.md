```python

11. Container With Most Water
Attempted
Medium
Topics
premium lock icon
Companies
Hint
You are given an integer array height of length n. There are n vertical lines drawn such that the two endpoints of the ith line are (i, 0) and (i, height[i]).

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return the maximum amount of water a container can store.

Notice that you may not slant the container.

 

Example 1:


Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
Example 2:

Input: height = [1,1]
Output: 1
 

Constraints:

n == height.length
2 <= n <= 105
0 <= height[i] <= 104




Code 1 : 

class Solution {
public:
    int maxArea(vector<int>& height) {
        int n;
        int m;
        int poll_value;
        int result;
        int index;
        int answer = 0;

        for(int i = 0; i < height.size(); i++){
            n = height[i];
            for(int j = 0; j < height.size(); j++){
                m = height[j];

                if(n == m){
                    poll_value = m;
                }else{
                    poll_value = min(n, m);
                }

                index = j - i;
                if(index < 0){
                    index = -1 * index;
                }
                result = index * poll_value;
                answer = max(result, answer);
            }
        }
        return answer;
    }
};


Here for this code Time Limit Exceeded
58 / 65 testcases passed




Code 2 : Here used the 2 pointer technique in order to get the answer in minimum time. 

class Solution {
public:
    int maxArea(vector<int>& height) {
        int left = 0;
        int right = height.size() - 1;
        int answer = 0;

        while (left < right) {
            int width = right - left;
            int shorter_poll = min(height[left], height[right]);
            int area = width * shorter_poll;
            answer = max(answer, area);

            if (height[left] < height[right]) {
                left++;
            } else {
                right--;
            }
        }

        return answer;
    }
};



Runtime
0 ms, Beats - 100.00%

Memory
62.90 MB, Beats - 49.80%
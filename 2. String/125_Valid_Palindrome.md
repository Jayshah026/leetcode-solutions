``` python 


125. Valid Palindrome
Solved
Easy

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

 

Example 1:

Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
Example 2:

Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.
Example 3:

Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.
 

Constraints:

1 <= s.length <= 2 * 105
s consists only of printable ASCII characters.




Code : 


class Solution {
public:
    bool isPalindrome(string s) {
        string cleaned = "";

        for(char c : s){
            if(isalnum(c)){
                cleaned += tolower(c);
            }
        } 

        string original_string = cleaned;
        reverse(cleaned.begin(), cleaned.end());


        if(original_string == cleaned){
            return true;
        }else{
            return false;
        }
    }
};



Runtime
2 ms, Beats - 36.00%

Memory
10.76 MB, Beats - 5.39%
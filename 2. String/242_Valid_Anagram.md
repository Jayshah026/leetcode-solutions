``` python 

242. Valid Anagram
Solved
Easy

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

 

Example 1:

Input: s = "anagram", t = "nagaram"

Output: true

Example 2:

Input: s = "rat", t = "car"

Output: false

 

Constraints:

1 <= s.length, t.length <= 5 * 104
s and t consist of lowercase English letters.
 

Follow up: What if the inputs contain Unicode characters? How would you adapt your solution to such a case?




Code 1 : 

class Solution {
public:
    bool isAnagram(string s, string t) {
        string st1 = "";
        string st2 = "";

        for(int i = 0; i < s.length(); i++){
            st1 += s[i];
        }
        sort(st1.begin(), st1.end());


        for(int j = 0; j < t.length(); j++){
            st2 += t[j];
        }
        sort(st2.begin(), st2.end());
        

        if(st1 == st2){
            return true;
        }else{
            return false;
        }
    }
};


Runtime
5 ms, Beats - 26.12%

Memory
10.30 MB, Beats - 11.58%




Code 2 : Here i didn't use any loop just change the real string and sort it. 

class Solution {
public:
    bool isAnagram(string s, string t) {
        sort(s.begin(), s.end());
        sort(t.begin(), t.end());

        if(s == t){
            return true;
        }else{
            return false;
        }
    }
};


Runtime
6 ms, Beats - 22.60%

Memory
9.76 MB, Beats - 50.10%
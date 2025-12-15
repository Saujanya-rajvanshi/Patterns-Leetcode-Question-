# Patterns-Leetcode-Question-

### ABAB PATTERN IN STRING 
three approaches 
1. Approach 1: Substring + Repeat (Brute Force / Beginner) //beginer
2. Approach 2: Array / Modulo Comparison (Efficient – Your Idea) //dsa
3. 
```cpp
class Solution {
public:
    bool repeatedSubstringPattern(string s) {
        int n = s.length();

        for (int len = 1; len <= n / 2; len++) {
            if (n % len != 0) continue;

            string pattern = s.substr(0, len);
            string temp = "";

            for (int i = 0; i < n / len; i++) {
                temp += pattern;
            }

            if (temp == s) return true;
        }
        return false;
    
};
//Time: O(n²)
//Easy to understand
```

```cpp
class Solution {
public:
    bool repeatedSubstringPattern(string s) {
        int n = s.length();

        for (int len = 1; len <= n / 2; len++) {
            if (n % len != 0) continue;

            bool match = true;
            for (int i = len; i < n; i++) {
                if (s[i] != s[i % len]) {
                    match = false;
                    break;
                }
            }

            if (match) return true;
        }
        return false;
    }
};
```cppcpp

# Patterns-Leetcode-Question-

## INDEX
1. abab patern in string

### ABAB PATTERN IN STRING 
three approaches 
1. Approach 1: Substring + Repeat (Brute Force / Beginner) //beginer
2. Approach 2: Array / Modulo Comparison (Efficient – Your Idea) //dsa
3. Approach 3: String Trick (Most Optimized & Elegant) //interview
- [Brute Force](#approach-1-brute-force)
- [Modulo Method](#approach-2-array--modulo-comparison)
- [Optimized Trick](#approach-3-string-trick)


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
//Time: O(n²)
//Best for DSA practice
```

## approach-1-brute-force
```cpp
class Solution {
public:
    bool repeatedSubstringPattern(string s) {
        string t = s + s;
        return t.find(s, 1) < s.size();
    }
};
//Time: O(n)
//Space: O(n)
//Most asked in interviews
```


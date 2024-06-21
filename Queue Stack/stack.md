### 1544. [Make the String Great](https://leetcode.com/problems/make-the-string-great/description/) easy
![image](https://github.com/zyalin459/Leetcode/assets/143965223/306a3425-83ea-4e40-9b83-dc25b9f51a9f)

### 1249. [Minimum remove to make valid parentheses](https://leetcode.com/problems/minimum-remove-to-make-valid-parentheses/description/?envType=daily-question&envId=2024-04-06) medium
![image](https://github.com/zyalin459/Leetcode/assets/143965223/f8dbd77a-1f45-4ade-b04f-9d01406fe240)

### 232. [Implementing queue with stacks](https://leetcode.com/problems/implement-queue-using-stacks/description/) (double stack)
![image](https://github.com/zyalin459/Leetcode/assets/143965223/fe93526a-cf55-4f51-8f1f-6d4c966149dc)

### 20. [Valid Parentheses](https://leetcode.com/problems/valid-parentheses/description/)
```c++
for (int i = 0; i < s.length(); i++) {
            if (s[i] == '(' || s[i] == '{' || s[i] == '[') {
                stk.push(s[i]);
            } else {
                if (stk.empty()) return false;
                if (s[i] == ')' && stk.top() != '(' ||
                    s[i] == '}' && stk.top() != '{' ||
                    s[i] == ']' && stk.top() != '[') {
                        return false;
                    }
                stk.pop();
            } 
        }
        return stk.empty();
```

### 150. [Evaluate Reverse Polish Notation](https://leetcode.com/problems/evaluate-reverse-polish-notation/description/)
![image](https://github.com/zyalin459/Leetcode/assets/143965223/09ba02d2-ca3a-4ac5-898f-61287dff6778)





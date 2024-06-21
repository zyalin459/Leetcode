### 59. [Spiral Matrix II](https://leetcode.com/problems/spiral-matrix-ii/description/)
```c++
vector<vector<int>> generateMatrix(int n) {
        std::vector<std::vector<int>> result(n, std::vector<int>(n, 0));
        int top = 0;
        int bottom = n-1;
        int left = 0;
        int right = n-1;
        int val = 1;
        while (top <= bottom && left <= right) {
            for (int i = left; i <= right; i++) {
                result[top].at(i) = val++;
            }
            if (++top > bottom) break;

            for (int i = top; i <= bottom; i++) {
                result[i].at(right) = val++;
            }
            if (--right < left) break;

            for (int i = right; i >= left; i--) {
                result[bottom].at(i) = val++;
            }
            if (--bottom < top) break;

            for (int i = bottom; i >= top; i--) {
                result[i].at(left) = val++;
            }
            if (left++ > right) break;
        }
        return result;
    }
```

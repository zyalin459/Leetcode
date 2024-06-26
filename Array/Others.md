### 287. [Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/description/)

![image](https://github.com/zyalin459/Leetcode/assets/143965223/cbe0d995-446d-4c9a-99d9-3db0e8a42653)

### 1700. [Number of students unable to eat lunch](https://leetcode.com/problems/number-of-students-unable-to-eat-lunch/description/)

![image](https://github.com/zyalin459/Leetcode/assets/143965223/45758a87-f107-40f6-9b1e-7121e683f6b5)

### 3194. [Minimum Average of smallest and largest elements](https://leetcode.com/contest/weekly-contest-403/problems/minimum-average-of-smallest-and-largest-elements/description/)
- `min_element` and `max_element` STL
  - Return an iterator of position, to get the value: `*min_element`
  - Make sure not implement an empty array
  - Can compare, result is same for index comparation
- `vector.erase()`
  - Parameter is position; therefore, we can pass in `min_element`
  - **Erase higher index first**
```c++
double minimumAverage(vector<int>& nums) {
        vector<double> average;
        int size = nums.size();

        while (!nums.empty()) {
            auto minIt = min_element(nums.begin(), nums.end());
            auto maxIt = max_element(nums.begin(), nums.end());

            // Calculate the average and store it
            double avg = (*minIt + *maxIt) / 2.0;
            average.push_back(avg);

            // Correctly erase elements
            if (minIt > maxIt) {  
                nums.erase(minIt);
                nums.erase(maxIt);
            } else {
                nums.erase(maxIt);
                nums.erase(minIt);
            }

            // Stop if we have processed half the original number of elements
            if (average.size() == size / 2) break;
        }

        return *min_element(average.begin(), average.end());
    }
```

[Problem 747, Largest Number At Least Twice of Others](https://leetcode.com/problems/largest-number-at-least-twice-of-others/)  
Written in: C++

~~~cpp
class Solution {
public:
    int dominantIndex(vector<int>& nums) {
        int result = 0, biggest = 0, size = nums.size();
        
        for (int i = 0; i < size; i++) {
            if (biggest < nums[i]) {
                biggest = nums[i];
                result = i;
            }
        }
        
        for (int i = 0; i < size; i++) {
            if (i == result) continue;
            
            if (biggest < nums[i] * 2) {
                result = -1;
            }
        }
        
        return result;
    }
};
~~~
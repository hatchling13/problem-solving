[Problem 1342, Number of Steps to Reduce a Number to Zero](https://leetcode.com/problems/number-of-steps-to-reduce-a-number-to-zero/)

~~~cpp
class Solution {
public:
    int numberOfSteps (int num) {
        int start = num;
        int result = 0;
        
        while (start != 0) {
            start % 2 == 0 ? start /= 2 : start--;
            
            result++;
        }
        
        return result;
    }
};
~~~
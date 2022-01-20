[Problem 724, Find Pivot Index](https://leetcode.com/problems/find-pivot-index/)  
Written in: C++

~~~cpp
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int size = nums.size();
        int result = 0;
        
        if (size == 0) result = -1;
        
        for (int i = 0; i < size; i++) {
            int presum = 0;
            int postsum = 0;
            
            for (int j = 0; j < i; j++) {
                presum += nums[j];
            }
            
            for (int k = i + 1; k < size; k++) {
                postsum += nums[k];
            }
            
            if (presum == postsum) {
                result = i;
                break;
            }
            else result = -1;
        }
        
        return result;
    }
};
~~~

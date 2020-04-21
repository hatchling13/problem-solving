[Problem 1046, Last Stone Weight](https://leetcode.com/problems/last-stone-weight/)
Written in: cpp

~~~cpp
#include <algorithm>

class Solution {
public:
    int lastStoneWeight(vector<int>& stones) {
        int result = 0;
        
        while (stones.size() >= 2) {
            int operand[2] = {};
            
            for (int i = 0; i < 2; i++) {
                auto max = find(stones.begin(), stones.end(), *max_element(stones.begin(), stones.end()));
                
                operand[i] = *max;
                
                stones.erase(max);
            }
            
            int sub = operand[0] - operand[1];
            
            if (sub != 0) (sub > 0) ? stones.push_back(sub) : stones.push_back(-sub);
            
            operand[0] = operand[1] = 0;
        }
        
        (stones.size() == 1) ? result = stones.front() : result = 0;
        
        return result;
    }
};
~~~
[Problem 66, Plus One](https://leetcode.com/problems/plus-one/)  
Written in: cpp

~~~cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int size = digits.size();
        
        digits[size - 1]++;
        
        for (int i = 1; i <= size; i++) {
            if (digits[size - i] == 10) {
                digits[size - i] = 0;
                
                if (i == size) {
                    auto pos = digits.begin();
                    
                    digits.insert(pos, 1);
                }
                
                else {
                    digits[size - i - 1]++;
                }
            }
        }
        
        return digits;
    }
};
~~~
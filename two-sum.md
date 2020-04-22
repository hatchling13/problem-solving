[Problem 1, Two Sum](https://leetcode.com/problems/two-sum/)  
Written in: Rust

~~~rust
impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        let a = nums.iter().enumerate();
        let b = nums.iter().enumerate();

        let mut c = Vec::<i32>::new();

        a.for_each(|(i, x)| b.clone().for_each(|(j, y)| if i != j && x + y == target {
            c.push(i as i32);
            c.push(j as i32);
        }));

        c.truncate(2);

        c
    }
}
~~~
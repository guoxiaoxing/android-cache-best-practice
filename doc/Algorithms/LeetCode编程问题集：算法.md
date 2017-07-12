# LeetCode编程问题集：算法

## 1 Two Sum

### Problem

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,

return [0, 1].

### Solution

思路：以数组值为key，以数组索引为value存于Map中，利用Map的查找功能，做减法查找满足条件的两个数值的索引。

```java
public int[] twoSum(int[] nums, int target) {
    int[] result = new int[2];
    Map<Integer, Integer> map = new HashMap<>();
    for(int i = 0; i < nums.length; i++){
        if(map.containsKey(target - nums[i])){
            result[1] = i;
            result[0] = map.get(target - nums[i]);
            return result;
        }
        map.put(nums[i], i);
    }
    return result;
}
```
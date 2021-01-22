# Two Sum
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.
You can return the answer in any order.

 
- Example 1:
Input: nums = [2,7,11,15], target = 9<br/>
Output: [0,1]<br/>
Output: Because nums[0] + nums[1] == 9, we return [0, 1].<br/>
- Example 2:
Input: nums = [3,2,4], target = 6<br/>
Output: [1,2]<br/>
- Example 3:
Input: nums = [3,3], target = 6<br/>
Output: [0,1]<br/>
 
###violence
```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n = nums.size();
        for (int i = 0; i < n; ++i) {
            for (int j = i + 1; j < n; ++j) {
                if (nums[i] + nums[j] == target) {
                    return {i, j};
                }
            }
        }
        return {};
    }
};

```
### hashtable
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> hashtable = new HashMap<Integer, Integer>();
        for (int i = 0; i < nums.length; ++i) {
            if (hashtable.containsKey(target - nums[i])) {
                return new int[]{hashtable.get(target - nums[i]), i};
            }
            hashtable.put(nums[i], i);
        }
        return new int[0];
    }
}

```

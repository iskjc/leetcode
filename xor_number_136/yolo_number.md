# Intorduction

给你一个 非空 整数数组 nums ，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。

**!!你必须设计并实现线性时间复杂度的算法来解决此问题，且该算法只使用常量额外空间!!**

---
输入：nums = [2,2,1]
输出：1

---
# Solution

#### **1^1=0**      **1^0=1**    **0^0=0**
#### 如上

---
## C++
```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int ans=nums[0];
        for(int i=1;i<nums.size();i++){
            ans^=nums[i];
        }
        return ans;
    }
};
```

## Python
```python
1. class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        result = 0
        for num in nums:
            result ^= num
        return result


2. class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        return reduce(lambda x, y: x ^ y, nums)
```
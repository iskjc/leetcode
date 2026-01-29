# Introduction

给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。

请注意 ，必须在不复制数组的情况下原地对数组进行操作。

---
 **输入: nums = [0,1,0,3,12]**
 **输出: [1,3,12,0,0]**

**输入: nums = [0]**
**输出: [0]**

---
# Solution
使用双指针，开始**l,r**都在**0索引下标**
进入循环，若 **nums[r]!=0** ,交换 l 和 r 仅当此时l++
每一次循环**r++**


---

## C++
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n = nums.size();
        int l = 0, r = 0;
        while (r < n) {
            if (nums[r]) {
                swap(nums[l], nums[r]);
                l++;
            }
            r++;
        }
    }
};
```
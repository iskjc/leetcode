# Introduction

假设你正在爬楼梯。需要 n 阶你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？

---

输入：n = 2
输出：2
解释：有两种方法可以爬到楼顶。

---

# Solution


经典dp，再做不出来就紫砂。

---

```cpp
class Solution {
public:
    int climbStairs(int n) {
        int a = 1, b = 2, c = 0;
        if (n == 1) {
            return a;
        }
        if (n == 2) {
            return b;
        }
        for (int i = 2; i < n; i++) {
            c = a + b;
            a = b;
            b = c;
        }
        return c;
    }
};
```
# Introduction

给定一个非负整数 numRows，生成「杨辉三角」的前 numRows 行。

在「杨辉三角」中，每个数是它左上方和右上方的数的和。

---
输入: numRows = 5

输出: [ [1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1] ]

---
# Solution

vector<vector<int>>  （二维向量）
创建二维向量，包含 numRows 个空行
为当前行创建向量，大小为 i+1（第i行有i+1个元素）

---
## C++
```cpp
class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> ret(numRows);
        for (int i = 0; i < numRows; i++) {
            ret[i].resize(i + 1);
            ret[i][0] = 1;
            ret[i][i] = 1;
            for (int j = 1; j < i; j++) {
                ret[i][j] = ret[i - 1][j - 1] + ret[i - 1][j];
            }
        }
        return ret;
    }
};
```
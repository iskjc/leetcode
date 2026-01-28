# Introduction
给你单链表的头节点 head ，请你反转链表，并返回反转后的链表。

eg:
输入：head = [1,2,3,4,5]
输出：[5,4,3,2,1]

```cpp
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* prev = nullptr;
        ListNode* curr = head;
        while (curr) {
            ListNode* next = curr->next;
            curr->next = prev;
            prev = curr;
            curr=next;
        }
        return prev;
    }
};
```
此为标准模板解法，后续会在 **回文链表_234** 中使用
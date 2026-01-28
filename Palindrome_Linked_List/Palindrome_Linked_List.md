# Introduction

给你一个单链表的头节点 head ，请你判断该链表是否为回文链表。如果是，返回 true ；否则，返回 false。

#### 输入：head = [1,2,2,1]
#### 输出：true
#### 输入：head = [1,2]
#### 输出：false
---
# 要求：
#### 时间复杂度 O(n)
#### 空间复杂度 O(1)

# Solution：
在原链表上操作，使用**快慢指针**将链表发分为**first_half** 和 **second_half**,翻转第二部分，再用**双指针**进行判别。


# C++
```cpp
class Solution {
public:
    bool isPalindrome(ListNode* head) {
        if (head == nullptr) {
            return true;
        }

        ListNode* firstHalfEnd = endOfFirstHalf(head);
        ListNode* secondHalfStart = ReverseList(firstHalfEnd->next);

        ListNode* p1 = head;
        ListNode* p2 = secondHalfStart;
        bool result = true;
        while (result && p2 != nullptr) {
            if (p1->val != p2->val) {
                result = false;
            }
            p1 = p1->next;
            p2 = p2->next;
        }
        firstHalfEnd->next = ReverseList(secondHalfStart);
        return result;
    }

    ListNode* endOfFirstHalf(ListNode* head) {
        ListNode* fast = head;
        ListNode* slow = head;
        while (fast->next != nullptr && fast->next->next != nullptr) {
            fast = fast->next->next;
            slow = slow->next;
        }
        return slow;
    }

    ListNode* ReverseList(ListNode* head) {
        ListNode* prev = nullptr;
        ListNode* curr = head;
        while (curr != nullptr) {
            ListNode* nextTemp = curr->next;
            curr->next = prev;
            prev = curr;
            curr = nextTemp;
        }
        return prev;
    }
};
```

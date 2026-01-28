# Introduction
给你单链表的头节点 head ，请你反转链表，并返回反转后的链表。

eg:
输入：head = [1,2,3,4,5]
输出：[5,4,3,2,1]

```cpp
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
       if(!head){return nullptr;}
       ListNode* pa=head->next;
       ListNode* curr=nullptr;
       head->next=nullptr;
       while(pa){
            curr=pa;
            pa=pa->next;
            curr->next=head;
            head=curr;
       }return head;
    }
};

```
因可能存在空链表
```cpp
ListNode* pa=head->next;
```
可能会因此报错，一定要在前面加上
```cpp
if(!head){return nullptr;}
```
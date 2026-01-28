# Introduction
给你两个单链表的头节点 headA 和 headB ，请你找出并返回两个单链表相交的起始节点。如果两个链表不存在相交节点，返回 null 。

图示两个链表在节点 c1 开始相交：
![alt text](image.png)

使用双指针法
---
### C++
```cpp
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        if(headA==nullptr||headB==nullptr){return nullptr;}
        ListNode * pa=headA,*pb=headB;
        while(pa!=pb){
            pa=pa==nullptr?headB:pa->next;
            pb=pb==nullptr?headA:pb->next;
        }
        return pa;
    }
};
```
两个链表长度分别为a,b，公共节点长度为c，因为循环pa!=pb，若a!=b,则将一起运行a+b次长度链表。若c==0,则在nullptr时退出，返回nullptr。
#### *best comment：这方法离神可能有些距离 但是已经离人很远了*

###


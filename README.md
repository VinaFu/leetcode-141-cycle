# leetcode-141-cycle


# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

class Solution:
    def hasCycle(self, head: Optional[ListNode]) -> bool:
        slow = fast = head               // two pointers at the begining
        while fast and fast.next:        // when fast.next exist; fast exist, we can loop. it is the last one,
            slow = slow.next             // one step one time
            fast = fast.next.next        // two steps one time
            if slow == fast:
                return True
        return False

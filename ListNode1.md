class Solution{
    public ListNode swapPairs(ListNode head){
        if (head == null || head.next == null){
            return head;
        }
        ListNode result = new ListNode(0);
        result.next = head;
        ListNode q = result;
        while (q.next != null && q.next.next != null){
            ListNode pre = q.next;
            ListNode preNext = pre.next;
            ListNode cur = preNext.next;

            preNext.next = pre;
            pre.next = cur;
            q.next = preNext;
            q = pre;
        }
        return result.next;
    }
}
//链表的经典题目：两两交换链表中的节点
//给定一个链表，两两交换其中相邻的节点，并返回交换后的链表。你不能单纯的改变节点内部的值，而是需要实际的进行节点交换。
//例如：1,2,3,4变成2,1,4,3；   
//1,2,3,4,5变成2,1,4,3,5

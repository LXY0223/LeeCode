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

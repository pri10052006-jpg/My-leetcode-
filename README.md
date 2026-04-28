class Solution {
    public boolean isPalindrome(int x) {
        int r=0;
        int y=x;
        while(y>0){
            r=(r*10)+y%10;
            y/=10;
        }
        if(x==r)
            return true;
        else
            return false;
    }
}
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[] { map.get(complement), i };
            }
            map.put(nums[i], i);
        }
        return new int[] {};
    }
}
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy=new ListNode(0);
        ListNode current=dummy;
        int c=0;
        while(l1!=null||l2!=null||c!=0){
            int sum=c;
            if(l1!=null){
                sum+=l1.val;
                l1=l1.next;
            }
            if(l2!=null){
                sum+=l2.val;
                l2=l2.next;
            }
            c=sum/10;
            current.next=new ListNode(sum%10);
            current=current.next;
        }
        
        return dummy.next;
        
    }
}
Given a string s, find the length of the longest substring without duplicate characters.
class Solution{
    public int lengthOfLongestSubstring(String s) {
    int left = 0, maxLen = 0;
    HashSet<Character> set = new HashSet<>();

    for (int right = 0; right < s.length(); right++) {
        char c = s.charAt(right);

        while (set.contains(c)) {
            set.remove(s.charAt(left));
            left++;
        }

        set.add(c);
        maxLen = Math.max(maxLen, right - left + 1);
    }

    return maxLen;
    }
}

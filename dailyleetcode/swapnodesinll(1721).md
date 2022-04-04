problem link:

https://leetcode.com/problems/swapping-nodes-in-a-linked-list/

Approach1: Traverse through ll, find total no.of nodes(n), using two traversals, find data at kth and n-k+1th nodes and swpa the data in nodes.

Time- O(n)+O(n)+O(n)(one for finding n, one to traverse upto k and other upto n-k+1)

space- O(1)

class Solution {

public:

    ListNode* swapNodes(ListNode* head, int k) {

        int n=0,i;

        ListNode* temp=head;

        while(temp!=NULL)

        {

             n++;

            temp=temp->next;

        }

        int r=n-k+1;

        int j=1;

        i=1;

        temp=head;

        ListNode* temp1=head;

        for(i=1;i<k;i++)

            temp=temp->next;

        int t1=temp->val;

        for(i=1;i<r;i++)

            temp1=temp1->next;

        int t2=temp1->val;

        temp->val=t2;

        temp1->val=t1;

        return head;

    }

};

Approach2: Traverse upto kth node, store the node in other pointer. Consider new pointer from head, and current pointer which is at kth node and move them simultaneously till the end of ll(i.e; they travel n-k nodes)

As we start from node1, the second pointer has travelled n-k+1  nodes; and hence, values are swapped

Time-O(k)+O(n-k)

space-O(1)

class Solution {

public:

    ListNode* swapNodes(ListNode* head, int k) {

      int i=1;

        ListNode* temp1=head;

        for(i=1;i<k;i++)

        {

            temp1=temp1->next;

        }

        ListNode* dummy=temp1;

        ListNode* temp2=head;

        while(temp1->next!=NULL)

        {

            temp1=temp1->next;

            temp2=temp2->next;

        }

        int t = temp2->val;

        temp2->val=dummy->val;

        dummy->val=t;

        return head;

    }

};

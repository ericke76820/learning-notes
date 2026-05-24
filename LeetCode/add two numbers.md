/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */
struct ListNode* addTwoNumbers(struct ListNode* l1, struct ListNode* l2) {
    int carry = 0;
    int sum = 0;
    struct ListNode *result = malloc(sizeof(struct ListNode)); 
    result -> val = 0;
    result -> next = NULL;
    struct ListNode *current = result;


    while(l1 != NULL || l2 != NULL || carry > 0){
        int val1 = (l1 != NULL) ? l1 ->val : 0;
        int val2 = (l2 != NULL) ? l2 ->val : 0;

        sum = carry + val1 + val2;
        
        current -> next = malloc(sizeof(struct ListNode));
        current = current -> next;

        carry = sum / 10;
        current -> val = sum % 10;
        current -> next = NULL;
        
        if (l1) l1 = l1 -> next;
        if (l2) l2 = l2 -> next;
    }

    return result -> next;
}

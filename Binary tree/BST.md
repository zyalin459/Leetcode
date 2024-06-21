### 108. [Covert sorted Array to BST](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/)
Binary search simulation
```c++
class Solution {
public:
    TreeNode* sortedArrayToBSTHelper(vector<int>& nums, int start, int end) {
        if (start > end) return nullptr;

        int mid = (start + end) / 2;
        TreeNode* node = new TreeNode(nums[mid]);
        node -> left = sortedArrayToBSTHelper(nums, start, mid - 1);
        node -> right = sortedArrayToBSTHelper(nums, mid + 1, end);
        return node;
    }
    TreeNode* sortedArrayToBST(vector<int>& nums) {
        if (nums.empty()) return nullptr;
        return sortedArrayToBSTHelper(nums, 0, nums.size()-1);
    }
};
```

### 109. [Convert sorted list to BST](https://leetcode.com/problems/convert-sorted-list-to-binary-search-tree/description/)
Binary search simulation
```c++
class Solution {
public:
    int getListSize(ListNode* head) {
        if (head == nullptr) return 0;
        ListNode* cur = head;
        int size = 0;
        while (cur != nullptr) {
            size++;
            cur = cur -> next;
        }
        return size;
    }

    TreeNode* sortedListToBSTHelper(ListNode* node, int start, int end) {
        if (start > end) return nullptr;
        int mid = (start + end) / 2;
        ListNode* cur = node;
        for (int i = 0; i < mid; i++) {
            cur = cur -> next;
        }
        TreeNode* parent = new TreeNode(cur -> val);
        parent -> left = sortedListToBSTHelper(node, start, mid - 1);
        parent -> right = sortedListToBSTHelper(node, mid + 1, end);
        return parent;
    }

    TreeNode* sortedListToBST(ListNode* head) {
        return sortedListToBSTHelper(head, 0, getListSize(head)-1);
    }
};
```

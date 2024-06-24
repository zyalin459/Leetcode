### 226. [Invert Binary tree](https://leetcode.com/problems/invert-binary-tree/description/)
![image](https://github.com/zyalin459/Leetcode/assets/143965223/2bcf1afc-b6d4-40fe-bb11-609503c19122)

### 101. [Symmetric Binary Tree](https://leetcode.com/problems/symmetric-tree/description/)
![image](https://github.com/zyalin459/Leetcode/assets/143965223/54ec5bc4-4fa1-4e60-9c14-5b84973ab87e)

### 111. [Minimum Depth of Binary Tree](https://leetcode.com/problems/minimum-depth-of-binary-tree/description/)
![image](https://github.com/zyalin459/Leetcode/assets/143965223/21154adc-12d6-4921-ab76-26fc295574a5)

### 222. [Count Complete Tree Nodes](https://leetcode.com/problems/count-complete-tree-nodes/description/)
![image](https://github.com/zyalin459/Leetcode/assets/143965223/78f695a0-d904-4d07-8d31-f1b0514e559a)

### 257. [Binary Tree Path](https://leetcode.com/problems/binary-tree-paths/description/)
![image](https://github.com/zyalin459/Leetcode/assets/143965223/59197188-8b5e-4708-a077-fd95cf296ace)

### 404. [Sum of Left leaves](https://leetcode.com/problems/sum-of-left-leaves/description/)
![image](https://github.com/zyalin459/Leetcode/assets/143965223/2e72eaf4-1bd7-40c4-ac54-2b148d73eeee)


### 112. [Path Sum](https://leetcode.com/problems/path-sum/description/) Easy
Given a root and targetSum, return true if find a path from the root to leaf that sum of their value is equal to the targetSum
#### Ideas
- No logic about dealing with the mid-node => all order traversal are okay!
#### Code
```c++
bool traversal(TreeNode* node, int count) {  // about target: minus the node everytime => 0 -- true
  // Stop condition: meet leaf node
  if (node -> left == nullptr && node -> right == nullptr && count == 0) return true;
  if (node -> left == nullptr && node -> right == nullptr && count != 0) return false;
  if (node -> left) {
      count -= node -> left -> val;
      if(tarversal(node->left, count)) return true;
      count += node-> left -> val; //  backtracking: After finishing all left recursion, should go bakc to the root and
                            // continue the right path
  }
  if (node -> right) {
    count -= node -> right;
    if (traversal(node -> right, count)) return true;
    count += node -> right -> val;
  }
  return false;
}

bool hasPathSum(TreeNode* root, int sum) {
  if (root == NULL) return false;
  return traversal(root, sum - root->val);
}
```


### 106. [Construct Binary Tree from Inorder and Postorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/description/)
![IMG_BF67802F860B-1](https://github.com/zyalin459/Leetcode-Problem-Notes/assets/143965223/0b7986dc-8c3f-41be-aba2-577726946b99)




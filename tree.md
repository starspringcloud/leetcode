## 树的题目的核心是如何dfs，不断分割递归集合
### 树的从上到下遍历，要用前序遍历
### 树的从下到上遍历，要用后序遍历(左右中）
236. 二叉树的最近公共祖先
```
 // 树的从下到上遍历，要用后序遍历
  if (root == nullptr || root == p || root == q)
  {
      return root;
  }
  // 左
  TreeNode* left = lowestCommonAncestor(root->left, p, q);
  // 右
  TreeNode* right = lowestCommonAncestor(root->right, p, q);
  // 中的逻辑
  if (left == nullptr) return right;
  if (right == nullptr) return left;
  return root;
```

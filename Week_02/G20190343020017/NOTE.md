# 学习内容
### 1. 哈希表（散列表）
键值对形式存储的数据结构，能够通过哈希函数将 Key value 映射到数据所在的下标，因此查询增加删除的时间复杂度都是 O(1)（在哈希函数不合适发生哈希碰撞最坏的情况下复杂度会退化到O(n)）。
- *哈希表的内部实现关键在于**哈希函数**，哈希函数可以有很多种，如 Java 的 hashCode，哈希函数计算 Key value 返回一个下标，不同的 Key value 返回相同下标的情况叫做**哈希碰撞**。为避免碰撞要选择合适的哈希函数。*
  
- ***拉链式解决冲突法**是在发生哈希碰撞的解决方案，也就是在同一个位置以链表的形式存储多个元素。*
### 2. 集合
集合可以视为特殊的哈希表（值为空，Java 中 HashSet 就是放了 PRESENT 占位符的 HashMap）
### 3. 树
常见名词：根节点，子节点，兄弟节点，父节点，左儿子，右儿子，叶子节点。如斐波拉契数列可以展开为递归二叉树。查找节点的时间复杂度为 O(n)。
- *树是特殊的图，链表是特殊的树*
- *三种遍历方式（按照根节点顺序）：*
  - *前序遍历 Pre-order：根节点，左子节点，右子节点*
  - *中序遍历 In-order：左子节点，根节点，右子节点*
  - *后序遍历 Post-order：左子节点，右子节点，根节点*

#### 二叉搜索树（有序二叉树，排序二叉树，二叉查找树）BST Binary Search Tree
空树或满足以下条件：
1. 左子树所有节点的值均小于根节点的值
2. 右子树所有节点的值均大于根节点的值
3. 左右子树也分别为二叉搜索树

二叉搜索树的特点：
- *二叉搜索树在中序遍历的情况下是升序排列*
- *二叉搜索树访问节点过程类似二分法，增加查询删除的时间复杂度为 O(logn)*
- *二叉搜索树在删除节点时需要拿最近一个大于该节点值的节点来替换占位*
# 总结
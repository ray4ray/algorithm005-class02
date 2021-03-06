LeetCode解题心得-49:
小白一名，之前没用过哈希表，实际使用后发现，其实是可以当成数组来使用，主要是将Key唯一化，作为数组的下标。
而异构词这种字母相同，但顺序不同的，可以通过字符串排序，这样所有的异构词就会变成一种形式。
更普通些的，可以直接统计26个字母的出现次数，但这样如果不仅字母的话就会加大难度。
如果单从判断异构词出发，可以在对比过程中，一个词负责递增，另一个词负责递减，最后结果是全部归零就证明属于异构词。

LeetCode解题心得-94:
二叉树的遍历使用递归是从定义出发最简单的想法，为了挑战下其他解法，还看了题解的栈方法。
前序排序还好，就是把中间节点压栈，出栈后分别压右子树和左子树（这里是先右再左，因为出栈是先左后右）。
但中序遍历的话，这种重复就不这么明显，要按照树的路径，从根节点出发，一路把左子树先全部压栈。
然后下面就有几种情况：
1、出栈的是左子树的叶子节点，按理应该弹出栈中下一个元素；
2、出栈的是某个父节点，有右子树，那么下一步是处理其右子树。重复上面压左子树的过程
3、出栈的是某个父节点，没有右子树，弹出栈顶元素
题解中就是将三种情况合并，统一将cur设为右子树，右子树如果为空，则直接弹栈顶元素；
如果右子树不为空，则将右子树，及其孙子节点一路压栈。

LeetCode解题心得-236:
真正体会到什么是不要纠结递归的过程，牢记递归的三要素，终止条件、当前层逻辑，递推公式。
在这个题目中递推公式是，从根节点出发求解可以分解成分别从左子树出发和右子树出发。
终止条件是已经到达叶子节点，
1、发现目标节点，直接返回叶子节点（也是当层的root）.
2、没有发现目标节点，应该返回null，引用递推公式的左右子树，叶子节点并不存在左右子树，可以让root==null时，返回null。
上面两个合并，就是统一输出root。
在画图验证时发现这种终止条件还可以包含一种情况，是两个目标元素在同一条单向树的链条上，也可以通过发现目标节点来直接返回root。
当层逻辑是左右子树返回的结果如何整合成当前层的返回，有三种情况：（大神合并的写法好难理解）
1、左右子树都是null，返回null；
2、左右子树都是非null，返回root；
3、左右子树有一个null，一个非null，返回非null的子树结果。
其中第二种情况就是对应已经发现最近共同祖先节点，只是对于递归链条还需要往上走回根节点。
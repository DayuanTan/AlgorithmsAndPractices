 # Binary tree DC

 ## Time complexity O(n)
 ## Space complexity O(n)

 Java
 ```java
 public ResultType divideConquer(TreeNode node){
    //递归出口
    //一般处理node==null就够了，大部分情况不需要处理node==leaf
    if (node == null){
        return ...; // 处理空节点应该返回的结果
    }

    // if (node.left == null && node.right == null){
    //     // 处理叶子节点应该返回的结果
    //     // 如果叶子节点的返回结果可以通过两个空节点的返回结果得到就省略这一段代码
    // }

    // 处理左子树
    ResultType leftResult = divideConquer(node.left);
    // 处理右子树
    ResultType rightResult = divideConquer(node.right);
    // 合并答案
    ResultType result = merge leftResult and rightResult;
    return result;
 }
 ```

 py
 ```py
 def divide_conquer(root):
    # 递归出口
    # 一般处理node==null就够了，大部分情况不需要处理node==leaf
    if root is None:
        return ... # 处理空节点应该返回的结果
    
    if not root.left and not root.right:
        处理叶子节点应该返回的结果
        如果叶子节点的返回结果可以通过两个空节点的返回结果得到就省略这一段代码

    # 处理左子树
    left_result = divide_conquer(root.left)
    # 处理右子树
    right_result = divide_conquer(root.right)
    # 合并答案
    result = merge left_result and right_result
    return result
 ```
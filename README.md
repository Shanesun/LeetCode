# 数据结构和算法
`程序` = `数据结构` + `算法`

## 数据结构

### 1. 数组和链表

数组与链表不同操作造成的时间复杂度：

| 操作 | 数组 | 链表 |
| ---- | ---- | ---- |
| 查找 | O(1) | O(n) |
| 插入 | O(n) | O(1) |
| 删除 | O(n) | O(1) |

**数组**，在内存中是一段连续的内存地址，可以通过下标偏移就可找到对应元素，所以时间负载度O(1)。但是在面对插入或者删除时，会造成七天元素移动来填满这段连续内存地址，所以时间复杂度是O(n)。

**链表**，在内存中是分散的内存地址。

### 2. Hash表



### 3. 队列

一种FIFO先进先出的数据结构。以数组作为底层数据结构的语言中，通常`队列`都是通过`循环数组`来实现。使用`循环数组`比普通`数组`更加高效、节约空间。  
[题目：使用循环数组实现队列]()  
[使用循环数组实现队列思路](https://leetcode-cn.com/explore/featured/card/queue-stack/216/queue-first-in-first-out-data-structure/865/)  

#### 广度优先搜索(BFS)

`广度优先搜索`（BFS）是一种`遍历或搜索`数据结构（如树或图）的算法。主要运用常见在`遍历`或`找出最短路径`。
[使用BFS查找最短路径]()

#### 深度优先(DFS)

`深度优先搜索`优先遍历节点深度。多用递归的方式，但是考虑到递归的局限性，通常也会考虑非递归的实现方式。

#### 剪枝

剪枝策略，属于算法优化范畴；通常应用在DFS 和 BFS 搜索算法中。剪枝策略就是寻找过滤条件，提前减少不必要的搜索路径。

### 4. 栈



### 5. 图

* BFS

* DFS


### 6. 树

* 深度优先遍历
1. 先序遍历
```c
void pre_order_traversal(TreeNode *root) {
    // Do Something with root
    if (root->lchild != NULL)
        pre_order_traversal(root->lchild);
    if (root->rchild != NULL)
        pre_order_traversal(root->rchild);
}
```
2. 中序遍历
```c
void in_order_traversal(TreeNode *root) {
    if (root->lchild != NULL)
        in_order_traversal(root->lchild);
    // Do Something with root
    if (root->rchild != NULL)
        in_order_traversal(root->rchild);
}
```
3. 后序遍历
```c
void post_order_traversal(TreeNode *root) {
    if (root->lchild != NULL)
        post_order_traversal(root->lchild);
    if (root->rchild != NULL)
        post_order_traversal(root->rchild);
    // Do Something with root
}
```
每一种遍历都包含递归和非递归两种方式。递归的本质是栈，非递归算法其实就是递归换成栈结构实现。

* 广度优先遍历
  队列实现

## 算法
### 双指针技巧

#### 1. 从两端向中间迭代

**同时使用两个指针**进行迭代，使用双指针技巧的典型场景之一是你想要**从两端向中间迭代**数组。这时你可以使用双指针技巧：**一个指针从始端开始，而另一个指针从末端开始**。值得注意的是，这种技巧经常在**排序数组**中使用。

常见场景：

1. 反转数组中的元素  
2. 快速排序变种算法
3. 数据排序  

[344. 反转字符串](#344-反转字符串)  

#### 2. 快慢指针

> 经典题目：给定一个数组和一个值，原地删除该值的所有实例并返回新的长度。考虑空间限制，不重新创建空间。  
> 解决方案：我们使用两个指针：一个仍然用于迭代，而第二个指针总是指向下一次添加删除元素的位置。 

```swift
func removeElement(nums: [Int], val: Int) {
    let k = 0
    for i in 0..<nums.count {
        if nums[i] != val {
            nums[k] = nums[i]
            k += 1
        }
    }
    return k
}
```

[167. 两数之和 II - 输入有序数组](#167-两数之和-ii-输入有序数组)   

#### 3. 滑窗指针

**使用两个指针一前一后遍历**，根据前后指针不同位置，指针闭区间内可以覆盖所有连续组合。  
[209. 长度最小的子数组](209-长度最小的子数组) 

### 排序

好的排序排序算法时间复杂度应该是nlogn，以下是常见的7中排序：

| 名称 | 时间复杂度 | 空间复杂度 | 是否稳定 |
| --- | --- | --- | --- |
| 冒泡排序 | O(n^2) | O(1) | 是 |
| 插入排序 | O(n^2) | O(1) | 是 |
| 选择排序 | O(n^2) | O(1) | 否 |
| 堆排序 | O(nlogn) | O(1) | 否 |
| 归并排序 | O(nlogn) | O(n) | 是 |
| 快速排序 | O(nlogn) | O(logn) | 否 |
| 桶排序 | O(n) | O(k) | 是 |




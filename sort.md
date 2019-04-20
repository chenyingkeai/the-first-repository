[TOC]

### 快排：

##### 以下为用到的函数和方法

this.quickSort:*声明一个主方法来调用递归函数，传递待排序数组*

quick:递归函数，用来拆分数组，拆分成一个较大数组和一个较小数组

partition:

+ 先用Math.floor()确定中间项，将这个项对应的值作为Pivot
+ 设置两个指针，分别从左右两端开始移动
+ 在未到达pivot之前，若碰到了左边的数大于pivot右边的数小于pivot的情况则交换
+ 返回i的最后值用于分割数组
+ 分割之后重复步骤

swapQuickSort：用于交换数字

#####  时间复杂度

因为每次都一分为二，所以2^k=n, k=logn,可知有logn层

每一层最多交换n次，所以结果就是O(nlogn),

##### 优化：

+ 采取三数取中法：选取左中右三个数，按排序所需顺序交换位置，用中间数作为枢轴(上面描述的快排用的仅是中间数)

+ 当排序序列长度分割到一定大小时，使用插入排序
+ 在一次分割结束后，可以把与key想等的元素聚在一起

### 归并

##### 所用函数与方法

mergeSort：:*声明一个主方法来调用递归函数，传递待排序数组，每当要实现一个递归函数，我们都会实现一个实际被执行的辅助函数*

mergeSortREC：

+ 将数组不断地进行左右拆分直到数组长度为1

+ slice() 方法可从已有的数组中返回选定的元素
+  return merge(mergeSortRec(left), mergeSortRec(right))在这个语句里递归分化成无数个小数组然后用merge归并

merge：

+ 使用push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度
+ if(left[il] < right[ir]) {  result.push(left[il++]);   }相当与push(left());i++；
+ 左右两个数组不断比较迭代成一个大数组，不断进行直到排序完成

##### 时间复杂度

归并排序每次会把当前的序列一分为二，然后两部分各自排好序之后再合并，可以手动模拟出一颗二叉树来，每一层的总计算量是O(n)的，因为每次都一分为二，所以2^k=n, k=logn,可知有logn层，即结果是O(nlogn)

##### 优化

大概这个代码思路是优化过的了？我想不到啥优化的方法，博客上的优化方法感觉也不是很适合。。。
# 选择排序

选择排序 (Selection-sort) 是一种简单直观的排序算法。它的工作原理：首先在未排序序列中找到最小 (大) 元素，存放到排序序列的起始位置；然后，再从剩余未排序元素中继续寻找最小 (大) 元素，然后放到已排序序列的末尾。以此类推，直到所有元素均排序完毕。

![](./img/selection_sort.gif)

### 算法描述

n个记录的直接选择排序可经过 n-1 趟直接选择排序得到有序结果。具体算法描述如下：

1. 初始状态：无序区为 R[1..n] ，有序区为空；

2. 第 i 趟排序 (i=1,2,3…n-1) 开始时，当前有序区和无序区分别为 R[1..i-1] 和 R(i..n)。该趟排序从当前无序区中选出关键字最小的记录  R[k]，将它与无序区的第1个记录 R 交换，使 R[1..i] 和 R[i+1..n) 分别变为记录个数增加1个的新有序区和记录个数减少1个的新无序区；

3. n-1 趟结束，数组有序化了。

### 代码

```python
def selection_sort(array):
    """
    选择排序算法的代码实现
    :param array: 一个数组
    :return: 一个升序数组
    """
    length = len(array)
    for i in range(length):
        index_of_min_elem = i
        for j in range(i + 1, length):
            if array[index_of_min_elem] > array[j]:
                index_of_min_elem = j
        if index_of_min_elem != i:
            array[i], array[index_of_min_elem] = array[index_of_min_elem], array[i]
    return array
```


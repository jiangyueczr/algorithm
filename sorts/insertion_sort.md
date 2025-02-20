# 插入排序

插入排序 (Insertion-Sort) 的算法描述是一种简单直观的排序算法。它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。

![](./img/insert_sort.gif)

### 算法描述

1. 从第一个元素开始，该元素可以认为已经被排序；
2. 取出下一个元素，在已经排序的元素序列中从后向前扫描；
3. 如果该元素 (已排序) 大于新元素，将该元素移到下一位置；
4. 重复步骤3，直到找到已排序的元素小于或者等于新元素的位置；
5. 将新元素插入到该位置后；
6. 重复步骤2~5。

### 代码

```python
def insert_sort(array):
    """
    :param array: 一个数组
    :return: 一个升序数组
    """
    for i in range(1, len(array)):
        j = i
        while j > 0:
            if array[j] <= array[j - 1]:
                array[j], array[j - 1] = array[j - 1], array[j]
            else:
                break
            j -= 1
    return array


# 更优的实现
def insert_sort2(array):
    """
    :param array: 一个数组
    :return: 一个升序数组
    """
    for insert_index, insert_value in enumerate(array[1:]):
        temp_index = insert_index
        while insert_index >= 0 and insert_value < array[insert_index]:
            array[insert_index + 1] = array[insert_index]
            insert_index -= 1
        if insert_index != temp_index:
            array[insert_index + 1] = insert_value
    return array
```


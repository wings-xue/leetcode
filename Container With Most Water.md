## 题目
给一个列表L， 寻找这个L可以装的最多的谁

## 思路
分别从两边遍历， 如果最短的边大于之前最长的边， 比较这个面积和之前最大面积。

## 例子

Input:Input: [1,8,6,2,5,4,8,3,7]
Output: 49

## 代码
```
class Solution:
    def maxArea(self, height):
        """
        :type height: List[int]
        :rtype: int
        """
        max_area = 0
        max_height = 0
        i ,j = 0, len(height) - 1

        while i < j:

            if height[i] <height[j]:
                n = height[i]
                i += 1

            else:
                n = height[j]
                j -= 1


            if n >max_height:
                max_height = n
                max_area = max(max_area,n*(j-i+1))

        return max_area
```

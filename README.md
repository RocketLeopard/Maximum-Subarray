# Maximum-Subarray（最大子序和）
给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。  

## Sample
输入: [-2,1,-3,4,-1,2,1,-5,4]  
输出: 6  
解释: 连续子数组 [4,-1,2,1] 的和最大，为6。 

## Solution
使用动态规划求解。  
设sum[i]是以第i个元素结尾且和最大的连续子数组。  
那么对于元素i，在它前面的元素组成的最大连续数组是已知的，因此，以元素i结尾且和最大的连续子数组，实际上要么是以第i-1个元素结尾且和最大的连续子数组加上这个元素，要么是只包含第i个元素，即sum[i] = max(sum[i-1] + a[i], a[i])。可以通过判断sum[i-1] + a[i]是否大于a[i]来做选择，而这实际上等价于判断sum[i-1]是否大于0。由于每次运算只需要前一次的结果，因此并不需要像普通的动态规划那样保留之前所有的计算结果，只需要保留上一次的即可，因此算法的时间和空间复杂度都很小

## 复杂度分析
时间复杂度：O(N)。只遍历了一次数组。  
空间复杂度：O(1)，使用了常数的空间。  

## 备注
来源 力扣（LeetCode）
链接：https://leetcode-cn.com/problems/maximum-subarray

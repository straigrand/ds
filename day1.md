###  **数组**art01



##### **704. 二分查找** 

参考资料：

题目链接：https://leetcode.cn/problems/binary-search/

文章讲解：[https://programmercarl.com/0704.%E4%BA%8C%E5%88%86%E6%9F%A5%E6%89%BE.html](https://programmercarl.com/0704.二分查找.html)

视频讲解：https://www.bilibili.com/video/BV1fA4y1o715



自我理解：

二分法使用条件：有序，无重复元素。

对于二分法，重要的是对区间处理的问题。有左闭右闭和左闭右开两种。

下面主要写左闭右闭的代码

```c++
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int n = nums.size();
        int left = 0;
        int right = n - 1;
        //因为左闭右闭，所以等号也有效
        while(left<=right){
            int mid = (left + right) / 2;
            if(nums[mid] < target){
                //区间为左闭右闭，所以应该将左边换到中间的右边，想象成块状。
                left = mid + 1;
            }
            else if(nums[mid] > target){
                right = mid - 1;
            }
            else{
                return mid;
            }
        }
        return -1;

    }
};
```

##### 35.搜索插入位置

题目链接：[35. 搜索插入位置 - 力扣（LeetCode）](https://leetcode.cn/problems/search-insert-position/)

第一想法：

使用暴力解法，从最开始往后找，如果等于返回，遇到小于的则返回该元素下标。



代码随想录思路：

使用二分法，找到元素即返回下标，没找到返回插入位置时候，就返回left。



代码同二分法



#####  **27. 移除元素**

题目链接：https://leetcode.cn/problems/remove-element/ 

文章讲解：[https://programmercarl.com/0027.%E7%A7%BB%E9%99%A4%E5%85%83%E7%B4%A0.html](https://programmercarl.com/0027.移除元素.html)

视频讲解：https://www.bilibili.com/video/BV12A4y1Z7LP 



第一想法：

暴力解法，使用两个for循环，如果遇到该元素要删除，则该元素后的所有元素都向前移动，然后size--。



文章思路：

通过快慢指针，搞清楚快慢指针的作用是什么？就可以解决这道题

快指针：遍历数组的所有元素，如果遇到非目标元素的，就将它替换到新数组。

慢指针：表示新数组的下标



代码：

```c++
int slow = 0;
for(int fast = 0; fast < nums.size(); fast++){
    if(nums[fast] != val){
        nums[slow] = nums[fast];
        num++;
    }
}
```


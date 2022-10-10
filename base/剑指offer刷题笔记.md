#### [剑指 Offer 04. 二维数组中的查找](https://leetcode.cn/problems/er-wei-shu-zu-zhong-de-cha-zhao-lcof/)
从**右上角**或者左下角开始搜索均可。证明：例如，从右上角开始搜索，当前值过小则下移，当前值过大则左移。假设下移，则**下一行的右侧一定大于当前行的右侧**，而当前行的右侧又是因为过大而被我们左移而抛弃的，所以不可能是目标值。

#### [剑指 Offer 07. 重建二叉树](https://leetcode.cn/problems/zhong-jian-er-cha-shu-lcof/)
写出了递归法，`迭代法还没看`。

#### 剑指 Offer 09. 用两个栈实现队列
很巧妙。设置了A、没有 B两个栈。每次入队时数据先进入B栈，出队则从A栈出，若A中无数据，则从B中pop出数据，push进A。

#### [剑指 Offer 11. 旋转数组的最小数字](https://leetcode.cn/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/)
二分的逻辑很巧妙。一个旋转了n次的数组，**二分后必定一半有序一半无序**。若target不在有序部分，则继续对半分无序的部分进行查找。

#### 剑指 Offer 14- I. 剪绳子
动态规划

#### [剑指 Offer 16. 数值的整数次方](https://leetcode.cn/problems/shu-zhi-de-zheng-shu-ci-fang-lcof/)
经典快速幂。此外注意幂可能为0或负数。

#### 剑指 Offer 22.链表中的倒数第k个节点
标答使用双指针更巧妙一些。fast先走K步，low再从终点出发一直走。

#### 剑指 Offer 24. 反转链表
O(n)即可，遍历一次链表完成反转，比较巧妙。设置一个pre节点，一个cur节点，一个next节点，每遍历一个节点，就对该节点的连接方式进行修改。遍历到末尾时即可获得头结点指针。

#### 剑指 Offer 25. 合并两个排序的链表
本题可以先新建一个节点（使用构造函数）作为哨兵节点，之后再在此基础上合并。最后只需要返回哨兵的next即可，会更方便。

#### [剑指 Offer 26. 树的子结构](https://leetcode.cn/problems/shu-de-zi-jie-gou-lcof/)
中等题。花了比较多的时间AC。在笔试中这道题应该果断使用递归来解决，因为笔试不考察效率，用非递归的方式会大大增加代码量与调试难度。在笔试中要注意！
此题的标答递归非常简短精炼、推荐多看看感受一下。

#### 剑指 Offer 29. 顺时针打印矩阵
简单题，但是下标的处理非常麻烦。参考答案中为上下左右四个边界设置了4个int，t,b,l,r，每次遍历完一行或一列就缩减对应的边界，当缩减完的边界不符合t>b或r>l的时候，循环结束。
#### 剑指 Offer 30. 包含min函数的栈
简单题，但不会。由于是一个栈，所以本题实际上只需要在保存当前栈的val的同时再保存一个min即可。可以发现，剑指offer还是必须刷一遍的，很多简单但是难以想到的方法，非常巧妙。
#### 剑指 Offer 31. 栈的压入、弹出序列
中等题。比较巧妙的方式是模拟栈的压入和弹出，通过试探每一步是否可以弹出栈，来判断是否存在一个可行的解。
#### 剑指 Offer 32 - II. 从上到下打印二叉树 II
层序遍历，但要对每层分别输出。类似普通层序遍历，只需要在每层遍历之前查看一下当前队列的长度，并遍历一次该长度，就可获取这一层的元素。
#### 剑指 Offer 35. 复杂链表的复制
关键在使用一个unordered_map来保存node* 与node* （即两个链表之间指针）的对应关系。对于当前节点head，先查看head是否在map中，不在则新建一个对应的node并加入map，然后递归建立该node的next与random。
#### 剑指 Offer 36. 二叉搜索树与双向链表
中等题，使用递归的思想，用中序遍历原地完成转换，难度在于对指针的操作与分析。
#### 剑指 Offer 40. 最小的k个数
使用堆，或者快速排序思想来解决该题。

#### [剑指 Offer 46. 把数字翻译成字符串](https://leetcode.cn/problems/ba-shu-zi-fan-yi-cheng-zi-fu-chuan-lcof/)
dp很快AC，超100%。用了to_string。

#### [剑指 Offer 47. 礼物的最大价值](https://leetcode.cn/problems/li-wu-de-zui-da-jie-zhi-lcof/)
简单二维DP。

#### [剑指 Offer 48. 最长不含重复字符的子字符串](https://leetcode.cn/problems/zui-chang-bu-han-zhong-fu-zi-fu-de-zi-zi-fu-chuan-lcof/)
滑动窗口，双指针。

#### [剑指 Offer 49. 丑数](https://leetcode.cn/problems/chou-shu-lcof/)
一开始采用了i++,(i%2\==0&&nums[i/2])||(i%3\==0&&nums[i/3])...的方式去判断丑数，超时了。正确的思路为直接递推出下一个丑数。
可以预见的是，一个丑数一定是之前的某个pa\*2，或pb\*3，或pc\*5。所以代码如下，可以直接递推出下一个丑数：
```cpp
int n2 = dp[a] * 2, n3 = dp[b] * 3, n5 = dp[c] * 5;
	dp[i] = min(min(n2, n3), n5);
	if(dp[i] == n2) a++;
	if(dp[i] == n3) b++;
	if(dp[i] == n5) c++;
```

#### [剑指 Offer 51. 数组中的逆序对](https://leetcode.cn/problems/shu-zu-zhong-de-ni-xu-dui-lcof/)
首先可以想出一种无需额外空间的方式。从头开始，进行插入排序，让前半部分保持有序。遍历到i时，可以直接通过二分查找查到前面有多少比当前大的元素，增加逆序数并插入到前半部分。重复此过程。每次折半查找的复杂度为logN，但进行元素移动则需要n的复杂度，最后的复杂度还是n^2.
标答为通过归并排序的方式统计逆序数。归并两个部分part1与part2，首先这两部分都是有序的，且part2的所有元素位置都在part1之后。设定两个指针i,j指向两个part的头部，若i元素大于j元素，则j往后都是逆序，j++；若i元素小于j，无逆序，i++。
很巧妙哇！

#### [剑指 Offer 52. 两个链表的第一个公共节点](https://leetcode.cn/problems/liang-ge-lian-biao-de-di-yi-ge-gong-gong-jie-dian-lcof/)
两个指针走到头时，从另一链表的头开始走。核心是`while (pA != pB)`退出循环，无论是有交点（pA不为null且相等）还是无交点（pA=pB=null）均可退出。

#### [剑指 Offer 53 - II. 0～n-1中缺失的数字](https://leetcode.cn/problems/que-shi-de-shu-zi-lcof/)
二分查找，返回left指针。简单题，但是下标的计算非常搞人！

#### [剑指 Offer 55 - I. 二叉树的深度](https://leetcode.cn/problems/er-cha-shu-de-shen-du-lcof/)
层序遍历可以轻松解决，但标答的三行代码非常优美，多学习一下。

#### [剑指 Offer 56 - I. 数组中数字出现的次数 - 力扣（LeetCode）](https://leetcode.cn/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-lcof/)
又是位运算啊！非常巧妙啊！
```cpp
	for (int n : nums)
		ret ^= n; //全部异或得到a^b
	
	int div = 1;  //找出a^b中不为0的第div位
	while ((div & ret) == 0)
		div <<= 1;
	//由于a,b的第div位一定不相等，故通过如下方式分组异或
	int a = 0, b = 0;
	for (int n : nums)
		if (div & n)
			a ^= n;
		else
			b ^= n;
	return vector<int>{a, b};
```

#### [剑指 Offer 56 - II. 数组中数字出现的次数 II](https://leetcode.cn/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-ii-lcof/)
解法1.没时间看是最优解，涉及到状态机等，有空看
解法2.map统计
解法3.一堆出现三次的数字，与一个出现一次的数字，统计每一位之和再%3，就是只出现一次的数字的对应位数的值。
```cpp
counts = [0] * 32
        for num in nums:
            for j in range(32):
                counts[j] += num & 1
                num >>= 1
        res, m = 0, 3
        for i in range(32):
            res <<= 1
            res |= counts[31 - i] % m
        return res if counts[31] % m == 0 else ~(res ^ 0xffffffff)   //~ 为取反

```

#### [剑指 Offer 57 - II. 和为s的连续正数序列 - 力扣（LeetCode）](https://leetcode.cn/problems/he-wei-sde-lian-xu-zheng-shu-xu-lie-lcof/?favorite=xb9nqhhg)
滑动窗口的经典题目。l、r为左右指针，l初始=1，r初始=2
1. sum\<target，则r++
2. sum\==target，则保存，并l++（因为一个l最多对应一个满足的序列）
3. sum\>target，则l++
4. 出口为l\<r

#### [面试题59 - II. 队列的最大值](https://leetcode.cn/problems/dui-lie-de-zui-da-zhi-lcof/)
这题很是有点难度。为了实现队列中的最大值，需要使用一个额外的deque来保存队列的最大值。
本算法基于问题的一个重要性质：当一个元素进入队列的时候，它前面所有比它小的元素就不会再对答案产生影响。
```cpp
class MaxQueue {
    queue<int> q; //正常存储队列
    deque<int> d; //存储队列中某个状态下的最大值
public:
    MaxQueue() {
    }
    
    int max_value() {
        if (d.empty())
            return -1;
        return d.front();
    }
    
    void push_back(int value) {
        while (!d.empty() && d.back() < value) {
            d.pop_back();
        }//弹出之前所有比自己小的元素，即实现递减
        d.push_back(value);//插入当前元素作为该状态的最大值
        q.push(value);//进入普通队列
    }
    
    int pop_front() {
        if (q.empty())
            return -1;
        int ans = q.front(); //从普通队列中弹出ans
        if (ans == d.front()) { //如果ans是此时的最大值
            d.pop_front(); //弹出这个值
        }
        q.pop(); //出队
        return ans;
    }
};

```


#### [剑指 Offer 60. n个骰子的点数](https://leetcode.cn/problems/nge-tou-zi-de-dian-shu-lcof/)
动态规划，逐行增加概率。注意vector的拷贝是深拷贝

#### [剑指 Offer 61. 扑克牌中的顺子](https://leetcode.cn/problems/bu-ke-pai-zhong-de-shun-zi-lcof/)
**简单**中带着几分**诡异**，不那么容易AC的一道题。
抽5张任意的牌，判断是不是顺子，0可以百搭。
遍历数组，遍历时跳过0。用一个set报错出现过的数字（除了0），**如果有重复的说明一定不能成为顺子**。如果没有重复，则**判断除0外的max与min的插值是否小于等于4**，若为真，则可以是顺子。

#### [剑指 Offer 64. 求1+2+…+n](https://leetcode.cn/problems/qiu-12n-lcof/)
```cpp
int sumNums(int n) { 
	n && (n += sumNums(n-1)); 
	return n; 
}
```


#### [剑指 Offer 65. 不用加减乘除做加法](https://leetcode.cn/problems/bu-yong-jia-jian-cheng-chu-zuo-jia-fa-lcof/)
标志是简单题啊，简单个鬼，感觉面试大概会喜欢出这种题。
在LeetCode下的C++环境中不支持负数的左移，在g++下可以左移
解法**非常巧妙**。
求a+b，
1. c = a&b<<1，求出所有的**进位**
2. a = a^b，求出所有丢弃进位的和
3. b=c， 继续进行循环
4. b\==0时跳出循环

#### [剑指 Offer 66. 构建乘积数组](https://leetcode.cn/problems/gou-jian-cheng-ji-shu-zu-lcof/)
AC。构建一个左侧乘积数组与右侧乘积数组，从而不用除法计算出乘积数组。空间复杂度O(n)。
更优方式为空间复杂度O(1)，倒序计算，左侧保留乘积数组，右侧保留计算结果。无需额外空间。


#### [剑指 Offer 68 - II. 二叉树的最近公共祖先](https://leetcode.cn/problems/er-cha-shu-de-zui-jin-gong-gong-zu-xian-lcof/)
`核心`
(lson && rson) || ((root->val == p->val || root->val == q->val) && (lson || rson))

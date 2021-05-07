## 万人等君上



https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/comments/155270



```java
终终终于提交成功了！！！！

总结： 历经四次失败，耗时4个小时左右。。。 虽然算法还是很垃圾，但是毕竟是自己一个字符一个字符打出来的。

通过这次算法，我感觉自己暴露出来了很多问题。

基础知识基本忘得一干二净，常用的api函数也记不清楚了
对数据结构一窍不通，对算法一窍不通。
考虑问题不够全面，急急忙忙得就开始写代码了，最后导致的结果就是。。填坑
今后的打算：

努力复习Java基础知识，记住常用的api函数
系统的学习数据结构和算法（看视频+看书）
每天一道算法题（LeetCode）
最后上代码

class Solution {
    public int lengthOfLongestSubstring(String s) {
       //如果s为空，length不大于0，是一个空串，就没有向下执行的必要了
        if(s != null && s.length() > 0 && s != ""){
            //String -> char[]
            char[] strChar = s.toCharArray();
            // 存储最长字串 key:char值，value:index下标
            ArrayList<String> maxStr = new ArrayList<>();
            //临时的字串存储空间
            ArrayList<String> tempStr = new ArrayList<>();
            //循环
            for(int i=0; i<strChar.length; i++){
                //char -> String
                String str = new String(new char[]{strChar[i]});
                //判断str是否存在于tempStr中
                if(tempStr.contains(str)){
                    //先判断tempStr的长度是否大于等于maxStr的长度,大于，才能将最长字串覆盖
                    if(tempStr.size() > maxStr.size()){
                        maxStr = new ArrayList<>(tempStr);
                    }
                    //存储重复字符
                    int reIndex = tempStr.indexOf(str);
                    // 删除tempStr中的重复字节及其之前的字符
                    for(int j=0;j<=reIndex;j++){
                        tempStr.remove(0);
                    }
                }
                //将当前字符存入tempStr中
                tempStr.add(str);
            }
            //最终判断
            if(tempStr.size() > maxStr.size()){
                maxStr = tempStr;
            }
            //返回最长字串的长度
            return maxStr.size();
        }
        return 0;
    }
}
```



![image-20210417004835224](https://i.loli.net/2021/04/17/m9jOoEcTyq26VH3.png)





![image-20210417005010185](https://i.loli.net/2021/04/17/LbeKtHYQWkITAry.png)









## woshishabi

https://leetcode-cn.com/problems/generate-parentheses/comments/729488



![image-20210506211756909](https://i.loli.net/2021/05/06/wBhtLTIKoeJ9fXd.png)





## 官方题解的代码复制粘贴还会报错？



为啥我直接把官方题解的代码复制粘贴还会报错？



https://leetcode-cn.com/problems/merge-k-sorted-lists/comments/747751











> 动态规划

1. 抽象数组，下标，求解值（求和值，最大值，最小值）
2. 抽象算法，func(数组，当前下标，求解值)
3. 找边界，当前递归的最终出路，不可能一直递归下去，需要有突破的地方
4. 暴力递归之后，需要抽象总结算法不足，重复计算等等，优化算法


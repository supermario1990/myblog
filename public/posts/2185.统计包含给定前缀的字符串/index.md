# 2185.统计包含给定前缀的字符串


题目描述:
```tex
给你一个字符串数组 words 和一个字符串 pref 。

返回 words 中以 pref 作为 前缀 的字符串的数目。

字符串 s 的 前缀 就是  s 的任一前导连续字符串。

 

示例 1：

输入：words = ["pay","attention","practice","attend"], pref = "at"
输出：2
解释：以 "at" 作为前缀的字符串有两个，分别是："attention" 和 "attend" 。
示例 2：

输入：words = ["leetcode","win","loops","success"], pref = "code"
输出：0
解释：不存在以 "code" 作为前缀的字符串。
```

分析：

题目非常简单。可以使用语言内置库函数，记不住库函数的话只能自己实现了。

解法一：使用语言内置库函数

```go
func prefixCount(words []string, pref string) int {
    cnt := 0
    for _, v := range words{
        if strings.HasPrefix(v, pref){
            cnt++
        }
    }
    return cnt
}
```

解法二：自己实现函数

```go
func prefixCount(words []string, pref string) int {
    cnt := 0
    for _, v := range words{
        if hasPrefix(v, pref){
            cnt++
        }
    }
    return cnt
}

// hasPrefix 判断str是否有前缀prefix
func hasPrefix(str, prefix string) bool{
  	// 如果前缀比字符串本身还长，肯定是false
    if len(prefix) > len(str) {
        return false
    }else{
        for i := 0; i < len(prefix); i++{
            if str[i] != prefix[i] {
                return false
            }
        }
    }
    return true
}
```

TODO：

重新复习下go语言中和字符串操作相关的库`strings`

链接：

1. [2185. 统计包含给定前缀的字符串](https://leetcode.cn/problems/counting-words-with-a-given-prefix/)


---

> 作者:   
> URL: https://super_mario.gitee.io/posts/2185.%E7%BB%9F%E8%AE%A1%E5%8C%85%E5%90%AB%E7%BB%99%E5%AE%9A%E5%89%8D%E7%BC%80%E7%9A%84%E5%AD%97%E7%AC%A6%E4%B8%B2/  


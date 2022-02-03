# 1. 题目
剑指 Offer 58 - II. 左旋转字符串
字符串的左旋转操作是把字符串前面的若干个字符转移到字符串的尾部。请定义一个函数实现字符串左旋转操作的功能。比如，输入字符串"abcdefg"和数字2，该函数将返回左旋转两位得到的结果"cdefgab"。

 

示例 1：

输入: s = "abcdefg", k = 2
输出: "cdefgab"
示例 2：

输入: s = "lrloseumgh", k = 6
输出: "umghlrlose"
# 2. 题解
具体步骤为：

反转区间为前n的子串
反转区间为n到末尾的子串
反转整个字符串
# 3. 代码
额外内存空间很好写
```c++
class Solution {
public:
    string reverseLeftWords(string s, int n) {
        string ans = s;
        for(int i = 0; i < s.size(); i++) {
            if(i < n) {
                ans[s.size() - n + i] = s[i];
            } else {
                ans[i - n] = s[i];
            }
        }
        return ans;
    }
};
```
贪吃蛇
```c++
class Solution {
public:
    string reverseLeftWords(string s, int n) {
        for(int k = n; k > 0; k--) {
            int tmp = s[0];
            for(int i = 1; i < s.size(); i++) {
                s[i-1] = s[i];
            }
            s[s.size()-1] = tmp;
        }
        return s;
    }
};
```
Carl:
```c++
class Solution {
public:
    string reverseLeftWords(string s, int n) {
        reverse(s.begin(), s.begin() + n);
        reverse(s.begin() + n, s.end());
        reverse(s.begin(), s.end());
        return s;
    }
};
```
# 4. 心得
反转局部，反转整体

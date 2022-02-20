# 1.题目
剑指 Offer 05. 替换空格
请实现一个函数，把字符串 s 中的每个空格替换成"%20"。

 

示例 1：

输入：s = "We are happy."
输出："We%20are%20happy."
# 2.题解
这题不是一个循环就好了吗？
**其实很多数组填充类的问题，都可以先预先给数组扩容到填充后的大小，然后在从后向前进行操作。**
1. 将数组扩充；
2. 从后向前填充元素，避免了从前先后填充元素要来的 每次添加元素都要将添加元素之后的所有元素向后移动。
# 3.代码
```c++
class Solution {
public:
    string replaceSpace(string s) {
        int count = 0;
        for(char ss: s) {
            if(ss == ' ') {
                count++;
            }
        }
        int oldSize = s.size() - 1;
        s.resize(s.size() + count*2);
        int newSize = s.size() - 1;
        for(int i = oldSize, j = newSize; i >= 0, j >= 0; i--, j--) {
            if(s[i] != ' ') {
                s[j] = s[i];
            } else {
                s[j] = '0';
                s[j - 1] = '2';
                s[j - 2] = '%';
                j -= 2;
            }
        }
        return s;
    }
};

```
# 4.心得

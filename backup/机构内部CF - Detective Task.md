**题目**

C. Detective Task

time limit per test: 2 seconds

memory limit per test: 256 megabytes

input: standard input

output: standard output

Polycarp bought a new expensive painting and decided to show it to his $n$ friends. He hung it in his room. $n$ of his friends entered and exited there one by one. At one moment there was no more than one person in the room. In other words, the first friend entered and left first, then the second, and so on.

It is known that at the beginning (before visiting friends) a picture hung in the room. At the end (after the $n$\-th friend) it turned out that it disappeared. At what exact moment it disappeared — there is no information.

Polycarp asked his friends one by one. He asked each one if there was a picture when he entered the room. Each friend answered one of three:

-   no (response encoded with 0);
-   yes (response encoded as 1);
-   can't remember (response is encoded with ?).

Everyone except the thief either doesn't remember or told the **truth**. The thief can say anything (any of the three options).

Polycarp cannot understand who the thief is. He asks you to find out the number of those who can be considered a thief according to the answers.

**Input**

The first number $t$ ($1 \le t \le 10^4$) — the number of test cases in the test.

The following is a description of test cases.

The first line of each test case contains one string $s$ (length does not exceed $2 \cdot 10^5$) — a description of the friends' answers, where $s_i$ indicates the answer of the $i$\-th friend. Each character in the string is either 0 or 1 or ?.

The given regularity is described in the actual situation. In particular, on the basis of answers, at least one friend can be suspected of stealing a painting.

It is guaranteed that the sum of string lengths over the entire input data set does not exceed $2 \cdot 10^5$.

**Output**

Output one positive (strictly more zero) number – the number of people who could steal the picture based on the data shown.

**DeepL翻译**

波利卡普买了一幅昂贵的新画，决定把它展示给他的 $n$ 朋友们看。他把画挂在自己的房间里。他的 $n$ 朋友们一个接一个地进进出出。有一次，房间里只剩下一个人。换句话说，第一个朋友先进出，然后是第二个，以此类推。

众所周知，在开始时（拜访朋友之前），房间里挂着一幅画。到最后（在 $n$ /那位朋友之后），它却消失了。具体是什么时候消失的--没有任何信息。

波利卡普一个一个地问他的朋友们。他问每个人，当他进入房间时，是否有一幅画。每个朋友都回答了三个问题中的一个：

- 没有（回答编码为 0）
- 有（回答编码为 1）
- 不记得了（回答用"...... "编码）。

除小偷外，其他人要么不记得，要么说的都是**事实。小偷可以说任何事情（三个选项中的任何一个）。

波利卡普不知道小偷是谁。他让你根据答案找出可以被视为小偷的人数。

**输入**

第一个数字 $t$ ( $1 \le t \le 10^4$ ) - 测试中的测试用例数。

下面是测试用例的说明。

每个测试用例的第一行包含一个字符串 $s$ （长度不超过 $2 \cdot 10^5$ ）--对好友答案的描述，其中 $s_i$ 表示 $i$ /-个好友的答案。字符串中的每个字符要么是 0，要么是 1，要么是 ?

给定的规律性是在实际情况中描述的。特别是，根据答案，至少可以怀疑一位朋友偷了一幅画。

保证整个输入数据集的字符串长度之和不超过 $2 \cdot 10^5$ 。

**输出**

输出一个正数（严格来说更多的是零）--根据所示数据可能偷到图片的人数。

**样例**
**输入：**
```
8
0
1
1110000
?????
1?1??0?0
0?0???
??11
??0??
```
**输出:**
```
1
1
2
5
4
1
1
3
```

**个人总结**
把玩下样例总结规律，然后实现即可


**满分代码**

```
#include <bits/stdc++.h>

using namespace std;

int main() {
    int n;
    cin >> n;
    while(n--){
        string s;
        cin >> s;
        int n = s.size();
        int pos1 = 0, pos2 = n-1;
        for (int i = 0; i < n; i++){
            if (s[i] == '1'){
                pos1 = i;
            }
        } //找最后一个1
        for (int i = pos1; i < n; i++){
            if (s[i] == '0'){
                pos2 = i;
                break;
            }
        }//找对后一个0
        cout << pos2-pos1+1 << endl;
    }
    
    return 0;
}
```
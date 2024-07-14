**题目**

A. Food for Animals

time limit per test: 1 second

memory limit per test: 256 megabytes

input: standard input

output: standard output

In the pet store on sale there are:

-   $a$ packs of dog food;
-   $b$ packs of cat food;
-   $c$ packs of universal food (such food is suitable for both dogs and cats).

Polycarp has $x$ dogs and $y$ cats. Is it possible that he will be able to buy food for all his animals in the store? Each of his dogs and each of his cats should receive one pack of suitable food for it.

**Input**

The first line of input contains an integer $t$ ($1 \le t \le 10^4$) — the number of test cases in the input.

Then $t$ lines are given, each containing a description of one test case. Each description consists of five integers $a, b, c, x$ and $y$ ($0 \le a,b,c,x,y \le 10^8$).

**Output**

For each test case in a separate line, output:

-   YES, if suitable food can be bought for each of $x$ dogs and for each of $y$ cats;
-   NO else.

You can output YES and NO in any case (for example, strings yEs, yes, Yes and YES will be recognized as a positive response).

**DeepL翻译**

宠物店里有

- $a$ 包狗粮；
- $b$ 包猫粮；
- $c$ 包通用食品（这种食品既适合狗也适合猫）。

波利卡普养了 $x$ 只狗和 $y$ 只猫。他有可能在商店里买到所有动物的食物吗？他的每只狗和每只猫都应该得到一包合适的食物。

**输入**

第一行输入包含一个整数 $t$ （ $1 \le t \le 10^4$ ）。( $1 \le t \le 10^4$ )--输入中的测试用例数。

然后是 $t$ 行，每行包含一个测试用例的描述。每个描述由五个整数 $a, b, c, x$ 和 $y$ （ $0 \le a,b,c,x,y \le 10^8$ ）组成。

**输出**

对每个测试用例单独一行输出：

- 如果可以为 $x$ 条狗和 $y$ 只猫购买合适的食物，则 "是"；
- 否，否则。

您可以在任何情况下输出 "是 "和 "否"（例如，字符串 yEs、yes、Yes 和 YES 将被视为肯定回答）。

**个人总结**
纯纯水题


**满分代码**

```
#include <bits/stdc++.h>

using namespace std;

int main() {
    int n;
    cin>>n;
    while(n--){
        int a,b,c,x,y;
        cin>>a>>b>>c>>x>>y;
        int need=0;
        need+=max(0,x-a);
        need+=max(0,y-b);
        if (need>c){
            cout<<"NO\n";
        } else {
            cout<<"YES\n";
        }
    }
}
```
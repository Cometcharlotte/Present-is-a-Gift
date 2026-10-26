# 《高级语言程序设计(C++语言)》实验报告

| 项目 | 内容 | 项目 | 内容 |
| :--- | :--- | :--- | :--- |
| **实验名称** | 第一次上机课实验 | **实验日期** | 2026年10月23日 |
| **实验地点** | 于刚宋晓楼A237 | **学号** | 2026302192042
| **专业** | 人工智能专业 | **指导老师** | 胡黔楠 |

---

## 一、实验目的
1. 掌握 C++ 的基本语法
2. 熟悉C++的分支，循环等基本语法

## 二、实验环境
- **操作系统**：Windows 11
- **开发工具**：Visual Studio Code
- **编程语言**：C++

## 三、实验过程及结果

### 题目1：企业奖金提成计算

**解答：代码**
```cpp
 #include <iostream>
using namespace std;

int main() {
    double I;
    cout << "请输入当月利润(万元): ";
    cin >> I;

    double bonus = 0;
    if (I <= 10) {
        bonus = I * 0.10;
    } else if (I <= 20) {
        bonus = 10 * 0.10 + (I - 10) * 0.075;
    } else if (I <= 40) {
        bonus = 10 * 0.10 + 10 * 0.075 + (I - 20) * 0.05;
    } else if (I <= 60) {
        bonus = 10 * 0.10 + 10 * 0.075 + 20 * 0.05 + (I - 40) * 0.03;
    } else if (I <= 100) {
        bonus = 10 * 0.10 + 10 * 0.075 + 20 * 0.05 + 20 * 0.03 + (I - 60) * 0.015;
    } else {
        bonus = 10 * 0.10 + 10 * 0.075 + 20 * 0.05 + 20 * 0.03 + 40 * 0.015 + (I - 100) * 0.01;
    }

    cout << "应发放奖金总数: " << bonus << " 万元" << endl;
    return 0;
}
```



![题目1运行结果]()

### 题目2：电影打分评语

**解答：代码**
```cpp
#include <iostream>
using namespace std;

int main() {
    int score;
    cout << "请输入电影评分(0-10): ";
    cin >> score;

    if (score >= 9 && score <= 10)
        cout << "你认为电影经典" << endl;
    else if (score >= 7)
        cout << "你认为电影非常好" << endl;
    else if (score >= 5)
        cout << "你认为电影一般" << endl;
    else
        cout << "你认为电影烂片" << endl;

    return 0;
}
```
![题目2运行结果]()

### 题目3：判断回文数

**解答：代码**
```cpp
#include<iostream>
int main(){
    int a;
    std::cin>>a;
    if(a<0){
        std::cout<<"不是回文数"<<std::endl;
    }
    int b=a;
    int c=0;
    while(a>0){
        int d=a%10;
        c=c*10+d;
        a=a/10;
    }
    if(b==c){
        std::cout<<"是回文数"<<std::endl;
    } else{
        std::cout<<"不是回文数"<<std::endl;
    }
    return 0;
}


![题目3运行结果]()

### 题目4：三位水仙花数

**解答：代码**
```cpp
#include <iostream>
using namespace std;

int main() {
    cout << "所有三位水仙花数: ";
    for (int n = 100; n <= 999; n++) {
        int a = n / 100;        // 百位
        int b = n / 10 % 10;    // 十位
        int c = n % 10;         // 个位
        if (a*a*a + b*b*b + c*c*c == n)
            cout << n << " ";
    }
    cout << endl;
    return 0;
}
```

若需判断某个输入的三位数，可加：

```cpp
int n; cin >> n;
int a=n/100, b=n/10%10, c=n%10;
if (a*a*a+b*b*b+c*c*c==n) cout<<"是水仙花数"; else cout<<"不是";
```

---


![题目4运行结果]()

### 题目5：数列 a, aa, aaa... 求和

**解答：代码**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, a;
    cout << "请输入 n 和 a: ";
    cin >> n >> a;

    long long term = 0, sum = 0;
    for (int i = 0; i < n; i++) {
        term = term * 10 + a;   // 构造 a, aa, aaa...
        sum += term;
    }

    cout << "数列和为: " << sum << endl;
    return 0;
}
```



![题目5运行结果]()

### 题目6：乘法口诀表

**解答：代码**
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 9; i++) {
        for (int j = 1; j <= i; j++) {
            cout << j << "*" << i << "=" << i * j << "\t";
        }
        cout << endl;
    }
    return 0;
}
```



![题目6运行结果]()
### 题目7：兔子数量

**解答：代码**
```cpp
#include <iostream>
using namespace std;

int main() {
    long long f1 = 1, f2 = 1, f;
    cout << "第1个月: 1 对" << endl;
    cout << "第2个月: 1 对" << endl;
    for (int i = 3; i <= 20; i++) {
        f = f1 + f2;
        cout << "第" << i << "个月: " << f << " 对" << endl;
        f1 = f2;
        f2 = f;
    }
    return 0;
}
```

![题目7运行结果]()

### 题目8：猴子吃桃

**解答：代码**
```cpp
#include <iostream>
using namespace std;

int main() {
    int peach = 1;  // 第10天剩下1个
    for (int day = 9; day >= 1; day--) {
        peach = (peach + 1) * 2;
    }
    cout << "第一天共摘了 " << peach << " 个桃子" << endl;
    return 0;
}
```
![题目8运行结果]()

实验总结：

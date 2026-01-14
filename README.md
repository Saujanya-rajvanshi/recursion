# recursion

## INDEX 
- [basic](#basic)
- [relevant questions](#important-questions)
- [striver questions](#striver-questions)


##### basic
---

## Definition

**Recursion** is a technique where a function **calls itself** to solve a problem by breaking it into **smaller subproblems** until a **base case** is reached.

---

## 🧩 Key components
1. **Base case** → stops recursion
2. **Recursive case** → function calls itself
3. **Smaller input** → moves toward base case

* Without a base case → **infinite recursion** 

---

## 🔧 General form
```cpp
return_type function(parameters) {
    if (base_condition)
        return value;
    return function(smaller_input);
}
```

## 🔄 Types of recursion

1. **Direct recursion**
   Function calls itself directly
2. **Indirect recursion**
   Function A → Function B → Function A
3. **Tail recursion**
   Recursive call is the **last statement**
4. **Non-tail recursion**
   Work remains after recursive call

---

### important questions
---

---


---


### striver questions 
- [print endless number one](#print-endless--number-one)
- [print number upto some point](print-number-upto-some-point)
- [print name times](#print-name-times)
- [sum of first n numbers](#sum-of-first-n-numbers)
- [reverse an array](#reverse-an-array)
- [check palindrom](#check-palindrom)
- [fibonaci series](#fibonaci-series)



###### print endless number one
```cpp
#include<bits/stdc++.h>
using namespace std;

void print() {
cout << 1 << endl;
print();
}

int main() {
#ifndef ONLINE_JUDGE
freopen("input.txt", "r", stdin);
freopen("output.txt", "w", stdout);
#endif

print();

return 0;
}
```
###### print number upto some point
```cpp
#include<bits/stdc++.h>
using namespace std;
int cnt = 0;
void print() {
if(cnt == 3) return;
cout << cnt << endl;
cnt++;
print();
}


int main() {
#ifndef ONLINE_JUDGE
freopen("input.txt", "r", stdin);
freopen("output.txt", "w", stdout);
#endif

print();

return 0;
}
```
###### print name times 
```cpp
#include <bits/stdc++.h>
using namespace std;

void f(int i, int n) {
    if (i > n)   // base condition
        return;

    cout << "Saujanya" << endl;   // print your name
    f(i + 1, n);                  // recursive call
}

int main() {
    int n;
    cin >> n;

    f(1, n);
    return 0;
}
```

###### sum of first n numbers
```cpp
\\paramaterised way
#include <bits/stdc++.h>
using namespace std;

void f(int i, int sum) {
    if (i < 1) {           // base condition
        cout << sum;      // print final sum
        return;
    }

    f(i - 1, sum + i);     // recursive call
}

int main() {
    int n;
    cin >> n;              // example: n = 3

    f(n, 0);               // start with sum = 0
    return 0;
}
```
```cpp
\\functional way
#include <bits/stdc++.h>
using namespace std;

int f(int n) {
    if (n == 0)           // base condition
        return 0;

    return n + f(n - 1);  // functional recursion
}

int main() {
    int n;
    cin >> n;             // example: 3

    cout << f(n);
    return 0;
}
```

###### reverse an array
```cpp
#include <bits/stdc++.h>
using namespace std;

void f(int l, int r, vector<int> &a) {
    if (l >= r)      // base condition
        return;

    swap(a[l], a[r]);    // swap left and right

    f(l + 1, r - 1, a);  // recursive call
}

int main() {
    int n;
    cin >> n;

    vector<int> a(n);
    for (int i = 0; i < n; i++)
        cin >> a[i];

    f(0, n - 1, a);      // call function to reverse

    for (int i = 0; i < n; i++)
        cout << a[i] << " ";

    return 0;
}
```
###### check palindrom
```cpp
#include <bits/stdc++.h>
using namespace std;

bool f(int i, string &s) {
    int n = s.size();

    if (i >= n / 2)      // base condition
        return true;

    if (s[i] != s[n - i - 1])
        return false;

    return f(i + 1, s);  // recursive call
}

int main() {
    string s;
    cin >> s;

    if (f(0, s))
        cout << "Palindrome";
    else
        cout << "Not Palindrome";

    return 0;
}
```
###### fibonaci series
```cpp
#include <bits/stdc++.h>
using namespace std;

int fib(int n) {
    if (n <= 1) return n;
    return fib(n - 1) + fib(n - 2);
}

int main() {
    int n;
    cin >> n;   // number of terms

    for (int i = 0; i < n; i++)
        cout << fib(i) << " ";

    return 0;
}
```

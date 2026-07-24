# 📒 **STL NOTES**

---

## 🔹 VECTOR

```cpp
vector<int> v;

v.push_back(x);
v.emplace_back(x);

v.pop_back();
v.size();
v.empty();
v.clear();

v.insert(v.begin()+i, x);
v.erase(v.begin()+i);

sort(v.begin(), v.end());
reverse(v.begin(), v.end());
```

Access:

```cpp
v[i]
v.front()
v.back()
```

Traversal:

```cpp
for(int x : v) {}
for(auto x : v) {}
for(int i=0;i<v.size();i++) {}
```

---

## 🔹 PAIR

```cpp
pair<int,int> p = {a,b};

p.first
p.second

auto p = make_pair(a,b);
```

---

## 🔹 MAP vs UNORDERED_MAP

```cpp
map<int,int> mp;              // O(log n)
unordered_map<int,int> ump;   // O(1) average
```

Common Operations

```cpp
mp[key]++;
mp[key] = value;

mp.find(key);
mp.count(key);

mp.erase(key);
```

Rules

- `unordered_map` → Frequency counting
- `map` → Sorted keys

---

## 🔹 SET vs UNORDERED_SET

```cpp
set<int> s;
unordered_set<int> us;
```

```cpp
s.insert(x);
s.emplace(x);

s.erase(x);

s.find(x);
s.count(x);
```

Properties

- Stores unique elements
- `set` keeps sorted order
- `unordered_set` has no order

---

## 🔹 STACK

```cpp
stack<int> st;

st.push(x);
st.emplace(x);

st.pop();

st.top();

st.empty();
st.size();

st.swap(st2);
```

⚠️ Never call `top()` on an empty stack.

---

## 🔹 QUEUE

```cpp
queue<int> q;

q.push(x);
q.emplace(x);

q.pop();

q.front();
q.back();

q.empty();
q.size();
```

---

## 🔹 DEQUE

```cpp
deque<int> dq;

dq.push_front(x);
dq.push_back(x);

dq.pop_front();
dq.pop_back();

dq.front();
dq.back();

dq[i];
```

---

## 🔹 PRIORITY_QUEUE (HEAP)

Max Heap

```cpp
priority_queue<int> pq;
```

Min Heap

```cpp
priority_queue<int, vector<int>, greater<int>> pq;
```

Functions

```cpp
pq.push(x);
pq.emplace(x);

pq.pop();

pq.top();

pq.empty();
pq.size();
```

---

## 🔹 LIST (DOUBLY LINKED LIST)

```cpp
list<int> ls;

ls.push_front(x);
ls.push_back(x);

ls.pop_front();
ls.pop_back();

ls.insert(it,x);
ls.erase(it);
```

---

## 🔹 SORTING

Ascending

```cpp
sort(v.begin(), v.end());
```

Descending

```cpp
sort(v.begin(), v.end(), greater<int>());
```

Custom Comparator

```cpp
sort(v.begin(), v.end(), [](int a,int b){
    return a>b;
});
```

---

## 🔹 BINARY SEARCH HELPERS

```cpp
binary_search(v.begin(), v.end(), x);

lower_bound(v.begin(), v.end(), x);

upper_bound(v.begin(), v.end(), x);
```

---

## 🔹 ITERATORS

```cpp
auto it = v.begin();

auto it = s.begin();

auto it = mp.begin();
```

---

## 🔹 USEFUL ALGORITHMS

Reverse

```cpp
reverse(v.begin(), v.end());
```

Minimum

```cpp
*min_element(v.begin(), v.end());
```

Maximum

```cpp
*max_element(v.begin(), v.end());
```

Count

```cpp
count(v.begin(), v.end(), x);
```

Find

```cpp
find(v.begin(), v.end(), x);
```

Sum

```cpp
accumulate(v.begin(), v.end(), 0);
```

---

## 🔹 BIT FUNCTIONS

Number of set bits

```cpp
__builtin_popcount(x);
```

For long long

```cpp
__builtin_popcountll(x);
```

---

## 🔹 NEXT PERMUTATION

```cpp
next_permutation(v.begin(), v.end());
```

Example

```cpp
do{

}while(next_permutation(v.begin(),v.end()));
```

---

## 🔹 IMPORTANT STL RULES

- Prefer `vector` over arrays.
- Use `emplace()`/`emplace_back()` when possible.
- Use `long long` for large sums.
- Check `empty()` before accessing elements.
- Clear containers between test cases.
- STL algorithms are highly optimized.

---

## 🔹 COMMON STL MISTAKES

- Using `map` instead of `unordered_map` → TLE
- Forgetting `greater<int>` for min heap
- Calling `top()` on empty stack
- Calling `front()` on empty queue
- Using `int` where `long long` is needed
- Forgetting `clear()` in multiple test cases
- Applying `lower_bound()` on an unsorted container

---

## 🔹 STL HEADER

```cpp
#include<bits/stdc++.h>
using namespace std;
```

---

## 🔹 WHEN TO USE WHAT (VERY IMPORTANT)

| Situation                        | STL              |
| -------------------------------- | ---------------- |
| Dynamic array                    | `vector`         |
| Frequency counting               | `unordered_map`  |
| Sorted key-value pairs           | `map`            |
| Unique sorted values             | `set`            |
| Unique fast lookup               | `unordered_set`  |
| LIFO                             | `stack`          |
| FIFO / BFS                       | `queue`          |
| Push/pop from both ends          | `deque`          |
| Always need max/min              | `priority_queue` |
| Frequent insert/delete in middle | `list`           |
| Pair two values                  | `pair`           |
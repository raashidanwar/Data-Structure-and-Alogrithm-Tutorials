## Stack
It's a type of data structure which follows **LIFO** (last in first out) rule.

In c++ we already have an inbuild stack library as part of [STL](https://en.wikipedia.org/wiki/Standard_Template_Library)(standard template library) however we can write our own if we want.

First we need to include the library in our programe file and we can do that either by including `#include <stack>` or `#inlcude <bits/stdc++.h>` (it contains pretty much all the standard libraries).

stack <**data_type**> (**data_type** can be any valid data type like `int`, `float` etc... or any custome made data type also).

**Note*** unlike `vector` or `array` we cannot access elements in the stack except the top element.

### supported methods
#### push
Push method inserts the element at the top of the stack.
```cpp
stack <int> st;
st.push(2);
st.push(3);
st.push(10);
```
**Note*** `emplace is an alternative of push (example st.emplace(element);)`



https://user-images.githubusercontent.com/35250507/177518425-5bc0306f-1171-4dde-91c5-de1ce4fb563f.mp4


#### pop
Pop method removes the top element or throw error is stack is empty.
```cpp
st.pop();
```


https://user-images.githubusercontent.com/35250507/177525018-dec38290-18b9-4310-9f51-0a5acacfedd5.mp4

#### top
Top method returns the top element of the stack or throw error is stack is empty.
```cpp
st.top();
```

#### size
Size method returns size of the stack.
```cpp
st.size();
```

#### empty
Empty method returns boolean (**true** if stack is empty otherwise **false**).
```
st.empty();
```

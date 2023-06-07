## Queue

It's a type of data structure which follows **FIFO** (first in first out) rule.

In c++ we already have an inbuild queue library as part of [STL](https://en.wikipedia.org/wiki/Standard_Template_Library)(standard template library) however we can write our own if we want.

First we need to include the library in our programe file and we can do that either by including `#include <queue>` or `#inlcude <bits/stdc++.h>` (it contains pretty much all the standard libraries).

queue <**data_type**> (**data_type** can be any valid data type like `int`, `float` etc... or any custome made data type also).

**Note*** unlike `vector` or `array` we cannot access elements in the queue except the front and back element.

### supported methods
#### push
Push method inserts the element at the back of the queue.
```cpp
queue <int> q;
q.push(2);
q.push(3);
q.push(10);
```
**Note*** `emplace is an alternative of push (example q.emplace(element);)`


https://user-images.githubusercontent.com/35250507/178089665-96b31800-865e-453e-9060-4180a1c00901.mp4

#### pop
Pop method removes the front element or throw error is queue is empty.
```cpp
q.pop();
```


https://user-images.githubusercontent.com/35250507/178089752-6d41e53a-6712-4b29-8a75-5b6786f87464.mp4
#### front
Front method returns the front element of the queue or throw error is queue is empty.
```cpp
q.front();
```

#### back
Back method returns the back element of the queue or throw error is queue is empty.
```cpp
q.back();
```

#### size
Size method returns size of the queue.
```cpp
q.size();
```

#### empty
Empty method returns boolean (**true** if queue is empty otherwise **false**).
```cpp
q.empty();
```

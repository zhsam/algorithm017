# 算法训练营第一周学习笔记
- [提交链接](https://github.com/algorithm017/algorithm017/issues/2)

### 第3课: 数组、链表、跳表
- 范型：不同的类型，都能存进数组中

- 数组 (Array)
    - 时间复杂度:
        - 增加元素: O(n), 最快O(1) -- 最前面/最后面增加元素
        - 删除元素: O(n)
        - 查询元素: O(1)
- 链表 (Linked List)
    - 几种链表: 单链表(只有一个next指针)、双向链表(有next指针，也有prev指针)、循环链表(尾指针，指向head)
    - 名次定义: 头(head)、尾(tail)
    - 时间复杂度:
        - 增加元素: O(1)
        - 删除元素: O(1)
        - 访问任意位置: O(n)
- 跳表 (Skip List)
    - 特点: 只能用于元素有序的情况.
    - 时间复杂度:
        - 查询元素: O(logn) -- 将链表的O(n)优化到O(logn)，通过n级的捷径


### 第4课: 栈、队列、优先队列、双端队列

- 栈 Stack
    - FILO 先进后出
    - 添加、删除皆为O(1)
    - 查询： O(n)，因为是无序的

- 队列 Queue
    - LIFO，后进先出
    - 添加、删除皆为
    - 查询： O(n)，因为是无序的

- 双端队列 Deque: Double-End Queue
    - 添加、删除皆为O(1)
    - 查询： O(n)，因为是无序的

- Demo
    - **受之以鱼，不如受之以渔**
    - Stack
        - Google: 
            - `latest java version`
            - `stack java 12`
        - 工程中，推荐直接使用`deque`
        - API:
            - `empyty()`: 检查是否为空
            - `peek()`
            - `pop()`
            - `push()`
    - Queue
        - 不是Class，而是Interface
        - API:
            - `add()`: 会抛出异常
            - `remove()`: 会抛出异常
            - `offer()`: 特殊返回值
            - `poll()`: 特殊返回值
    - Deque
        - 不是Class，而是Interface
        - API:
            - `addFirst()`
            - `removeFirst()`
            - `oferFirst()`
            - `pollFirst()`
            - 双端队列，可以对首或者尾进行操作

- 优先队列 Priority Queue
    - 插入: O(1)
    - 取出: O(logN) -- 按照元素优先级取出（VIP先行）
    - 底层实现较为复杂、多样, 可以使用 heap, bst, treap
    - API:
        - `clear()`
        - `add()`
        - `offer()`
        - `comparator()`

- 实现代码
    - `java source code download`
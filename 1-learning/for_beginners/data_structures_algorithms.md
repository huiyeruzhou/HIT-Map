# 数据结构与算法

我首先推荐《算法导论》，可以阅读其中开头的算法复杂性、排序算法的内容，然后阅读栈、队列、链表、图、二叉树中的内容，并实现其中的算法。
之后，可以开始阅读清华大学出版社的紫书《数据结构与算法》（考研教材），学习kmp算法，散列表，b+树，红黑树等。

我推荐实现：

```c
// 排序算法
void bubble_sort(int a[], int n);
void insert_sort(int a[], int n);
void select_sort(int a[], int n);
void merge_sort(int a[], int begin1, int begin2, int n);
void quick_sort(int a[], int begin, int end);

//数组栈
typedef struct stack {
    int capacity; // 栈的容量
    int end;      // 栈顶索引
    int *s;       // 栈的数组
} stack;
stack* init(int capacity); // 初始化栈，返回栈的指针
void deinit(stack* s); // 释放栈的内存
void push(stack *s, int a); // 将元素压入栈
int top(stack *s); // 获取栈顶元素
int pop(stack *s); // 弹出栈顶元素
void expand(stack *s); // 扩容栈的容量

//数组循环队列
typedef struct queue {
    int capacity; // 队列的容量
    int front; // 队列的前端索引
    int rear; // 队列的后端索引
    int size; // 队列的当前大小
    int *q; // 队列的数组
} queue;

queue* init(int capacity); // 初始化队列，返回队列的指针
int deinit(queue* q); // 释放队列的内存
int enqueue(queue *q, int a); // 将元素加入队列
int dequeue(queue *q); // 移除队列前端元素
int front(queue *q); // 获取队列前端元素
void expand(queue *q); // 扩容队列的容量

//单链表
typedef struct node {
    int data; // 节点数据
    struct node* next; // 指向下一个节点的指针
} node;

//双向链表
typedef struct dnode {
    int data; // 节点数据
    struct dnode* prev; // 指向前一个节点的指针
    struct dnode* next; // 指向下一个节点的指针
} dnode;

//二叉树，最小堆
typedef struct tnode {
    int data; // 节点数据
    struct dnode* lchild; // 指向左孩子的指针
    struct dnode* rchild; // 指向右孩子的指针
} tnode;
//堆排序
void heap_sort(int a[], int n);

// 图的邻接链表节点
typedef struct adj_list_node {
    int dest; // 目标顶点
    struct adj_list_node* next; // 指向下一个邻接链表节点的指针
} adj_list_node;

// 图的邻接链表
typedef struct adj_list {
    adj_list_node* head; // 指向邻接链表头的指针
} adj_list;

// 图结构
typedef struct graph {
    int vertices; // 顶点数
    adj_list* array; // 邻接链表数组
} graph;

graph* init_graph(int cnt_v);
void directed_edge(int from, int to);
void undirected_edge(int between, int and);
void BFS(graph *g, int start);
void DFS(graph *g, int start);
int shortest_path(graph* g, int src, int dest);
```

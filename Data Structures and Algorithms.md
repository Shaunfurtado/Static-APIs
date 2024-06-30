# C++ Data Structures and Algorithms Cheat Sheet

## Table of Contents

- [C++ Data Structures and Algorithms Cheat Sheet](#c-data-structures-and-algorithms-cheat-sheet)
	- [Table of Contents](#table-of-contents)
	- [1.0 Data Structures](#10-data-structures)
		- [1.1 Vector `std::vector`](#11-vector-stdvector)
		- [1.2 Deque `std::deque`](#12-deque-stddeque)
		- [1.3 List `std::list` and `std::forward_list`](#13-list-stdlist-and-stdforward_list)
		- [1.4 Map `std::map` and `std::unordered_map`](#14-map-stdmap-and-stdunordered_map)
		- [1.5 Set `std::set`](#15-set-stdset)
		- [1.6 Stack `std::stack`](#16-stack-stdstack)
		- [1.7 Queue `std::queue`](#17-queue-stdqueue)
		- [1.8 Priority Queue `std::priority_queue`](#18-priority-queue-stdpriority_queue)
		- [1.9 Heap `std::priority_queue`](#19-heap-stdpriority_queue)
	- [2.0 Trees](#20-trees)
		- [2.1 Binary Tree](#21-binary-tree)
		- [2.2 Balanced Trees](#22-balanced-trees)
		- [2.3 Binary Search](#23-binary-search)
		- [2.4 Depth-First Search](#24-depth-first-search)
		- [2.5 Breadth-First Search](#25-breadth-first-search)
	- [3.0 NP Complete Problems](#30-np-complete-problems)
		- [3.1 NP Complete](#31-np-complete)
		- [3.2 Traveling Salesman Problem](#32-traveling-salesman-problem)
		- [3.3 Knapsack Problem](#33-knapsack-problem)
	- [4.0 Algorithms](#40-algorithms)
		- [4.1 Insertion Sort](#41-insertion-sort)
		- [4.2 Selection Sort](#42-selection-sort)
		- [4.3 Bubble Sort](#43-bubble-sort)
		- [4.4 Merge Sort](#44-merge-sort)
		- [4.5 Quicksort](#45-quicksort)

## 1.0 Data Structures

### 1.1 Vector `std::vector`
**Use for:** Simple storage, quick lookups by index.

**Time Complexity:**
| Operation | Time Complexity |
|-----------|-----------------|
| Insert Head | O(n) |
| Insert Tail | O(1) |
| Access by Index | O(1) |
| Remove Head | O(n) |
| Remove Tail | O(1) |

**Example Code:**
```cpp
#include <vector>
#include <iostream>

using namespace std;

vector<int> v;
v.push_back(10); // Insert Tail
int head = v.front(); // Access Head
v.pop_back(); // Remove Tail

for(int x : v) cout << x << endl;
```

### 1.2 Deque `std::deque`
**Use for:** Similar to `vector` but allows efficient insertion and removal at both ends.

**Time Complexity:**
| Operation | Time Complexity |
|-----------|-----------------|
| Insert Head | O(1) |
| Insert Tail | O(1) |
| Access by Index | O(1) |
| Remove Head | O(1) |
| Remove Tail | O(1) |

**Example Code:**
```cpp
#include <deque>
#include <iostream>

using namespace std;

deque<int> d;
d.push_front(10); // Insert Head
d.push_back(20); // Insert Tail
int head = d.front(); // Access Head
d.pop_front(); // Remove Head

for(int x : d) cout << x << endl;
```

### 1.3 List `std::list` and `std::forward_list`
**Use for:** Efficient insertion and deletion from the middle.

**Time Complexity:**
| Operation | Time Complexity |
|-----------|-----------------|
| Insert Head | O(1) |
| Insert Tail | O(1) |
| Access by Index | O(n) |
| Remove Head | O(1) |
| Remove Tail | O(1) |

**Example Code:**
```cpp
#include <list>
#include <iostream>

using namespace std;

list<int> l;
l.push_front(10); // Insert Head
l.push_back(20); // Insert Tail
int head = l.front(); // Access Head
l.pop_front(); // Remove Head

for(int x : l) cout << x << endl;
```

### 1.4 Map `std::map` and `std::unordered_map`
**Use for:** Key-value pairs, constant time lookups.

**Time Complexity:**
| Operation | `std::map` | `std::unordered_map` |
|-----------|------------|----------------------|
| Insert | O(log(n)) | O(1) |
| Access by Key | O(log(n)) | O(1) |
| Remove by Key | O(log(n)) | O(1) |

**Example Code:**
```cpp
#include <map>
#include <unordered_map>
#include <iostream>

using namespace std;

map<string, int> m;
m["key"] = 10; // Insert
int value = m["key"]; // Access by Key
m.erase("key"); // Remove by Key

unordered_map<string, int> um;
um["key"] = 10; // Insert
value = um["key"]; // Access by Key
um.erase("key"); // Remove by Key
```

### 1.5 Set `std::set`
**Use for:** Removing duplicates, ordered storage.

**Time Complexity:**
| Operation | Time Complexity |
|-----------|-----------------|
| Insert | O(log(n)) |
| Remove | O(log(n)) |
| Find | O(log(n)) |

**Example Code:**
```cpp
#include <set>
#include <iostream>

using namespace std;

set<int> s;
s.insert(10); // Insert
bool exists = (s.find(10) != s.end()); // Find
s.erase(10); // Remove

for(int x : s) cout << x << endl;
```

### 1.6 Stack `std::stack`
**Use for:** Last-In First-Out operations.

**Time Complexity:**
| Operation | Time Complexity |
|-----------|-----------------|
| Push | O(1) |
| Pop | O(1) |
| Top | O(1) |

**Example Code:**
```cpp
#include <stack>
#include <iostream>

using namespace std;

stack<int> s;
s.push(10); // Push
int top = s.top(); // Top
s.pop(); // Pop

cout << top << endl;
```

### 1.7 Queue `std::queue`
**Use for:** First-In First-Out operations.

**Time Complexity:**
| Operation | Time Complexity |
|-----------|-----------------|
| Push | O(1) |
| Pop | O(1) |
| Front | O(1) |

**Example Code:**
```cpp
#include <queue>
#include <iostream>

using namespace std;

queue<int> q;
q.push(10); // Insert
int head = q.front(); // Access Head
q.pop(); // Remove Head

cout << head << endl;
```

### 1.8 Priority Queue `std::priority_queue`
**Use for:** First-In First-Out with priority overriding arrival time.

**Time Complexity:**
| Operation | Time Complexity |
|-----------|-----------------|
| Push | O(log(n)) |
| Pop | O(log(n)) |
| Top | O(1) |

**Example Code:**
```cpp
#include <queue>
#include <iostream>

using namespace std;

priority_queue<int> p;
p.push(10); // Insert
int top = p.top(); // Access Top
p.pop(); // Remove Top

cout << top << endl;
```

### 1.9 Heap `std::priority_queue`
**Notes:** A heap is an instance of a priority queue.

## 2.0 Trees

### 2.1 Binary Tree
**Use for:** Ordered maps, sets, heaps, binary search trees.

### 2.2 Balanced Trees
**Use for:** Ensure `O(log(n))` operations. Examples: AVL Trees, Red-Black Trees.

### 2.3 Binary Search
**Use for:** Efficiently finding an element in a sorted array or tree.

### 2.4 Depth-First Search
**Use for:** Traversing or searching tree or graph structures.

### 2.5 Breadth-First Search
**Use for:** Traversing or searching tree or graph structures.

## 3.0 NP Complete Problems

### 3.1 NP Complete
**Definition:** Problems that can be verified in polynomial time but not necessarily solved in polynomial time.

### 3.2 Traveling Salesman Problem
**Definition:** Find the shortest possible route visiting each city exactly once and returning to the origin city.

### 3.3 Knapsack Problem
**Definition:** Maximize the total value in the knapsack without exceeding the weight limit.

## 4.0 Algorithms

### 4.1 Insertion Sort
**Idea:** Insert elements into their correct position in a sorted array.
**Time Complexity:**


| Best | Average | Worst |
|------|---------|-------|
| O(n) | O(n^2)  | O(n^2)|

**Example Code:**
```cpp
void insertionSort(vector<int>& arr) {
    int n = arr.size();
    for (int i = 1; i < n; ++i) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            --j;
        }
        arr[j + 1] = key;
    }
}
```

### 4.2 Selection Sort
**Idea:** Select the minimum element from the unsorted part and swap it with the leftmost unsorted element.
**Time Complexity:**
| Best  | Average | Worst |
|-------|---------|-------|
| O(n^2)| O(n^2)  | O(n^2)|

**Example Code:**
```cpp
void selectionSort(vector<int>& arr) {
    int n = arr.size();
    for (int i = 0; i < n - 1; ++i) {
        int min_idx = i;
        for (int j = i + 1; j < n; ++j)
            if (arr[j] < arr[min_idx])
                min_idx = j;
        swap(arr[min_idx], arr[i]);
    }
}
```

### 4.3 Bubble Sort
**Idea:** Repeatedly swap adjacent elements that are out of order.
**Time Complexity:**
| Best | Average | Worst |
|------|---------|-------|
| O(n) | O(n^2)  | O(n^2)|

**Example Code:**
```cpp
void bubbleSort(vector<int>& arr) {
    int n = arr.size();
    for (int i = 0; i < n - 1; ++i)
        for (int j = 0; j < n - i - 1; ++j)
            if (arr[j] > arr[j + 1])
                swap(arr[j], arr[j + 1]);
}
```

### 4.4 Merge Sort
**Idea:** Divide the array into halves, sort each half, and merge them back together.
**Time Complexity:**
| Best    | Average | Worst  |
|---------|---------|--------|
| O(n log n) | O(n log n) | O(n log n)|

**Example Code:**
```cpp
void merge(vector<int>& arr, int l, int m, int r) {
    int n1 = m - l + 1;
    int n2 = r - m;

    vector<int> L(n1), R(n2);
    for (int i = 0; i < n1; ++i)
        L[i] = arr[l + i];
    for (int i = 0; i < n2; ++i)
        R[i] = arr[m + 1 + i];

    int i = 0, j = 0, k = l;
    while (i < n1 && j < n2) {
        if (L[i] <= R[j])
            arr[k++] = L[i++];
        else
            arr[k++] = R[j++];
    }
    while (i < n1)
        arr[k++] = L[i++];
    while (j < n2)
        arr[k++] = R[j++];
}

void mergeSort(vector<int>& arr, int l, int r) {
    if (l >= r) return;
    int m = l + (r - l) / 2;
    mergeSort(arr, l, m);
    mergeSort(arr, m + 1, r);
    merge(arr, l, m, r);
}
```

### 4.5 Quicksort
**Idea:** Partition the array into elements less than and greater than a pivot, then sort each part.
**Time Complexity:**
| Best     | Average  | Worst  |
|----------|----------|--------|
| O(n log n) | O(n log n) | O(n^2)|

**Example Code:**
```cpp
int partition(vector<int>& arr, int low, int high) {
    int pivot = arr[high];
    int i = (low - 1);
    for (int j = low; j <= high - 1; ++j) {
        if (arr[j] < pivot) {
            ++i;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i + 1], arr[high]);
    return (i + 1);
}

void quickSort(vector<int>& arr, int low, int high) {
    if (low < high) {
        int pi = partition(arr, low, high);
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}
```

---

This cheat sheet covers the basic data structures and algorithms in C++. Each section includes the purpose, time complexity, and example code for the data structures and algorithms mentioned.


## Based on Neetcode 150

### 1. Arrays & Hashing
**Concepts:**
- **Arrays:** Store elements in a contiguous memory location.
- **Hashing:** Use hash tables (unordered_map in C++) for fast lookup.

**Problem: Two Sum**
- **Background:** Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.
- **Approach:** Use a hash map (unordered_map in C++) to store each element's index as we iterate through the array. Check if the complement (target - current number) exists in the map.

```cpp
#include <vector>
#include <unordered_map>
using namespace std;

vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> map;
    for (int i = 0; i < nums.size(); i++) {
        int complement = target - nums[i];
        if (map.find(complement) != map.end()) {
            return {map[complement], i};
        }
        map[nums[i]] = i;
    }
    return {};
}
```

### 2. Two Pointers
**Concepts:**
- **Two Pointers:** Use two indices to solve problems involving arrays or strings, often for finding pairs or subarrays.

**Example: Valid Palindrome**
```cpp
#include <string>
#include <cctype>
using namespace std;

bool isPalindrome(string s) {
    int left = 0, right = s.size() - 1;
    while (left < right) {
        while (left < right && !isalnum(s[left])) left++;
        while (left < right && !isalnum(s[right])) right--;
        if (tolower(s[left]) != tolower(s[right])) return false;
        left++;
        right--;
    }
    return true;
}
```
**Problem: Container With Most Water**
- **Background:** Given n non-negative integers `height` where each represents a point at coordinate (i, height[i]), n vertical lines are drawn such that the two endpoints of the line i is at (i, height[i]) and (i, 0). Find two lines, which, together with the x-axis forms a container, such that the container contains the most water.
- **Approach:** Use two pointers technique to maximize the area between two lines.

```cpp
#include <vector>
using namespace std;

int maxArea(vector<int>& height) {
    int maxArea = 0;
    int left = 0, right = height.size() - 1;
    while (left < right) {
        int minHeight = min(height[left], height[right]);
        maxArea = max(maxArea, minHeight * (right - left));
        if (height[left] < height[right]) {
            left++;
        } else {
            right--;
        }
    }
    return maxArea;
}
```

### 3. Sliding Window
**Concepts:**
- **Sliding Window:** Maintain a window over a subset of the data, adjusting its size or moving it as needed.

**Example: Maximum Sum Subarray of Size K**
```cpp
#include <vector>
using namespace std;

int maxSumSubarray(vector<int>& nums, int k) {
    int windowSum = 0, maxSum = 0;
    for (int i = 0; i < k; i++) windowSum += nums[i];
    maxSum = windowSum;
    for (int i = k; i < nums.size(); i++) {
        windowSum += nums[i] - nums[i - k];
        maxSum = max(maxSum, windowSum);
    }
    return maxSum;
}
```

**Problem: Minimum Size Subarray Sum**
- **Background:** Given an array of n positive integers and a positive integer s, find the minimal length of a contiguous subarray of which the sum ≥ s. If there isn't one, return 0 instead.
- **Approach:** Use a sliding window technique to find the smallest subarray that meets the condition.

```cpp
#include <vector>
using namespace std;

int minSubArrayLen(int s, vector<int>& nums) {
    int left = 0, sum = 0, minLength = INT_MAX;
    for (int right = 0; right < nums.size(); right++) {
        sum += nums[right];
        while (sum >= s) {
            minLength = min(minLength, right - left + 1);
            sum -= nums[left++];
        }
    }
    return minLength == INT_MAX ? 0 : minLength;
}
```

### 4. Stack
**Concepts:**
- **Stack:** Last In First Out (LIFO) data structure.

**Example: Valid Parentheses**
```cpp
#include <stack>
#include <string>
using namespace std;

bool isValid(string s) {
    stack<char> stk;
    for (char c : s) {
        if (c == '(' || c == '{' || c == '[') {
            stk.push(c);
        } else {
            if (stk.empty()) return false;
            char top = stk.top();
            if ((c == ')' && top != '(') || (c == '}' && top != '{') || (c == ']' && top != '[')) {
                return false;
            }
            stk.pop();
        }
    }
    return stk.empty();
}
```
**Problem: Evaluate Reverse Polish Notation**
- **Background:** Evaluate the value of an arithmetic expression in Reverse Polish Notation (postfix notation).
- **Approach:** Use a stack to push operands and pop them for operations.

```cpp
#include <vector>
#include <stack>
#include <string>
using namespace std;

int evalRPN(vector<string>& tokens) {
    stack<int> s;
    for (string& token : tokens) {
        if (token == "+" || token == "-" || token == "*" || token == "/") {
            int b = s.top();
            s.pop();
            int a = s.top();
            s.pop();
            if (token == "+") s.push(a + b);
            else if (token == "-") s.push(a - b);
            else if (token == "*") s.push(a * b);
            else if (token == "/") s.push(a / b);
        } else {
            s.push(stoi(token));
        }
    }
    return s.top();
}
```

### 5. Binary Search
**Concepts:**
- **Binary Search:** Efficiently find elements in sorted arrays.

**Example: Binary Search**
```cpp
#include <vector>
using namespace std;

int binarySearch(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) return mid;
        if (nums[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```
**Problem: Search in Rotated Sorted Array**
- **Background:** Suppose an array of length n sorted in ascending order is rotated at some pivot unknown to you beforehand. You are given a target value to search. If found in the array return its index, otherwise return -1.
- **Approach:** Use binary search to find the target element in the rotated sorted array.

```cpp
#include <vector>
using namespace std;

int search(vector<int>& nums, int target) {
    int left = 0, right = nums.size() - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (nums[mid] == target) return mid;
        if (nums[left] <= nums[mid]) {  // Left side is sorted
            if (nums[left] <= target && target < nums[mid]) {
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        } else {  // Right side is sorted
            if (nums[mid] < target && target <= nums[right]) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }
    }
    return -1;
}
```

### 6. Linked List
**Concepts:**
- **Linked List:** Sequence of nodes where each node points to the next node.

**Example: Reverse Linked List**
```cpp
struct ListNode {
    int val;
    ListNode* next;
    ListNode(int x) : val(x), next(nullptr) {}
};

ListNode* reverseList(ListNode* head) {
    ListNode* prev = nullptr;
    ListNode* curr = head;
    while (curr) {
        ListNode* next = curr->next;
        curr->next = prev;
        prev = curr;
        curr = next;
    }
    return prev;
}
```
**Problem: Merge Two Sorted Lists**
- **Background:** Merge two sorted linked lists and return it as a sorted list.
- **Approach:** Use a dummy node and iterate through both lists, appending the smaller current node to the merged list.

```cpp
struct ListNode {
    int val;
    ListNode *next;
    ListNode(int x) : val(x), next(nullptr) {}
};

ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
    ListNode* dummy = new ListNode(0);
    ListNode* current = dummy;
    while (l1 && l2) {
        if (l1->val < l2->val) {
            current->next = l1;
            l1 = l1->next;
        } else {
            current->next = l2;
            l2 = l2->next;
        }
        current = current->next;
    }
    current->next = l1 ? l1 : l2;
    return dummy->next;
}
```

### 7. Trees
**Concepts:**
- **Trees:** Hierarchical data structures with nodes connected by edges.
- **Binary Trees, Binary Search Trees:** Special kinds of trees.

**Example: Binary Tree Inorder Traversal**
```cpp
#include <vector>
using namespace std;

struct TreeNode {
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

void inorderTraversal(TreeNode* root, vector<int>& result) {
    if (root) {
        inorderTraversal(root->left, result);
        result.push_back(root->val);
        inorderTraversal(root->right, result);
    }
}

vector<int> inorderTraversal(TreeNode* root) {
    vector<int> result;
    inorderTraversal(root, result);
    return result;
}
```

**Problem: Binary Tree Maximum Path Sum**
- **Background:** Given a non-empty binary tree, find the maximum path sum. For this problem, a path is defined as any sequence of nodes from some starting node to any node in the tree along the parent-child connections.
- **Approach:** Use recursion to calculate the maximum path sum for each subtree and update the maximum sum found so far.

```cpp
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
};

int maxPathSum(TreeNode* root) {
    int maxSum = INT_MIN;
    maxPathSumHelper(root, maxSum);
    return maxSum;
}

int maxPathSumHelper(TreeNode* root, int& maxSum) {
    if (!root) return 0;
    int leftSum = max(0, maxPathSumHelper(root->left, maxSum));
    int rightSum = max(0, maxPathSumHelper(root->right, maxSum));
    maxSum = max(maxSum, leftSum + rightSum + root->val);
    return max(leftSum, rightSum) + root->val;
}
```

### 8. Tries
**Concepts:**
- **Tries:** Tree-like data structures for storing dynamic sets of strings.

**Problem: Implement Trie (Prefix Tree)**
- **Background:** Implement a trie with insert, search, and startsWith methods.
- **Approach:** Use a nested structure with unordered_map for each node to represent characters and pointers to child nodes.

```cpp
#include <string>
#include <unordered_map>
using namespace std;

class Trie {
private:
    struct TrieNode {
        unordered_map<char, TrieNode*> children;
        bool isEndOfWord;
        TrieNode() : isEndOfWord(false) {}
    };
    
    TrieNode* root;
    
public:
    Trie() {
        root = new TrieNode();
    }
    
    void insert(string word) {
        TrieNode* node = root;
        for (char c : word) {
            if (!node->children.count(c)) {
                node->children[c] = new TrieNode();
            }
            node = node->children[c];
        }
        node->isEndOfWord = true;
    }
    
    bool search(string word) {
        TrieNode* node = root;
        for (char c : word) {
            if (!node->children.count(c)) return false;
            node = node->children[c];
        }
        return node->isEndOfWord;
    }
    
    bool startsWith(string prefix) {
        TrieNode* node = root;
        for (char c : prefix) {
            if (!node->children.count(c)) return false;
            node = node->children[c];
        }
        return true;
    }
};
```

### 9. Heaps (Priority Queue)
**Concepts:**
- **Heaps:** Special tree-based data structure that satisfies the heap property.

**Example: Kth Largest Element in a Stream**
```cpp
#include <queue>
#include <vector>
using namespace std;

class KthLargest {
    priority_queue<int, vector<int>, greater<int>> minHeap;
    int k;
    
public:
    KthLargest(int k, vector<int>& nums) : k(k) {
        for (int num : nums) {
            add(num);
        }
    }
    
    int add(int val) {
        minHeap.push(val);
        if (minHeap.size() > k) {
            minHeap.pop();
        }
        return minHeap.top();
    }
};
```

**Problem: Top K Frequent Elements**
- **Background:** Given a non-empty array of integers, return the k most frequent elements.
- **Approach:** Use a min-heap to keep track of the k most frequent elements based on their frequencies.

```cpp
#include <vector>
#include <unordered_map>
#include <queue>
using namespace std;

vector<int> topKFrequent(vector<int>& nums, int k) {
    unordered_map<int, int> freq;
    for (int num : nums) {
        freq[num]++;
    }
    using Pair = pair<int, int>;
    priority_queue<Pair, vector<Pair>, greater<Pair>> minHeap;

    for (const auto& entry : freq) {
        minHeap.push({entry.second, entry.first});
        if (minHeap.size() > k) {
            minHeap.pop();
        }
    }

    vector<int> result;
    while (!minHeap.empty()) {
        result.push_back(minHeap.top().second);
        minHeap.pop();
    }
    return result;
}
```

### 10. Backtracking
**Concepts:**
- **Backtracking:** Try to build a solution incrementally and backtrack as soon as a solution fails.

**Example: N-Queens**
```cpp
#include <vector>
#include <string>
using namespace std;

void solve(int row, int n, vector<string>& board, vector<vector<string>>& solutions, vector<int>& columns, vector<int>& diag1, vector<int>& diag2) {
    if (row == n) {
        solutions.push_back(board);
        return;
    }
    for (int col = 0; col < n; col++) {
        if (columns[col] || diag1[row - col + n - 1] || diag2[row + col]) continue;
        board[row][col] = 'Q';
        columns[col] = diag1[row - col + n - 1] = diag2[row + col] = 1;
        solve(row + 1, n, board, solutions, columns, diag1, diag2);
        board[row][col] = '.';
        columns[col] = diag1[row - col + n - 1] = diag2[row + col] = 0;
    }
}

vector<vector<string>> solveNQueens(int n) {
    vector<vector<string>> solutions;
    vector<string> board(n, string(n, '.'));
    vector<int> columns(n, 0), diag1(2 * n - 1, 0), diag2(2 * n - 1, 0);
    solve(0, n, board, solutions, columns, diag1, diag2);
    return solutions;
}
```

**Problem: Subsets**
- **Background:** Given an integer array `nums` of unique elements, return all possible subsets (the power set).
- **Approach:** Use backtracking to generate all subsets by including or excluding each element.

```cpp
#include <vector>
using namespace std;

void backtrack(vector<int>& nums, vector<vector<int>>& result, vector<int>& subset, int start) {
    result.push_back(subset);
    for (int i = start; i < nums.size(); i++) {
        subset.push_back(nums[i]);
        backtrack(nums, result, subset, i + 1);
        subset.pop_back();
    }
}

vector<vector<int>> subsets(vector<int>& nums) {
    vector<vector<int>> result;
    vector<int> subset;
    backtrack(nums, result, subset, 0);
    return result;
}
```

### 11. Graphs
**Concepts:**
- **Graphs:** Data structures consisting of nodes (vertices) connected by edges.
- **Graph Traversal (BFS, DFS):** Explore nodes and edges of a graph.

**Example: Number of Islands**
```cpp
#include <vector>
#include <queue>
using namespace std;

void bfs(vector<vector<char>>& grid, int r, int c) {
    int nr = grid.size();
    int nc = grid[0].size();
    queue<pair<int, int>> q;
    q.push({r, c});
    grid[r][c] = '0';  // Mark the cell as visited by setting it to '0'
    vector<pair<int, int>> directions = {{1, 0}, {0, 1}, {-1, 0}, {0, -1}};
    while (!q.empty()) {
        auto [x, y] = q.front();
        q.pop();
        for (auto [dx, dy] : directions) {
            int newX = x + dx;
            int newY = y + dy;
            if (newX >= 0 && newX < nr && newY >= 0 && newY < nc && grid[newX][newY] == '1') {
                q.push({newX, newY});
                grid[newX][newY] = '0';  // Mark the new cell as visited
            }
        }
    }
}

int numIslands(vector<vector<char>>& grid) {
    if (grid.empty()) return 0;
    int nr = grid.size();
    int nc = grid[0].size();
    int num_islands = 0;
    for (int r = 0; r < nr; r++) {
        for (int c = 0; c < nc; c++) {
            if (grid[r][c] == '1') {
                num_islands++;
                bfs(grid, r, c);
            }
        }
    }
    return num_islands;
}

```

**Problem: Course Schedule**
- **Background:** There are a total of `numCourses` courses you have to take, labeled from 0 to `numCourses - 1`. Some courses have prerequisites. Given the total number of courses and a list of prerequisite pairs, return true if you can finish all courses.
- **Approach:** Use topological sort (BFS) to check if there is a cycle in the graph.

```cpp
#include <vector>
#include <queue>
using namespace std;

bool canFinish(int numCourses, vector<vector<int>>& prerequisites) {
    vector<vector<int>> adjList(numCourses);
    vector<int> indegree(numCourses, 0);

    for (const auto& prereq : prerequisites) {
        adjList[prereq[1]].push_back(prereq[0]);
        indegree[prereq[0]]++;
    }

    queue<int> q;
    for (int i = 0; i < numCourses; i++) {
        if (indegree[i] == 0) {
            q.push(i);
        }
    }

    int count = 0;
    while (!q.empty()) {
        int course = q.front();
        q.pop();
        count++;
        for (int nextCourse : adjList[course]) {
            if (--indegree[nextCourse] == 0) {
                q.push(nextCourse);
            }
        }
    }

    return count == numCourses;
}
```

### 12. Dynamic Programming (DP)
**Concepts:**
- **Dynamic Programming:** Solve problems by combining the solutions to subproblems.

**Example: Climbing Stairs**
```cpp
#include <vector>
using namespace std;

int climbStairs(int n) {
    if (n <= 2) return n;
    vector<int> dp(n + 1);
    dp[1] = 1;
    dp[2] = 2;
    for (int i = 3; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
}
```
**Problem: Longest Increasing Subsequence**
- **Background:** Given an integer array `nums`, return the length of the longest strictly increasing subsequence.
- **Approach:** Use dynamic programming to keep track of the length of the longest subsequence ending at each index.

```cpp
#include <vector>
using namespace std;

int lengthOfLIS(vector<int>& nums) {
    if (nums.empty()) return 0;
    vector<int> dp(nums.size(), 1);
    int maxLength = 1;
    for (int i = 1; i < nums.size(); i++) {
        for (int j = 0; j < i; j++) {
            if (nums[i] > nums[j]) {
                dp[i] = max(dp[i], dp[j] + 1);
            }
        }
        maxLength = max(maxLength, dp[i]);
    }
    return maxLength;
}
```

### 13. Intervals
**Concepts:**
- **Intervals:** Problems involving ranges or segments.

**Example: Merge Intervals**
```cpp
#include <vector>
#include <algorithm>
using namespace std;

vector<vector<int>> merge(vector<vector<int>>& intervals) {
    if (intervals.empty()) return {};
    sort(intervals.begin(), intervals.end());
    vector<vector<int>> merged;
    for (const auto& interval : intervals) {
        if (merged.empty() || merged.back()[1] < interval[0]) {
            merged.push_back(interval);
        } else {
            merged.back()[1] = max(merged.back()[1], interval[1]);
        }
    }
    return merged;
}
```

**Problem: Insert Interval**
- **Background:** Given a set of non-overlapping intervals, insert a new interval into the intervals (merge if necessary).
- **Approach:** Traverse the list and handle different cases of overlapping and merging.

```cpp
#include <vector>
using namespace std;

vector<vector<int>> insert(vector<vector<int>>& intervals, vector<int>& newInterval) {
    vector<vector<int>> result;
    int i = 0, n = intervals.size();
    while (i < n && intervals[i][1] < newInterval[0]) {
        result.push_back(intervals[i++]);
    }
    while (i < n && intervals[i][0] <= newInterval[1]) {
        newInterval[0] = min(newInterval[0], intervals[i][0]);
        newInterval[1] = max(newInterval[1], intervals[i][1]);
        i++;
    }
    result.push_back(newInterval);
    while (i < n) {
        result.push_back(intervals[i++]);
    }
    return result;
}
```

### 14. Greedy
**Concepts:**
- **Greedy Algorithms:** Make the best choice at each step.

**Example: Maximum Subarray**
```cpp
#include <vector>
using namespace std;

int maxSubArray(vector<int>& nums) {
    int max_sum = nums[0], current_sum = nums[0];
    for (int i = 1; i < nums.size(); i++) {
        current_sum = max(nums[i], current_sum + nums[i]);
        max_sum = max(max_sum, current_sum);
    }
    return max_sum;
}
```
**Problem: Jump Game**
- **Background:** Given an array of non-negative integers `nums`, you are initially positioned at the first index of the array. Each element in the array represents your maximum jump length at that position. Determine if you are able to reach the last index.
- **Approach:** Use a greedy algorithm to keep track of the farthest index that can be reached.

```cpp
#include <vector>
using namespace std;

bool canJump(vector<int>& nums) {
    int farthest = 0;
    for (int i = 0; i < nums.size(); i++) {
        if (i > farthest) return false;
        farthest = max(farthest, i + nums[i]);
    }
    return true;
}
```

### 15. Bit Manipulation
**Concepts:**
- **Bit Manipulation:** Perform operations directly on binary representations.

**Example: Single Number**
```cpp
#include <vector>
using namespace std;

int singleNumber(vector<int>& nums) {
    int result = 0;
    for (int num : nums) {
        result ^= num;
    }
    return result;
}
```

**Problem: Number of 1 Bits**
- **Background:** Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).
- **Approach:** Use bit manipulation to count the number of '1' bits.

```cpp
int hammingWeight(uint32_t n) {
    int count = 0;
    while (n != 0) {
        count += n & 1;
        n >>= 1;
    }
    return count;
}
```

### 16. Math & Geometry
**Concepts:**
- **Math Problems:** Often involve combinatorics, probability, etc.
- **Geometry Problems:** Involve shapes, distances, etc.

**Example: Pow(x, n)**
```cpp
double myPow(double x, int n) {
    if (n == 0) return 1;
    if (n < 0) {
        x = 1 / x;
        n = -n;
    }
    double half = myPow(x, n / 2);
    if (n % 2 == 0) {
        return half * half;
    } else {
        return half * half * x;
    }
}
```

**Problem: Happy Number**
- **Background:** Write an algorithm to determine if a number is "happy". A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy numbers.
- **Approach:** Use a hash set to detect cycles.

```cpp
#include <unordered_set>
using namespace std;

int sumOfSquares(int n) {
    int sum = 0;
    while (n) {
        int digit = n % 10;
        sum += digit * digit;
        n /= 10;
    }
    return sum;
}

bool isHappy(int n) {
    unordered_set<int> seen;
    while (n != 1 && !seen.count(n)) {
        seen.insert(n);
        n = sumOfSquares(n);
    }
    return n == 1;
}
```
# 📚 AlgoMania Projects

A collection of **menu-driven C++ console applications** built to demonstrate the practical application of **Data Structures & Algorithms (DSA)** in solving real-world problems. Each project models a familiar scenario and uses appropriate STL containers and algorithms to achieve efficient solutions.

---

# 🛒 Project 1: Inventory & Billing System

A menu-driven C++ console application simulating a shop's stock management and billing counter — built to demonstrate how multiple data structures work together to model a real, everyday workflow.

## 📌 Problem Statement

A retail counter needs to track stock levels, process customer orders in the order they arrive, generate bills, allow last-item cancellation, and flag items running low — all efficiently and in real time. This project simulates that entire flow end-to-end.

## ✨ Features

* 📦 Add or update stock for an item
* 🛍️ Place customer orders that queue up for processing
* ⏳ Process orders one at a time in first-come-first-served order
* ↩️ Cancel the most recently billed item (with automatic stock restoration)
* 🧾 View the current running bill
* ⚠️ Get a low-stock alert for items below a chosen threshold
* 📊 Generate a sales report ranked by revenue

## 🧠 Data Structures & Algorithms Used

| Feature                 | DSA Concept                 | Why                                                                         |
| :---------------------- | :-------------------------- | :-------------------------------------------------------------------------- |
| Stock lookup by SKU     | Hash Map (`unordered_map`)  | O(1) average access to any item's stock/price                               |
| Order processing        | Queue                       | Orders must be served in the exact order they were placed (FIFO)            |
| Cancel last billed item | Stack                       | The most recently billed item must be the first one reversible (LIFO)       |
| Low-stock alert         | Min-Heap (`priority_queue`) | Surfaces items with the smallest quantity first, in O(log n) per extraction |
| Sales report            | Sorting (custom comparator) | Ranks items by revenue generated, O(n log n)                                |

### ⏱️ Time Complexity

| Operation               |  Complexity  |
| :---------------------- | :----------: |
| Add/Update Stock        | O(1) average |
| Place Order             |     O(1)     |
| Process Next Order      | O(1) average |
| Cancel Last Billed Item |     O(1)     |
| Low Stock Alert         |  O(n log n)  |
| Sales Report            |  O(n log n)  |

### 🚀 Run

```bash
g++ -std=c++17 inventory_billing_system.cpp -o inventory_billing
./inventory_billing
```

### 💡 Sample Workflow

1. Add stock for a few items with SKU, price, and quantity.
2. Place a few customer orders — they enter a processing queue.
3. Process orders one by one and watch the bill build up.
4. Cancel the last billed item and see the stock and bill total automatically restored.
5. Check the low-stock alert for items running out.
6. Generate the final sales report ranked by revenue.

### 🎯 Why This Project

A shop billing counter is something everyone has experienced firsthand, so there's no background needed to explain what the system does. It also naturally combines five different data structures — each solving one specific part of the workflow — which made it a strong way to demonstrate practical DSA usage beyond isolated problems.

### 🛠️ Tech Stack

* C++17
* STL: `unordered_map`, `queue`, `stack`, `priority_queue`, `vector`, custom comparators

---

# 🎓 Project 2: Exam / Result Management & Ranking System

A menu-driven C++ console application that manages student exam records and generates rank lists, top performers, and grade analytics — designed to solve a real process every college goes through at the end of each semester.

## 📌 Problem Statement

Colleges need a reliable way to rank students, identify top performers, and analyze grade distribution once results are in. This project models that process using efficient data structures instead of manually sorting through spreadsheets.

## ✨ Features

* 📝 Add student records with subject-wise marks
* 🔍 Search a student's result instantly by roll number
* 🏆 Generate a full rank list ordered by total marks
* ⭐ View the Top-N toppers without sorting the entire dataset
* 📊 View grade distribution across the class
* 💾 Export the rank list to a file

## 🧠 Data Structures & Algorithms Used

| Feature               | DSA Concept                         | Why                                                                                 |
| :-------------------- | :---------------------------------- | :---------------------------------------------------------------------------------- |
| Search by roll number | Hash Map (`unordered_map`)          | O(1) average lookup instead of scanning all records                                 |
| Rank list generation  | Sorting (custom comparator)         | Orders students by total marks, with tie-breaking by name                           |
| Top-N toppers         | Min-Heap of size N                  | Finds N largest totals in O(n log N) instead of sorting all n records in O(n log n) |
| Grade distribution    | Hashing (`unordered_map<char,int>`) | O(1) frequency counting per grade bucket                                            |

### ⏱️ Time Complexity

| Operation          |  Complexity  |
| :----------------- | :----------: |
| Add Student        |     O(1)     |
| Search by Roll No. | O(1) average |
| View Rank List     |  O(n log n)  |
| Top-N Toppers      |  O(n log N)  |
| Grade Distribution |     O(n)     |

### 🚀 Run

```bash
g++ -std=c++17 exam_result_ranking_system.cpp -o exam_ranking
./exam_ranking
```

### 💡 Sample Workflow

1. Add a batch of student records with marks for 5 subjects.
2. View the full rank list, sorted automatically by total marks.
3. Use the Top-N option to fetch just the top 3 or top 5 students without generating the entire ranked list.
4. Check the grade distribution to see how many students fall into each grade bucket.
5. Export the final rank list to a file for record-keeping.

### 🎯 Why This Project

Every student understands result ranking — there's no domain knowledge required to explain what it does. It also mirrors an actual process my own college runs each semester, which made it a natural, practical problem to solve using sorting, hashing, and heaps together instead of relying on any single technique.

### 🛠️ Tech Stack

* C++17
* STL: `unordered_map`, `priority_queue`, `vector`, custom comparators, file I/O

---

# ✅ Project 3: Smart Task Management System

A menu-driven C++ console application that manages tasks using core data structures — built to demonstrate practical use of heaps, hash maps, and stacks in a real-world scheduling problem.

## 📌 Problem Statement

Managing daily tasks efficiently requires quick lookups, priority-based scheduling, and the ability to undo mistakes. This project simulates a task manager that lets users add, search, prioritize, and undo task operations — all backed by efficient data structures instead of simple linear storage.

## ✨ Features

* ➕ Add, delete, and mark tasks as done
* ⚡ Fetch the most urgent pending task instantly
* 🔍 Search any task by ID in constant time
* 📅 View all tasks sorted by deadline
* ↩️ Undo the last add/delete action
* 💾 Persist tasks to a file and reload them later

## 🧠 Data Structures & Algorithms Used

| Feature                | DSA Concept                 | Why                                                            |
| :--------------------- | :-------------------------- | :------------------------------------------------------------- |
| Get next priority task | Max-Heap (`priority_queue`) | Always retrieves the highest-priority pending task in O(log n) |
| Search task by ID      | Hash Map (`unordered_map`)  | O(1) average lookup instead of O(n) linear search              |
| Undo last action       | Stack                       | LIFO order naturally matches "undo the most recent operation"  |
| View tasks by deadline | Sorting (custom comparator) | O(n log n) ordering of tasks for a readable view               |

### ⏱️ Time Complexity

| Operation               |     Complexity     |
| :---------------------- | :----------------: |
| Add Task                |      O(log n)      |
| Search by ID            |    O(1) average    |
| Get Next Priority Task  | O(log n) amortized |
| View Sorted by Deadline |     O(n log n)     |
| Undo                    |        O(1)        |

### 🚀 Run

```bash
g++ -std=c++17 task_management_system.cpp -o task_manager
./task_manager
```

### 💡 Sample Workflow

1. Add a few tasks with different priorities and deadlines.
2. Use option 4 to instantly fetch the most urgent task.
3. Use option 5 to view all tasks sorted by deadline.
4. Delete a task, then use option 7 to undo the deletion.
5. Save your session with option 8 and reload it anytime with option 9.

### 🎯 Why This Project

Task scheduling is something everyone interacts with daily, which makes it easy to reason about — but under the hood it requires combining multiple data structures, each solving a distinct problem: a heap for "what's next," a hash map for "find fast," and a stack for "undo." This project was built to apply these concepts to a relatable, real use case rather than an isolated algorithm exercise.

### 🛠️ Tech Stack

* C++17
* STL: `unordered_map`, `priority_queue`, `stack`, `vector`, file I/O

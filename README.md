# AgriSmart: Smart Crop Recommendation System

**AgriSmart** is a lightweight command-line utility written in C that assists farmers and agricultural consultants in choosing optimal crops. By assessing region-specific inputs like environmental seasons and regional water availability, the system recommends a tailored list of crops, manages crop selections, and showcases foundational farming guidelines.

This project showcases core procedural programming paradigms, structured string handling, and recursive traversal algorithms without relying on heavy external dependencies.

---

## 🛠️ Features
* **Smart Filtering Logic:** Matches combinations of seasons (Winter, Summer, Spring) and water availability profiles (Low, Medium, High) to output precise crop groupings.
* **Recursive View Engine:** Employs recursive loops rather than standard iterative statements (`for`/`while`) to cleanly render options to the terminal interface.
* **Granular Profile Delivery:** Maps user selections directly back to dynamic schedules detailing sowing periods, ideal irrigation intervals, and estimated harvest timelines.

---

## 🧮 C Concepts Covered

This project serves as a functional demonstration of intermediate C concepts, including:
* **Flattened Multi-dimensional Character Arrays:** Employs a continuous 1D buffer (`char cr[100]`) handled as chunked string slots spaced exactly 20 bytes apart to act as a 2D array matrix.
* **Pointer Arithmetic & Referencing:** Utilizes memory address referencing (`&cr[i * 20]`) to selectively parse, extract, and write string tokens safely.
* **Recursion:** Implements a localized recursive function to handle array traversal and display workflows without relying on native loop structures.
* **Conditional Control Flow:** Demonstrates efficient code execution branching utilizing nested `if-else` expressions and compact multi-case `switch` panels.

---

## 🏗️ Code Architecture

The codebase is split into modular components designed around specific logical responsibilities:

* `main()`: Coordinates execution by acquiring string inputs from standard input (`stdin`), calling execution modules, and formatting summary outputs.
* `selectCrops(char si[], char wa[], char cr[])`: The core evaluation rules engine. It updates the flattened string buffer based on matching climate variables.
* `displayCrops(char cr[], int i)`: A recursive display driver that prints individual crop options and handles bounds tracking via an execution call stack.
* `cropDetails(int choice)`: Maps numeric inputs directly to preconfigured crop metadata profiles outlining essential farming practices.

---

## 🚀 Getting Started

### Prerequisites
To build and run this software, you need a C compiler installed on your system (such as `gcc` or `clang`).

### Compilation
Open your terminal or command prompt, navigate to the folder containing your file (e.g., `main.c`), and execute the compiler command:

```bash
gcc main.c -o agrismart
```

### Execution
Run the compiled executable file:

```bash
# On Linux/macOS
./agrismart

# On Windows
agrismart.exe
```

---

## 📊 Sample Execution Flow

```text
===== AGRISMART =====
Enter State: Punjab
Enter Season (Winter/Summer/Spring): Winter
Water Availability (Low/Medium/High): Low

===== RECOMMENDED CROPS =====
1. Mustard
2. Gram
3. Lentil
4. Peas
5. Barley

Select your crop: 1

===== SELECTED CROP DETAILS =====
State: Punjab
Selected Crop: Mustard
Sowing: October-November
Water: Medium
Irrigation: Every 15-20 days
Harvest: February-March

Farming Steps:
1. Prepare the land.
2. Sow the seeds.
3. Allow seeds to germinate.
4. Provide water and take care of crops.
5. Harvest the crop when mature.
Thanks for consulting!
```

---

## 📌 Future Enhancement Roadmaps
To scale this codebase closer to a full **Student Record Management System** or similar administrative enterprise setups, you can add:
1. **Dynamic Memory Allocation:** Replace the static `char cr[100]` structure with dynamic heap memory arrays (`malloc`, `realloc`) to support dynamic quantities of recommended items.
2. **Structures (`struct`):** Bind the discrete crop variables (sowing date, harvest window, title) inside organized objects instead of printing static `switch` messages.
3. **File System Integration (`stdio.h` file operations):** Save consulting history files directly to external text logs so details persist across multiple program runs.

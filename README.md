# Time Arithmetic & Structure Analyzer (C++)

This C++ application implements a custom data structure to manage and manipulate time in the format of hours, minutes, and seconds. It focuses on robust time arithmetic, ensuring that all calculations respect the 24-hour clock cycle.

###  Mathematical & Technical Logic
The core of the application relies on **Time Normalization**. To perform accurate arithmetic, the program converts complex `Time` structures into a single scalar value (total seconds):

$$TotalSeconds = (Hours \times 3600) + (Minutes \times 60) + Seconds$$

**Key Algorithms:**
* **Rollover Handling:** When adding an interval, the program uses modulo arithmetic to ensure the time stays within a 24-hour range:
  $$\text{NewTime} = (\text{TotalSeconds} + \text{Interval}) \pmod{86400}$$
* **Duration Calculation:** To find the interval between Time A and Time B, the program handles "day-wrap" cases (where B is on the following day) by adding $86,400$ seconds if the difference is negative.



###  Key Features
* **Custom Data Structures:** Uses a `struct Time` to encapsulate related data members, improving code readability and organization.
* **Normalization Logic:** Efficiently converts between human-readable time and raw seconds for calculation.
* **Boundary Case Management:** Correctily handles midnight transitions (rollover) for both addition and subtraction.
* **Pass-by-Reference:** Utilizes `const Time&` references in functions to optimize performance by avoiding unnecessary data copying.

This project was developed as part of the programming curriculum at **Lviv Polytechnic National University**.

###  Technical Stack
* **Language:** C++
* **Concepts:** Structs, Address Arithmetic (references), Modulo Operations, Time Normalization.

###  How to Use
1. Compile the program using any C++ compiler (e.g., `g++`).
2. The current implementation uses a predefined Time A (`23:45:50`) and an interval of `5000` seconds.
3. Run the executable to see the calculated Time B and the verified difference between the two points.

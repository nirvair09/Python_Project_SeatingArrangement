# Exam Seating Arrangement & Attendance System

A comprehensive Python-based solution for automating exam seating allocations and generating professional attendance sheets. This project streamlines the complex process of assigning students to rooms while adhering to specific constraints and seating modes.

## 🚀 Overview

The **Exam Seating Arrangement System** is designed to take student registration data, exam timetables, and room availability to produce a structured seating plan. Beyond just allocation, it generates individual Excel-based attendance sheets for every room, complete with student names, roll numbers, and signature fields.

## ✨ Key Features

- **Flexible Seating Modes**:
    - **Dense**: Utilizes full room capacity (minus a buffer).
    - **Sparse**: Uses half the room capacity for increased spacing (minus a buffer).
- **Buffer Seat Management**: Allows users to specify a fixed number of empty seats per room for flexibility.
- **Priority-Based Allocation**:
    - Automatically prioritizes specific blocks (e.g., Block 9) and lower floors.
    - Seamlessly overflows to larger Lecture Halls (LT halls) when needed.
- **Smart Course Sorting**: Prioritizes larger courses for allocation to minimize room fragmentation.
- **Automated Attendance Sheets**:
    - Generates separate Excel files for each (Date, Course, Room, Shift) combination.
    - Includes student names mapped from roll numbers.
    - Features pre-formatted signature areas for students, invigilators, and TAs.

## 🛠️ Technology Stack

- **Languge**: Python
- **Libraries**:
    - `pandas`: For data manipulation and tabular processing.
    - `openpyxl`: For creating, styling, and formatting Excel workbooks.
- **Environment**: Jupyter Notebook (tested on Google Colab/Local Jupyter).

## 🧠 Code Logic

The system follows a structured pipeline:

1.  **Data Ingestion**: Reads a master Excel file (`py_project.xlsx`) containing registrations, timetable, room data, and name mappings.
2.  **Configuration**: Prompts the user for `buffer_seats` and `seating_mode` (dense/sparse).
3.  **Capacity Calculation**:
    - `get_max_capacity()`: Dynamically calculates available seats based on the mode and buffer.
4.  **Allocation Engine**:
    - `allocate_seating()`: 
        - Iterates through the timetable sessions.
        - Sorts courses by size.
        - Assigns students to rooms starting from Block 9, then LT halls.
        - Records student roll numbers assigned to each room.
5.  **Output Generation**:
    - `seating_arrangement.xlsx`: A summary file of all allocations.
    - `create_attendance_sheet()`: Uses `openpyxl` to create stylized, ready-to-print Excel sheets for each room.

## 📋 Data Requirements

The project expects an input file named `py_project.xlsx` with the following sheets:

| Sheet Name | Description | Key Columns |
| :--- | :--- | :--- |
| **ip_1** | Student Registrations | `rollno`, `course_code` |
| **ip_2** | Exam Timetable | `Date`, `Morning`, `Evening` |
| **ip_3** | Room Details | `Room No.`, `Exam Capacity`, `Block` |
| **ip_4** | Roll to Name Map | `Roll`, `Name` |

## ⚙️ How to Run

1.  **Prerequisites**:
    - Ensure Python 3.x is installed.
    - Install dependencies:
      ```bash
      pip install pandas openpyxl
      ```
2.  **Prepare Data**:
    - Place your `py_project.xlsx` in the project directory.
3.  **Execute**:
    - Open `FinalProject_.ipynb` in a Jupyter environment.
    - Run all cells.
    - When prompted, enter the number of buffer seats (e.g., `2`) and the seating mode (`dense` or `sparse`).
4.  **Review Results**:
    - Check the root directory for `seating_arrangement.xlsx` and the individual attendance sheets.

---
*Developed for efficient academic management.*

Built a complete and practical system to automate **exam seating allocation and attendance generation**—a real-world solution with strong applications in educational institutions.

```markdown
# 🎓 Exam Seating Arrangement & Attendance Sheet Generator 📋

A comprehensive Python project to **automate exam room seating allocations** and generate **attendance sheets** for IIT Patna or any other institution. This tool ensures optimal seat usage, supports different seating modes (dense/sparse), and produces organized Excel sheets for invigilation.

---

## 🚀 Features

✅ **Seating Allocation Automation**  
• Assigns students to rooms based on course size, block priority (Block 9 first, then LT halls), and room capacity.  
• Supports `dense` (maximized capacity) and `sparse` (distanced seating) modes.  
• Considers **buffer seats** for safety or spacing needs.

✅ **Dynamic Attendance Sheet Generation**  
• Generates an Excel attendance sheet for every exam room.  
• Includes student **roll numbers**, **mapped names**, and spaces for **invigilator/TA signatures**.  
• Professional formatting using `openpyxl` (centered cells, borders, adjusted widths).

✅ **Custom Configurations**  
• Set buffer seats interactively.  
• Choose seating density (`dense` or `sparse`) based on current policy.  

✅ **Excel-Driven Input**  
• Student-course registrations  
• Exam schedules (with shifts)  
• Room details (capacity, block)  
• Roll-to-name mapping

✅ **Output Files**  
• `seating_arrangement.xlsx` – Summary of student allocations per course & room.  
• Individual Excel attendance sheets per room, named like:  
  `DD_MM_YYYY_COURSECODE_ROOMNO_SHIFT.xlsx`

---

## 🛠 Technologies Used

- **Python 3**
- `pandas` – Data handling and transformation  
- `openpyxl` – Excel creation, formatting  
- `xlsx` files as input/output

---

## 📁 Folder Structure

```

📁 exam\_seating\_project/
├── main.py
├── py\_project.xlsx           # Input Excel file (students, rooms, timetable)
├── seating\_arrangement.xlsx  # Output seating plan
├── \*.xlsx                    # Generated attendance sheets
└── README.md

````

---

## 🔧 How to Use

1. Place your data Excel file as `py_project.xlsx` with sheets:
   - `ip_1`: Roll No. ↔ Course Code  
   - `ip_2`: Exam Schedule (Date, Morning, Evening)  
   - `ip_3`: Room info (Block, Room No., Capacity)  
   - `ip_4`: Roll ↔ Student Name

2. Run the main script:

```bash
python main.py
````

3. Provide buffer and seating mode when prompted.

4. Check output files in the same directory!

---

## 📌 Example Attendance Sheet

Each sheet contains:

| Roll        | Student\_Name | Signature |
| ----------- | ------------- | --------- |
| 2101CS01    | Aryan Singh   |           |
| 2101CS02    | Bhavya Nair   |           |
| ...         | ...           |           |
| TA 1        |               |           |
| TA 2        |               |           |
| Invigilator |               |           |

---

## 📈 Impact

This project is tailored to streamline exam management, saving hours of manual effort and reducing room conflicts or over-allocations. It’s easily extensible to other institutions or exam settings.

---

## 🤝 Contributions

Pull requests, feature suggestions, and issue reports are welcome!

---

## 📜 License

MIT License

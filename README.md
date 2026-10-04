# PyCon: The Complete Codolingo Python Curriculum Content Dataset

[![Curriculum Status](https://img.shields.io/badge/Curriculum-100%25%20Complete%20(244%2F244)-brightgreen.svg)]()
[![Items Generated](https://img.shields.io/badge/Items-7%2C320%20Validated-blue.svg)]()
[![Sections](https://img.shields.io/badge/Units-43%20Sections-purple.svg)]()
[![Schema](https://img.shields.io/badge/Format-Canonical%20JSON-orange.svg)]()

This repository contains the standalone, learner-facing curriculum content for the **Codolingo Python Master Curriculum**.

It houses all **43 Sections** and **244 Lessons**, comprising **7,320 interactive educational items** (exactly 30 meaningful items per lesson with zero placeholder content).

---

## Directory Structure

```
pycon/
├── python_content/
│   ├── unit_01/                 # Getting Started with Python (Lessons 1.1 - 1.6)
│   ├── unit_02/                 # Variables and Data Types (Lessons 2.1 - 2.7)
│   ├── unit_03/                 # Basic Operators (Lessons 3.1 - 3.5)
│   ├── ...
│   └── unit_43/                 # Final Synthesis and Capstone (Lessons 43.1 - 43.5)
├── PYTHON_MASTER_SYLLABUS.txt   # Master syllabus mapping all 43 units
└── README.md                    # Documentation & schema reference
```

---

## Complete Unit Breakdown (All 43 Units)

| Unit | Title | Lessons | Interactive Items |
| :--- | :--- | :---: | :---: |
| **Unit 01** | Getting Started with Python | 6 | 180 |
| **Unit 02** | Variables and Data Types | 7 | 210 |
| **Unit 03** | Basic Operators | 5 | 150 |
| **Unit 04** | User Input and Output | 4 | 120 |
| **Unit 05** | Conditional Logic | 6 | 180 |
| **Unit 06** | Loops and Repetition | 8 | 240 |
| **Unit 07** | String Manipulation | 9 | 270 |
| **Unit 08** | Lists | 6 | 180 |
| **Unit 09** | Tuples and Sets | 6 | 180 |
| **Unit 10** | Dictionaries | 7 | 210 |
| **Unit 11** | Basic Data Structures Review | 6 | 180 |
| **Unit 12** | Functions: The Basics | 5 | 150 |
| **Unit 13** | Functions: Scope and Advanced Parameters | 5 | 150 |
| **Unit 14** | Functional Programming Concepts | 6 | 180 |
| **Unit 15** | Modules and Packages | 6 | 180 |
| **Unit 16** | Error Handling and Exceptions | 6 | 180 |
| **Unit 17** | File Input and Output | 7 | 210 |
| **Unit 18** | Working with Different File Formats | 5 | 150 |
| **Unit 19** | Regular Expressions | 6 | 180 |
| **Unit 20** | Date and Time Handling | 5 | 150 |
| **Unit 21** | Object-Oriented Programming: Classes & Objects | 6 | 180 |
| **Unit 22** | OOP: Inheritance and Polymorphism | 5 | 150 |
| **Unit 23** | OOP: Encapsulation and Abstraction | 5 | 150 |
| **Unit 24** | Advanced OOP Concepts | 6 | 180 |
| **Unit 25** | Object-Oriented Design Patterns | 6 | 180 |
| **Unit 26** | Iterators and Generators | 5 | 150 |
| **Unit 27** | Context Managers and the with Statement | 5 | 150 |
| **Unit 28** | Decorators | 6 | 180 |
| **Unit 29** | Basic Data Structures: Stacks and Queues | 5 | 150 |
| **Unit 30** | Linked Lists | 5 | 150 |
| **Unit 31** | Trees and Graphs: Introduction | 5 | 150 |
| **Unit 32** | Searching and Sorting Algorithms | 7 | 210 |
| **Unit 33** | Algorithm Complexity and Big O (Deep Dive) | 5 | 150 |
| **Unit 34** | Recursion and Dynamic Programming | 5 | 150 |
| **Unit 35** | Concurrency: Threading and Multiprocessing | 6 | 180 |
| **Unit 36** | Asynchronous Programming with asyncio | 6 | 180 |
| **Unit 37** | Working with Web APIs and Networking | 6 | 180 |
| **Unit 38** | Web Scraping Fundamentals | 5 | 150 |
| **Unit 39** | Databases and SQL with Python | 7 | 210 |
| **Unit 40** | Testing and Quality Assurance | 6 | 180 |
| **Unit 41** | Packaging, Distribution, and Virtual Environments | 5 | 150 |
| **Unit 42** | Performance Optimization and Profiling | 5 | 150 |
| **Unit 43** | Final Synthesis and Capstone | 5 | 150 |
| **TOTAL** | **43 Units** | **244 Lessons** | **7,320 Items** |

---

## Lesson JSON Schema

Each lesson is stored as an independent, canonical JSON document (`{unit_id}/{lesson_id}_{slug}.json`).

### Top-Level Document Structure
```json
{
  "lesson_id": "12.1",
  "title": "Defining Functions",
  "unit": "Functions: The Basics",
  "items": [ ... ]
}
```

### Item Types & Pedagogical Clusters
Every lesson contains exactly 30 items arranged across 5 pedagogical clusters:

1. **Micro-Lessons & Active Recall (Items 1–6)**:
   - `micro_lesson`: Educational explanations with code snippets.
   - `multiple_choice`: Conceptual recall questions with 4 choices and explanations.
2. **Code Prediction & Execution Tracing (Items 7–12)**:
   - `code_prediction`: Predict execution outcomes.
   - `output_prediction`: Predict stdout values.
3. **Fill in the Blank & Sequencing (Items 13–18)**:
   - `fill_in_the_blank`: Complete missing keywords or operators (`___`).
   - `code_ordering`: Arrange shuffled code lines into logical execution order.
4. **Debugging & Bug Repair (Items 19–24)**:
   - `error_diagnosis`: Identify syntax or runtime errors.
   - `fix_the_code`: Correct broken code blocks.
5. **Hands-On Coding & Challenges (Items 25–30)**:
   - `write_the_code`: Write code solving specific requirements with test cases.
   - `mini_challenge` / `real_world_scenario`: Applied synthesis challenges.

---

## How to Consume the Curriculum

### Python
```python
import json
from pathlib import Path

lesson_file = Path("python_content/unit_01/1.1_what_is_python.json")
with open(lesson_file, "r", encoding="utf-8") as f:
    lesson = json.load(f)

print(f"Loaded: {lesson['title']} ({len(lesson['items'])} items)")
```

### TypeScript / JavaScript (Node.js & Frontend)
```typescript
import fs from "fs";
import path from "path";

interface CurriculumItem {
  id: string;
  type: string;
  concept: string;
  skill: string;
  difficulty: "easy" | "medium" | "hard";
  prompt?: string;
  options?: string[];
  correct_answer?: string | string[];
  starter_code?: string;
  solution_code?: string;
  explanation?: string;
}

interface Lesson {
  lesson_id: string;
  title: string;
  unit: string;
  items: CurriculumItem[];
}

const raw = fs.readFileSync("python_content/unit_04/4.1_the_input_function.json", "utf-8");
const lesson: Lesson = JSON.parse(raw);
```

---

## License

MIT License. Open for educational platforms, apps, and learning management systems.

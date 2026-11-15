# Mission 0: TO CREATE GITHUB WORKSPACE

## 1. Task Completed And Repository Name
- **Repository Name:** `digital-detective-8495`
- **Task Summary:** Setup the project workspace,Created the project folder, Checked development tools version, Created the complete folder and file structure for all missions,Prepared the root README and Published the repository.

---

## 2. Tools Checked and Versions
Both Python and Git were checked through the terminal to confirm they are installed and functional:

| Tool | Version Verified | Command Used |
| :--- | :--- | :--- |
| **Git** | `git version 2.55.0` | `git --version` |
| **Python** | `Python 3.9.6` | `python3 --version` |

---

## 3. Folders and Files Created
The following file and folder hierarchy was prepared in the project root:

```text
digital-detective-8495/
├── README.md
├── mission-00-setup/
│   └── README.md
├── mission-01-computer-basics/
│   └── README.md
├── mission-02-terminal/
│   └── README.md
├── mission-03-operating-system/
│   └── README.md
├── mission-04-programs/
│   └── README.md
├── mission-05-numbers-data/
│   ├── README.md
│   └── number_converter.py
├── mission-06-git-github/
│   └── README.md
├── mission-07-networking/
│   └── README.md
├── mission-08-final-report/
│   └── README.md
└── evidence/
```

---

## 4. Brief Explanation

### What is a Repository?
A Git repository is a digital storage space that holds all project files, assets, and documentation, along with the complete history of every change made over time.It allows developers to track, get back form mistakes, collaborate safely.

### Why the Folder Structure is Organised by Mission
Organizing the repository mission-by-mission provides:
- Changes and progress can be committed and reviewed independently per mission without changing unrelated files.
- Each mission maintains its own `README.md` for specific notes and conclusions.

---

## 5. Setup Difficulties and Resolutions
- **Issue:** Git does not track `evidence/` which is completely empty directory by default.
- **Solution:** Initialized empty markdown files inside each mission folder and added a `.gitkeep` placeholder inside `evidence/` so Git correctly staged and pushed the entire workspace.
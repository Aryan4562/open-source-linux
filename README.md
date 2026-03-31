# OSS Audit — Python
### The Open Source Audit | VITyarthi | Open Source Software Course

<table>
<tr><td><strong>Student Name</strong></td><td>Aryan Singh</td></tr>
<tr><td><strong>Roll Number</strong></td><td>24MIM10121</td></tr>
<tr><td><strong>Chosen Software</strong></td><td>Python (PSF License)</td></tr>
<tr><td><strong>Course</strong></td><td>Open Source Software — Units 1–5</td></tr>
<tr><td><strong>Slot</strong></td><td>A24</td></tr>
</table>

---

## Why Python?

Python was created by Guido van Rossum in 1989 out of frustration with closed, limited
programming tools. He wanted a language that was readable, powerful, and — critically —
free for anyone to use, modify, and share. Over 30 years later, it is the most widely used
programming language in the world and remains open source under the Python Software
Foundation License.

---

## Repository Structure

```
oss-audit-[rollnumber]/
│
├── script1_system_identity.sh       # System info welcome screen
├── script2_package_inspector.sh     # FOSS package checker with case statement
├── script3_disk_auditor.sh          # Directory permissions and size audit
├── script4_log_analyzer.sh          # Log file keyword counter
├── script5_manifesto_generator.sh   # Interactive open source manifesto creator
│
└── README.md                        # This file
```

---

## Script Descriptions

### Script 1 — System Identity Report
**File:** `script1_system_identity.sh`

Displays a formatted welcome screen with:
- Linux distribution name and kernel version
- Logged-in user and home directory
- System uptime and current date/time
- The open-source licence covering the OS (GPL v2)

**Key shell concepts:** Variables, `echo`, command substitution `$()`, string formatting

---

### Script 2 — FOSS Package Inspector
**File:** `script2_package_inspector.sh`

Checks whether Python 3, git, vlc, and firefox are installed on the system. Retrieves
version and package description using `dpkg`. Uses a `case` statement to print a
philosophy note about each package's open-source significance.

**Key shell concepts:** Functions, `if-then-else`, `case` statement, `dpkg -l`, pipe with `grep`, `awk`

---

### Script 3 — Disk and Permission Auditor
**File:** `script3_disk_auditor.sh`

Loops through standard Linux system directories and Python-specific installation directories.
Reports size, permissions, owner, and group for each. Includes a short explanation of why
permissions matter in the context of open-source security.

**Key shell concepts:** Arrays, `for` loop, `ls -ld`, `du -sh`, `awk`, `cut`, `-d` and `-e` file tests, `printf`

---

### Script 4 — Log File Analyzer
**File:** `script4_log_analyzer.sh`

Reads a log file line by line, counting how many lines match a keyword. Prints total lines,
match count, percentage, and the last 5 matching lines. Includes retry logic for empty files.

**Key shell concepts:** `while IFS= read -r`, counter variables, `$1`/`$2` arguments,
`grep -i`, `tail`, input redirection `<`, do-while style retry pattern

**Usage:**
```bash
./script4_log_analyzer.sh /var/log/syslog error
./script4_log_analyzer.sh /var/log/auth.log WARNING
```

---

### Script 5 — Open Source Manifesto Generator
**File:** `script5_manifesto_generator.sh`

Asks the user 3 interactive questions and generates a personalised open-source philosophy
statement saved to a `.txt` file. Demonstrates the alias concept through comments.

**Key shell concepts:** `read -p` for interactive input, string concatenation, `>` and `>>`
for file writing, `date` command, alias concept demonstration

---

## How to Run the Scripts

### Step 1 — Clone the repository
```bash
git clone https://github.com/[your-username]/oss-audit-[rollnumber].git
cd oss-audit-[rollnumber]
```

### Step 2 — Make all scripts executable
```bash
chmod +x *.sh
```

### Step 3 — Install dependencies (Ubuntu/Debian)
```bash
sudo apt update
sudo apt install python3 python3-pip lsb-release git -y
```

### Step 4 — Run each script

```bash
# Script 1: System Identity Report
./script1_system_identity.sh

# Script 2: FOSS Package Inspector
./script2_package_inspector.sh

# Script 3: Disk and Permission Auditor
./script3_disk_auditor.sh

# Script 4: Log File Analyzer (requires a log file argument)
./script4_log_analyzer.sh /var/log/syslog error

# Script 5: Open Source Manifesto Generator (interactive — it will ask you questions)
./script5_manifesto_generator.sh
```

---

## Dependencies

| Dependency | Purpose | How to install |
|-----------|---------|----------------|
| `bash` (v4+) | Shell interpreter | Pre-installed on all Linux systems |
| `python3` | Main audited software | `sudo apt install python3` |
| `lsb-release` | Detect Linux distro name | `sudo apt install lsb-release` |
| `dpkg` | Package info (Debian/Ubuntu) | Pre-installed |
| `coreutils` | `date`, `du`, `ls`, `cut`, `tail` | Pre-installed |
| `git` | Version control | `sudo apt install git` |

> All scripts tested on **Ubuntu 22.04 LTS** inside a VirtualBox virtual machine.

---

## References

- Python Software Foundation — https://www.python.org/psf/
- PSF License — https://docs.python.org/3/license.html
- GNU Free Software Definition — https://www.gnu.org/philosophy/free-sw.html
- The Cathedral and the Bazaar — http://catb.org/~esr/writings/cathedral-bazaar/
- CPython source code — https://github.com/python/cpython
- Choose a License — https://choosealicense.com
- Linux man pages — https://man.cx

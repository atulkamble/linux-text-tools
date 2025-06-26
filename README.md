# 📄 Text Handling in Linux (CLI)

In Linux, handling and processing text files is an essential system administration and scripting task. Linux provides powerful command-line tools for viewing, searching, filtering, and transforming text data. These tools can work individually or together through **pipes** (`|`) to build complex workflows.

---

## 📖 Common Text Handling Commands

### 1️⃣ **cat** — Display Content

* **Usage:** Concatenate and display file contents.

```bash
cat filename.txt
```

* Combine multiple files:

```bash
cat file1.txt file2.txt > combined.txt
```

---

### 2️⃣ **tac** — Reverse `cat`

* Displays content in reverse line order.

```bash
tac filename.txt
```

---

### 3️⃣ **nl** — Add Line Numbers

```bash
nl filename.txt
```

---

### 4️⃣ **head** — Show Top Lines

* Display the first **n** lines (default is 10)

```bash
head -n 5 filename.txt
```

---

### 5️⃣ **tail** — Show Bottom Lines

* Display the last **n** lines

```bash
tail -n 5 filename.txt
```

* Monitor file in real-time:

```bash
tail -f /var/log/messages
```

---

### 6️⃣ **more** and **less** — Page-wise Viewing

* `more` scrolls down one page at a time:

```bash
more filename.txt
```

* `less` allows scrolling both ways:

```bash
less filename.txt
```

---

## 🔍 Searching Text

### 7️⃣ **grep** — Pattern Matching

* Search for specific patterns in a file:

```bash
grep "error" /var/log/messages
```

* Case-insensitive search:

```bash
grep -i "error" file.txt
```

* Count occurrences:

```bash
grep -c "error" file.txt
```

* Search recursively in directories:

```bash
grep -r "config" /etc/
```

---

## 🔧 Text Transformation

### 8️⃣ **cut** — Extract Specific Columns

* Extract column(s) using delimiter:

```bash
cut -d ":" -f 1 /etc/passwd
```

---

### 9️⃣ **awk** — Field-wise Text Processing

* Print specific fields:

```bash
awk '{print $1, $3}' file.txt
```

* Conditional processing:

```bash
awk '$3 > 50 {print $1, $3}' file.txt
```

---

### 🔟 **sed** — Stream Editor

* Find and replace:

```bash
sed 's/oldtext/newtext/g' file.txt
```

* Delete specific line:

```bash
sed '3d' file.txt
```

---

## 📊 Sorting and Counting

### 1️⃣1️⃣ **sort** — Sort Text Data

* Sort alphabetically:

```bash
sort file.txt
```

* Sort numerically:

```bash
sort -n numbers.txt
```

---

### 1️⃣2️⃣ **uniq** — Filter Unique Lines

* Remove duplicates:

```bash
uniq file.txt
```

* Count occurrences:

```bash
uniq -c file.txt
```

---

### 1️⃣3️⃣ **wc** — Count Words, Lines, Characters

```bash
wc filename.txt
```

* Just word count:

```bash
wc -w filename.txt
```

* Just line count:

```bash
wc -l filename.txt
```

---

## 🔗 Combining Commands with Pipes

Example: Find number of errors in a log:

```bash
grep "error" /var/log/messages | wc -l
```

---

## 📌 Summary

| Command       | Purpose                      |
| :------------ | :--------------------------- |
| `cat`         | Display file content         |
| `tac`         | Display in reverse           |
| `head`/`tail` | Show start or end of file    |
| `more`/`less` | Page-wise file viewing       |
| `grep`        | Pattern search               |
| `cut`         | Extract fields               |
| `awk`         | Field-wise processing        |
| `sed`         | Text stream editing          |
| `sort`        | Sort data                    |
| `uniq`        | Remove duplicate lines       |
| `wc`          | Count words/lines/characters |

---

## 📚 Pro Tip

Combine these tools via pipes to perform advanced text processing in one line, making Linux extremely efficient for system logs, data files, and configuration management.

---



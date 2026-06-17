# GitHub Upload Commands

Use these commands from inside the `digital-logic-final-assignment` folder.

## 1. Initialize Git

```bash
git init
git branch -M main
git add .
git commit -m "Add digital logic final assignment"
```

## 2. Create a GitHub Repository

Recommended repository name:

```text
digital-logic-final-assignment
```

Recommended description:

```text
First-year Digital Logic coursework project covering comparators, JK flip-flops, counters, K-maps, and seven-segment display systems.
```

Recommended topics:

```text
digital-logic, logic-design, jk-flip-flop, karnaugh-map, counter, seven-segment-display, comparator, coursework
```

## 3. Connect Local Folder to GitHub

Replace `YOUR_USERNAME` with your GitHub username.

```bash
git remote add origin https://github.com/YOUR_USERNAME/digital-logic-final-assignment.git
git push -u origin main
```

## 4. If the Remote Already Exists

```bash
git remote set-url origin https://github.com/YOUR_USERNAME/digital-logic-final-assignment.git
git push -u origin main
```

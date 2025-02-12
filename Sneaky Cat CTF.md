# Sneaky Cat CTF 🐱🔍

**Authored by:** crow

website:[SNEAKY Cat CTF](https://ctfguide.com/challenges/2860b99e-d07b-4620-abe5-37fef4a32faf)

## Challenge Description

The **Sneaky Cat** challenge involved analyzing an image of a ginger cat. The description hinted that something was hidden within the image, and the goal was to extract the hidden flag.

## Tools Used

- **strings** – Extracts readable text from binary files.
- **grep** – Filters text based on patterns.

## Steps to Solve

### 1️⃣ Initial Analysis

The provided file was an image (`7.jpg`). The first step was to check for hidden text inside the image.

### 2️⃣ Extracting Strings

Using the `strings` command to pull readable text from the image:

```bash
strings /home/user/Downloads/7.jpg
```

### 3️⃣ Filtering for the Flag

To refine the output, `grep` was used to search for "flag" (case-insensitive):

```bash
strings /home/user/Downloads/7.jpg | grep -i "flag"
```

### 4️⃣ Finding the Flag

This command returned:

```
flag:*******************
```

The flag was hidden in plain text within the image!

## Conclusion 🏆

This challenge was solved using basic command-line tools to extract hidden data. The flag was in plain sight, making it a fun and straightforward challenge.

## Lessons Learned

✔️ Start with simple tools like `strings` and `grep` when analyzing files.\
✔️ Sometimes, the easiest approach is the correct one—flags can be hidden in plain sight!


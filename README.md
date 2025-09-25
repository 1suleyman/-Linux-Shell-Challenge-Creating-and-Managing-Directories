# 🌐 Linux Shell Challenge: Creating and Managing Directories

In this challenge, I learned how to navigate the shell, create nested directories, move and rename directories, and delete them using Linux commands. This README generalizes the experience so it can be applied to any user.

---

## 📋 Challenge Overview

**Goal:**

* Identify the home directory of a user
* Create multiple nested directories using `mkdir -p`
* Move and rename directories
* Delete directories recursively

**Learning Outcomes:**

* Understanding directory structure and absolute paths
* Using `mkdir`, `mv`, and `rm` commands effectively
* Managing nested directories in Linux
* Understanding arguments vs commands

---

## 🛠 Step-by-Step Journey

### Step 1: Identify the Home Directory

**Task:** Determine the home directory of a user.

**Commands:**

```bash
pwd           # Shows current directory
echo $HOME    # Shows the home directory for the current user
```

* `pwd` shows your current working directory
* `echo $HOME` prints the full path to your home directory

💡 **Tip:** On most Linux systems, user home directories are under `/home/<username>`.

---

### Step 2: Create Nested Directories

**Task:** Create directories for different animal categories:

* birds
* fish → salmon
* mammals → elephant, monkey
* reptile → snake, frog
* amphibian → salamander

**Commands:**

```bash
# Create birds
mkdir -p /home/<user>/birds

# Create fish and salmon
mkdir -p /home/<user>/fish/salmon

# Create mammals, elephant and monkey in one go
mkdir -p /home/<user>/mammals/elephant /home/<user>/mammals/monkey

# Create reptiles, snake and frog in one go
mkdir -p /home/<user>/reptile/snake /home/<user>/reptile/frog

# Create amphibians, salamander
mkdir -p /home/<user>/amphibian/salamander
```

💡 **Tip:** Using `-p` allows creation of parent directories as needed. Multiple directories can be created in a single command separated by spaces.

---

### Step 3: Move a Directory

**Task:** Move the `frog` directory from `reptile` to `amphibian`.

**Command:**

```bash
sudo mv /home/<user>/reptile/frog /home/<user>/amphibian/
```

* Using `sudo` ensures permission to move directories outside the user’s home directory if required.
* Always specify **absolute paths** to avoid mistakes.

---

### Step 4: Rename a Directory

**Task:** Rename `snake` directory to `crocodile`.

**Command:**

```bash
sudo mv /home/<user>/reptile/snake /home/<user>/reptile/crocodile
```

💡 **Tip:** `mv` works both for moving and renaming directories.

---

### Step 5: Delete a Directory

**Task:** Delete the `reptile` directory and all its contents.

**Command:**

```bash
sudo rm -r /home/<user>/reptile
```

* `-r` recursively deletes all files and subdirectories.
* Be careful with `sudo rm -r` — it permanently deletes content.

✅ **Checkpoint:** All directories created, moved, renamed, and deleted successfully.

---

### Step 6: Verification

List directories in the home directory to confirm structure:

```bash
ls /home/<user>
```

Expected structure:

```
birds
fish
mammals
amphibian
```

*Reptile should no longer exist, and `frog` should now be under `amphibian`.*

---

## 💡 Notes / Tips

* **Absolute vs Relative Paths:** Using absolute paths (`/home/<user>/`) avoids mistakes related to current working directory.
* **`mkdir -p`** simplifies creating nested directories in one command.
* **`mv`** can move or rename directories depending on the arguments.
* **`rm -r`** is powerful but destructive — double-check paths before running.
* **Experimentation:** Using `ls` and `pwd` often helps verify commands before executing them.

---

## ✅ Summary Table

| Step                      | Status | Key Notes                            |
| ------------------------- | ------ | ------------------------------------ |
| Identify home directory   | ✅      | `pwd` and `echo $HOME`               |
| Create nested directories | ✅      | `mkdir -p` creates parents as needed |
| Move directory            | ✅      | Moved `frog` to `amphibian`          |
| Rename directory          | ✅      | `snake` → `crocodile`                |
| Delete directory          | ✅      | Deleted `reptile` recursively        |
| Verify structure          | ✅      | Checked with `ls`                    |

---

## ✅ References

* [Linux mkdir Command](https://linuxize.com/post/linux-mkdir-command/)
* [Linux mv Command](https://linuxize.com/post/linux-mv-command/)
* [Linux rm Command](https://linuxize.com/post/linux-rm-command/)
* [Linux Home Directory Basics](https://www.geeksforgeeks.org/home-directory-in-linux/)


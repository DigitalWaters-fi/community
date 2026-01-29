# bash for file management
## Objectives:
In reproducible scientific computing, the goal is to permit someone to recreate our scientific workflows step by step. This tutorial will help you to build reproducible scientific workflows by teaching you to interact with your computer using text commands, instead of your mouse and graphical user interfaces. These text commands represent a record of what software was used, what operations were run, and on what data that is *automatable*, or capable of running without human interaction.

By the end of this tutorial you will be able to:
1. Define terminal, shell, and bash; and explain why we use them for scientific computing.
2. Open a terminal window on the DIWA DataLab.
3. Identify text-based file paths to documents on your computer.
4. Interpret file path structure of documents/data on online geodatabases.
5. Run bash commands to navigate files on your computer.

Please see the companion file "bash-cheat-sheet.md" to keep track of these common commands.

## Part 1: The language of computers
First, some definitions.
* **Terminal**: A terminal is an input/output device or software interface that allows a user to communicate with an operating system or remote computer using typed commands rather than graphical controls. In the DIWA DataLab, when we open a **terminal**, we open a window based-interface to type commands that emmulate common interactions you have with your computer using a mouse.
* **Shell**: The word shell in this context has two meanings. First, and most commonly used, the shell is the language that you type in the terminal. It is the program that interprets commands to your computer. Just to make things confusing, shell also refers to a specific type of shell (this would be similar to someone naming a car brand "Car"). If you have a Windows operating system, your shell is called *CMD*. If you have a Mac or Linux operating system, your shell is called "bash." Our DIWA DataLab has a Linux operating system, so we will learn commands to the bash shell.
* **CLI (Command Line Interface)**: On your laptop or PC, there are two ways to interact with your shell. If you are typing commands in to the terminal using your keyboard, you are interacting with your shell's CLI.
* **GUI (Graphical User Interface)**: The other way to interact with your shell involves a lot more use of your computer's mouse. If you are navigating files and running software by pointing and clicking on graphic icons displayed on your screen, you are using your shell's GUI (note GUI is pronounced like the English word "gooey")

The **CLI** and **GUI** are two different ways of interacting with your shell, but they do the same thing. Every time you point and click on an icon to complete a task on your computer, there is a corresponding text command that could be typed into the **CLI**, achieving the same result. 

*Figure 1.1: A "teletypewriter" was the first kind of terminal. Rather than a screen you'd have a literal typewriter in front of you. When you type on it, you're seeing the text on a piece of paper AND inputting that text into a computer. When that computer replies, you'll see the typewriter automatically type on the same paper.*

### Shells in scientific computing
To recap, the **shell** is the program that takes commands and gives them to your computer (your computer’s language).

There is a **shell** named shell, also known as Unix or sh, which is the most common language spoken by computers.The **shell** is the original Unix command interpreter (dating back to the 1970s).

**Bash**, was released in 1989, is a later, GNU-developed (aka open source) shell that extended and standardized earlier shells like `sh` with more features and scripting capabilities.

*Quick punny title interlude: Bourne Again SHell gives a cheeky nod the Stephen Bourne, who originally developed shell, and suggests that it was "born again" with new features. One of this "new" features is its "GNU-ness". Here, GNU (pronounced like the English word "new") stands for “GNU’s Not Unix” — a recursive acronym coined to emphasize that while GNU is Unix-like, it is completely free software and not derived from the proprietary Unix code.*

Our DIWA DataLab, like most high performance computing/scientific computing systems, speaks *bash*. We pick this GNU shell because we care a lot about this free and open source component.

Because *bash* was developed from *shell*, *bash* can always speak *shell*, but *shell* doesn't have all the commands you can access with *bash*. Still, nowadays ”shell script” and “bash script” are used interchangeably; assume “sh” = “bash.”

As mentioned above, Windows computers have their own shell called *CMD.* *CMD* doesn’t speak *Bash*, and *Bash* doesn’t speak *CMD*. This because CMD is a proprietary shell: it generates file types that can only be read by Windows machines. Bash is an open-source shell, it generates file types that can be read by all machines (including Windows)

**Why does this proprietary verses open source thing matter (keywords: version control and reproducible research)?**

### Common pitfalls you might encounter moving data/files/code developed in a Windows OS to a Linux OS (like our DIWA DataLab)
These differences between bash and cmd means that Windows users might encounter some unexpected translation issues when they move files to a scientific computing. Common things to look out for:
Moving code and data from **Windows** to **Linux** can be straightforward, but there are several common pitfalls that often trip people up. I’ll break them down clearly:


1. **File paths and separators**

* **Windows** uses `C:\Users\Name\Documents\file.txt`
* **Linux** uses `/home/name/file.txt`
* Forward slashes `/` vs backslashes `\` can break scripts.
  **Tip:** Use `/` in code whenever possible; many languages handle it cross-platform.

2. **Line endings**

* Windows: `CRLF` (`\r\n`)
* Linux: `LF` (`\n`)
* Scripts may fail on Linux due to extra `\r` characters.
  **Fix:** Convert files with:

  ```bash
  dos2unix filename
  ```
(you will type the actual filename in where it says filename above)

3. **Case sensitivity**

* Windows filenames are **case-insensitive** (`File.txt` = `file.txt`)
* Linux is **case-sensitive** (`File.txt` ≠ `file.txt`)
* Script imports or file references may break if capitalization isn’t exact.

4. **Path environment differences**

* Windows: uses `PATH` with `;` separators, backslashes
* Linux: uses `PATH` with `:` separators, forward slashes
* Scripts that reference absolute paths may need updating.

5. **Dependencies and libraries**

* Windows binaries (DLLs) won’t run on Linux.
* External software may need Linux equivalents or source compilation.
* Python/Node/etc.: you may need to reinstall dependencies (`pip install -r requirements.txt`).

6. **Shell differences**

* Windows batch scripts (`.bat`) are **not compatible** with Linux shells.
* PowerShell scripts need Linux PowerShell installed or rewritten for Bash/zsh.
* Shell syntax differences:

  ```bash
  # Windows batch
  set VAR=hello
  echo %VAR%

  # Bash
  VAR=hello
  echo $VAR
  ```

7. **File permissions and ownership**

* Windows NTFS stores permissions differently; Linux users may need to adjust ownership after copying:

  ```bash
  chown -R username:group folder/
  chmod -R 755 folder/
  ```

8. **Hidden/system files**

* Windows: files starting with `.` are not hidden; Linux treats them as hidden.
* Some config files might not copy correctly if not explicitly included.

**Quick tips for smoother migration**
* Convert line endings: `dos2unix`
*  Check filename case
*  Reinstall dependencies for Linux
5. Test scripts in a Linux environment before full deployment

---

If you want, I can make a **“migration checklist”** — a concise step-by-step to move Windows code and data to Linux **without breaking anything**. It’s basically a one-page cheat sheet for developers.

Do you want me to make that?


## Part 2: getting to know your terminal
### To access the terminal (CLI for your shell) on your computer:
* WINDOWS: Press Windows Key + r, type “cmd”, Enter
* Mac: Press Command + space, type “terminal”, Enter
* Ubuntu (Linux): Press Ctrl + Alt + T
* DIWA DataLab: in a Notebook image, File > New > Terminal


*Figure 2.1: Accessing terminal in DIWA DataLab*

### Using terminal to understand system settings:
In a Microsoft or Mac, you can use "Settings" to learn important information about your computer.

#### Check what shell you are running:
If you type the following text into your terminal, it will tell you which shell you are running 

`echo $SHELL`

*Figure 2.2: On the DIWA DataLab, our shell is *bash*


#### Check available storage
To show disk usage for all mounted filesystems

df -h

# Show size of files and directories in current directory
du -sh *


### Launching 

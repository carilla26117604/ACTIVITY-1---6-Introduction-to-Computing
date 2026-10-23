# Republic of the Philippines

**Sorsogon State University**\
**College of Information and Communications Technology**\
Bulan Campus\
Zone 8, Bulan, Sorsogon\
Tel. No.: 056 311-0103 \| Email: cict@sorsu.edu.ph

# CC 101 Laboratory Activity: Exploring the Windows Command Line

  -----------------------------------------------------------------------
  Item                                Details
  ----------------------------------- -----------------------------------
  Course                              CC 101 Introduction to Computing
                                      (BSCS 1st Year)

  Course Outcome                      CO2: Identify the functions and
                                      relationships of major hardware and
                                      software components

  Output                              Command Line Exploration
                                      Documentation (PDF)

  Estimated time                      2 to 2½ hours

  Reference                           CC 101 Lecture Notes: Exploring the
                                      Windows Command Line
  -----------------------------------------------------------------------

## Instructions

Follow every step in order, take the screenshots marked
**\[Screenshot\]**, and answer the questions marked **\[Answer\]** in
your documentation.

### Before you start

-   You need a Windows 10 or 11 computer. No administrator rights are
    needed.
-   To take a screenshot, press **Windows + Shift + S**, drag over the
    terminal window, then paste it (**Ctrl + V**) into your
    documentation.
-   Replace the sample values (Juan Dela Cruz, BSCS 1-1) with your own
    details.
-   Type every command yourself. Do not copy and paste; typing is how
    you learn.

## Part A: Open the Two Shells

1.  Press **Windows + R**, type `cmd`, and press Enter. Type `cls` and
    press Enter.
2.  Type `echo Juan Dela Cruz, BSCS 1-1` (your own name and section) and
    press Enter.

**Figure A1**

3.  Press **Windows + R**, type `powershell`, and press Enter. Type the
    same echo command, but put the text in quotation marks:
    `echo "Juan Dela Cruz, BSCS 1-1"`. PowerShell treats the comma as a
    list separator without them.

**Figure A2**

> The two prompts are a little different because PowerShell has "PS" at
> the beginning, while Command Prompt does not. The path shows the drive
> and the folder where I am currently working. The "\>" symbol is where
> I can type my commands. Both of them basically show my current
> location and allow me to enter commands.

**A-Q1.** Compare the two prompts. What is different, and what does each
part of the Command Prompt prompt mean?

## Part B: Inspect Your System (Command Prompt)

Use the Command Prompt window for Parts B to D.

1.  Run these commands one at a time: `whoami`, then `hostname`, then
    `ver`.

**Figure B1**

2.  Run the command below. It may take 10 to 30 seconds.

``` cmd
systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type" /C:"Total Physical Memory"
```

**Figure B2**

3.  Run `ipconfig`. Find the adapter that shows an IPv4 Address.

**Figure B3**

**\[Answer\] B-Q1.** Complete this table in your documentation using
your results:

  Item                           Your result
  ------------------------------ ----------------------------
  Logged-in account (`whoami`)   desktop-2gq05ai
  Computer name (`hostname`)     DESKTOP-2GQ05AI
  OS name                        Microsoft Windows 11 Pro
  OS version                     10.0.21996 N/A Build 21996
  System type (x64 or ARM)       x64-based PC
  Total physical memory (RAM)    7,973 MB
  IPv4 address                   192.168.56.1

> It filters the information from systeminfo, and instead of showing
> everything, it only shows specific information I was looking for.

**B-Q2.** The `|` symbol in step 2 is called a pipe. Run `systeminfo`
alone and compare. In your own words, what did `| findstr` do?

## Part C: Build a Folder Structure

1.  Go to your user folder and create the lab folders:

``` cmd
cd %USERPROFILE%
mkdir CC101-Lab
cd CC101-Lab
mkdir Notes Projects Screenshots
```

2.  Create a text file about yourself (use your own details):

``` cmd
echo Name: Juan Dela Cruz > profile.txt
echo Section: BSCS 1-1 >> profile.txt
echo Favorite app: YouTube >> profile.txt
type profile.txt
```

**Figure C1** (show all commands and the output of `type`)

3.  Run `tree /F` to display your folder structure.

**Figure C2**

4.  Open File Explorer, go to `C:\Users\(your account)\CC101-Lab`, and
    open `profile.txt` in Notepad.

**Figure C3**

> If I use `>` instead of the double one, the previous content of the
> file will be replaced by the new text. The `>>` means new text without
> removing what is already there.

**C-Q1.** What would happen if you used `>` instead of `>>` in the
second echo line? Test it on a new file (`test.txt`) and explain.

## Part D: Copy, Rename, and Delete Files

``` cmd
copy profile.txt Notes\profile-copy.txt
cd Notes
ren profile-copy.txt about-me.txt
echo This file will be deleted > temp.txt
dir
del temp.txt
dir
cd ..
tree /F
```

**Figure D1** (from `copy` to the first `dir`) and **Figure D2** (from
`del` to `tree /F`)

> No, it was not in recycle bin after I used the `del` command. It was
> deleted directly from the command line. This shows that when I delete
> a file using this command line, it normally does not go in the recycle
> bin.

**D-Q1.** After `del temp.txt`, check your Recycle Bin. Is `temp.txt`
there? What does this tell you about deleting files from the command
line?

## Part E: Explore PowerShell

Switch to the PowerShell window.

1.  Go to your lab folder and list and read its files:

``` powershell
cd $HOME\CC101-Lab
Get-ChildItem
Get-Content profile.txt
$PSVersionTable
```

**Figure E1**

2.  Run `Get-Help Get-ChildItem`. If PowerShell asks whether to run
    `Update-Help`, type `N` and press Enter.

**Figure E2**

3.  Take the last three digits of your student ID number (for example,
    `2025-00347` → `347`). Convert it with PowerShell:

``` powershell
[Convert]::ToString(347, 2)
[Convert]::ToString(347, 8)
'{0:X}' -f 347
```

**Figure E3**

> In decimal is 604, in binary is 1001011100, in octal is 1134, and in
> hexadecimal is 25c.

**E-Q1.** Write your number in decimal, binary, octal, and hexadecimal.
Keep this; you will verify it by hand in Week 5.

## Part F: Discover a New Command

1.  In Command Prompt, type `help` to see a list of commands.
2.  Choose one command that was not taught in this lesson and is safe to
    run (for example: `date /t`, `time /t`, `tasklist`, `vol`, or
    `color 0A`).
3.  Read its help with `command /?` (for example, `tasklist /?`), then
    run it.

**Figure F1** (help output) and **Figure F2** (command result)

**My chosen command is `systeminfo`, and its main function is to display
a comprehensive list of detailed configuration information about my
computer and its operating system.**

**Part G: Reflection**

**\[Answer\]** Answer in 3 to 5 sentences each.

### 1. G-Q1. Which task in this activity was faster in the CLI than in the GUI? Which was easier in the GUI? Explain why.

For me, creating, copying, renaming, and deleting files was faster
because I could just type the commands. Using GUI was easier when I
needed to look for folders or open files because I could see everything
on the screen. And I think both are useful but, it maybe depend on the
task I want to perform.

### 2. G-Q2. What error did you encounter (if any), what caused it, and how did you fix it?

Some command line that I put it in wrong spelling and I resolve it by
double checking it again so that it not can cause an error again. With
this, I manage to continue using the command line. And also, to a
further error I encounter I ask AI to help me resolve it.

### 3. G-Q3. Give one real-world job or situation in computing where knowing the command line would be important.

Being a web developer, so it make it very easy for them to get what they
need just using the command line. And also, this is very helpful to not
use your time just finding data that you need from the applications.
With this command, you can just type the data name and the command line
and you will get it. Finally, we can say that it became their partner in
creating web application.

## Documentation and Submission

Submit one PDF that records what you did, what the computer showed, and
what you learned. Someone reading it should be able to repeat your work.

### Required Contents (in this order)

1.  Cover page: activity title, your full name, student ID, section,
    date performed, and instructor's name.
2.  Introduction (3 to 5 sentences): what the command line is and the
    purpose of this activity, in your own words.
3.  Procedure and results, Parts A to F: for each part, a short heading,
    the commands you typed, the labeled screenshots, and your answers to
    that part's **\[Answer\]** questions.
4.  Commands learned table: every command you used and what it does, in
    your own words.
5.  Reflection: your answers to G-Q1 to G-Q3.

### Formatting Rules

  ----------------------------------------------------------------------------
  Item                                Requirement
  ----------------------------------- ----------------------------------------
  File type                           PDF (write in Word or Google Docs, then
                                      export as PDF)

  File name                           `CC101_CLI-Lab_Lastname_Firstname.pdf`

  Font                                Arial or Calibri, 11 pt; commands in
                                      Consolas or Courier New

  Screenshots                         Crop to the terminal window; text must
                                      be readable. Label each one below the
                                      image, e.g., "Figure B2. Filtered
                                      systeminfo output"

  Personal details                    Your own name, section, and student ID
                                      must appear in Figures A1, C1, and E3

  Total screenshots                   16 (A1--A2, B1--B3, C1--C3, D1--D2,
                                      E1--E3, F1--F2)
  ----------------------------------------------------------------------------

### Sample Commands Learned Table

  -----------------------------------------------------------------------
  Command                 Shell                   What it does
  ----------------------- ----------------------- -----------------------
  `mkdir Notes`           Command Prompt          Creates a folder named
                                                  Notes in the current
                                                  folder

  `type profile.txt`      Command Prompt          Displays the contents
                                                  of profile.txt
  -----------------------------------------------------------------------

### Submission

-   Upload the PDF to the activity page in the course LMS before the
    deadline your instructor sets.
-   Outputs must be your own work. Identical screenshots or answers will
    be treated as plagiarism under the class policy.
-   Keep your `CC101-Lab` folder; later activities may build on it.

## Grading Rubric

The documentation is scored out of 100 points and counts under
Laboratory: Project.

  -----------------------------------------------------------------------------------
  Criterion                 Points Full marks           Partial marks Low marks
  -------------- ----------------- -------------------- ------------- ---------------
  Completeness                  30 All 16 labeled,      1 to 4        5 or more
  of procedure                     readable             screenshots   screenshots
                                   screenshots; every   missing or    missing
                                   part A to F          unreadable    
                                   documented                         

  Accuracy of                   20 System-information   Minor errors  Many errors, or
  results                          table complete;      or 1 to 2     results not the
                                   commands and         missing       student's own
                                   conversions correct  values        
                                   and personalized                   

  Answers to                    20 Correct, clear, in   Mostly        Missing,
  guide                            the student's own    correct but   incorrect, or
  questions (A                     words                brief or      copied
  to F)                                                 vague         

  Reflection                    15 Specific, honest,    General       Missing or
  (G-Q1 to G-Q3)                   and linked to the    statements    off-topic
                                   activity             with few      
                                                        specifics     

  Organization                  15 Follows the required Some rules    Disorganized;
  and formatting                   order, naming, and   not followed  wrong file type
                                   formatting rules;                  or name
                                   commands learned                   
                                   table complete                     

  **Total**                **100**                                    
  -----------------------------------------------------------------------------------

# Activity 6

```text
Republic of the Philippines
                                      Sorsogon State University
                                 COLLEGE OF INFORMATION
                             AND COMMUNICATIONS TECHNOLOGY
                                            Bulan Campus
                                          Zone 8, Bulan, Sorsogon
                         Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph




                             CC 101 – Introduction to Computing
 “From Problem to README”: Designing a Number-System Converter
                 and Documenting It in Markdown
 Name: Francine L. Carilla                            Block: BSCS 1-1

 Computer Unit Used (Desktop/Laptop, brand):                      Date: 10/20/2026
 Laptop



    I. Objectives

At the end of this activity, you should be able to:
 • Analyze a number-system conversion problem by identifying its inputs, processes, loop
    condition, and outputs.
 • Write pseudocode using sequence, selection, and iteration.
 • Draw flowcharts using standard symbols and check them by tracing and testing with
    sample data.
 • Create a properly formatted README.md file in Markdown using Notepad, without an
    Internet connection.
 • Upload the README.md to your CC 101 GitHub Computing Portfolio repository (take-home
    part).


    II. Materials Needed

 • A computer running Windows 11 with Notepad (no network or Internet connection is
    needed in the laboratory)
 • This worksheet, a pencil, and a ruler (or a flowchart template) for drawing flowcharts
 • A USB flash drive, to bring your README.md home for uploading
 • For Part G only (outside the laboratory): any device with Internet access and a free GitHub
    account
 • Week 7 lecture notes, for reference on pseudocode, flowchart symbols, and Markdown
    syntax


    III. Background

Programmers do not start by typing code. They first analyze the problem, plan the solution as
pseudocode and a flowchart, and check it by hand. In this activity, you will design a program
that converts numbers between the decimal and binary number systems you learned in Week 5.
An algorithm can be written as pseudocode (English-like steps) or drawn as a flowchart (standard
symbols connected by arrows). Good work is also documented. On GitHub, the standard way to
introduce a project is a README.md file written in Markdown, a plain-text format that uses symbols
such as #, *, and - for headings, emphasis, and lists. Because Markdown is plain text, you can write
it in Notepad with no Internet connection and upload it to GitHub later.


    IV. Procedure

Part A – Analyze the Problem (Problem 1)
Problem 1: Decimal-to-Binary Converter. Design a program that asks the user for a whole number
in decimal (base 10) that is 0 or greater, converts it to binary (base 2), and displays the binary
result.
                                        Republic of the Philippines
                                       Sorsogon State University
                                COLLEGE OF INFORMATION
                            AND COMMUNICATIONS TECHNOLOGY
                                             Bulan Campus
                                          Zone 8, Bulan, Sorsogon
                         Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


Worked example (13 in decimal): 13 ÷ 2 = 6 r 1; 6 ÷ 2 = 3 r 0; 3 ÷ 2 = 1 r 1; 1 ÷ 2 = 0 r 1. Reading
the remainders from bottom to top gives 1101.
 1. Convert 13 and 25 to binary by hand using the method above, so you understand every
     step before writing the pseudocode.
 2. Complete Table 1: list the input, the output, the processes (operations), the decision or loop
     condition, and the variables you will need.

Part B – Write the Pseudocode
 3. In Box 1, write the pseudocode for Problem 1. Use START, INPUT, SET, WHILE … DO …
     ENDWHILE, IF … THEN … ELSE … ENDIF, DISPLAY, and END, and indent the steps inside the
     loop.
       Tip: Use MOD for the remainder of a division (13 MOD 2 = 1) and DIV for whole-number division
       (13 DIV 2 = 6). Each new remainder must be placed at the left of the binary digits found so far,
       for example SET binary = remainder + binary. Also decide what your algorithm should display
       when the input is 0.

Part C – Draw the Flowchart and Desk Check
 4. In Figure 1, draw the flowchart for Problem 1 using the standard symbols: oval (start/end),
     parallelogram (input/output), rectangle (process), and diamond (decision). Show the loop
     with an arrow going back to the decision, and label every decision exit Yes or No.
 5. Trace your pseudocode with the input 13 and fill in one row of Table 2 for each pass
     through the loop. The last column should end with 1101.
 6. Test your pseudocode and flowchart with the five inputs in Table 3. First convert each
     number by hand, then follow your pseudocode or flowchart step by step. If the two results
     do not match, find and correct the error in your pseudocode and flowchart.

Part D – Reverse Conversion (Problem 2)
Problem 2: Binary-to-Decimal Converter. Design a program that asks the user for a binary number
(entered as digits 0 and 1, such as 1101) and displays its decimal value. Use the positional (place
value) method from Week 5: starting from the rightmost digit, multiply each digit by its place value
(1, 2, 4, 8, 16, …) and add the products.
Worked example (1101 in binary): (1 × 1) + (0 × 2) + (1 × 4) + (1 × 8) = 1 + 0 + 4 + 8 = 13.
 7. In Box 2, write the pseudocode. You can take the rightmost digit with binary MOD 10 and
     remove it with binary DIV 10; the place value starts at 1 and doubles after each digit.
 8. In Figure 2, draw its flowchart.
 9. Test your pseudocode with the inputs in Table 4, comparing hand computation with the
     result of following your pseudocode.
 10.    Optional / Bonus: Extend Problem 1 so the user can choose the target base (2, 8, or 16).
     For base 16, remainders 10 to 15 must be displayed as the letters A to F. Write the extended
     pseudocode in the Bonus box.

Part E – Create Your README.md Offline
 11.   Show file extensions so that you can see the real file name. Press Windows + E to open File
     Explorer, then click View → Show → File name extensions (make sure it is checked).
 12.    In File Explorer, click Documents, then click New → Folder. Name the folder cc101-
     portfolio (all lowercase, with a hyphen) and press Enter. Open it and create two more
     folders inside: week07-algorithms and images.
 13.    Press the Windows key, type Notepad, and press Enter. If your Notepad shows a
     formatting toolbar, open the View menu and switch to the Markdown syntax view so the
     symbols you type stay visible.
 14.   Type the README content below. Replace everything in square brackets with your own
                                     Republic of the Philippines
                                    Sorsogon State University
                             COLLEGE OF INFORMATION
                         AND COMMUNICATIONS TECHNOLOGY
                                          Bulan Campus
                                        Zone 8, Bulan, Sorsogon
                       Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


  information, and replace the pseudocode with your pseudocode from Box 1. Keep the
  blank lines; they separate the parts.
      # CC 101 Computing Portfolio

      This repository contains my laboratory outputs and documentation for *CC 101 Introduction to
      Computing* at **Sorsogon State University – Bulan Campus**.

      ## About Me

      - **Name:** [Your full name]
      - **Program and Section:** BSCS 1-[section]
      - **Interests:** [two or three interests]
      - **Goal:** [one sentence about your goal as a computer science student]

      ## Course Information

      | Item | Details |
      | --- | --- |
      | Course | CC 101 Introduction to Computing |
      | Instructor | [Instructor's name] |
      | Academic Year | 2026–2027 |

      ## Portfolio Contents

      1. [Week 7 – Pseudocode and Flowcharts](week07-algorithms/)
      2. More activities will be added each week.

      ## Sample Pseudocode: Decimal to Binary

      ```
      [Paste your pseudocode from Box 1 here]
      ```

      ## My Workspace

      ![My laboratory computer](images/my-pc.jpg)

      ---

      *Last updated: [date in YYYY-MM-DD format]*

15.  Save the file. Click File → Save as. Go to Documents → cc101-portfolio. Type README.md
  as the File name, set Save as type to All files, make sure Encoding is UTF-8, and click Save.
16. Verify the file. In File Explorer, open the cc101-portfolio folder and confirm the file is
  named README.md, not README.md.txt. If it ends in .txt, right-click it, choose Rename, and
  remove .txt. Then press the Windows key, type cmd, press Enter, and run the commands
  below. Record the results in Table 5.
      cd %USERPROFILE%\Documents\cc101-portfolio
      dir
      type README.md
      Tip: If “The system cannot find the path specified” appears, your Documents folder may be
      inside OneDrive. Try cd %USERPROFILE%\OneDrive\Documents\cc101-portfolio instead.

17.   Optional preview: if your Notepad has a formatted view, switch to it from the View menu
                                        Republic of the Philippines
                                       Sorsogon State University
                                 COLLEGE OF INFORMATION
                             AND COMMUNICATIONS TECHNOLOGY
                                             Bulan Campus
                                           Zone 8, Bulan, Sorsogon
                          Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


    and note in Table 5 which elements appear formatted. Some elements, such as tables,
    images, and code blocks, may still appear as plain text. GitHub will display them correctly.
 18.     Copy the whole cc101-portfolio folder to your USB flash drive.

Part F – Peer Review
 19.   Exchange seats with a classmate. Open their README.md in Notepad and complete the
    checklist in Table 6 for their file. Write your name as the reviewer and return the worksheet.
    Fix any missing element in your own file before leaving.

Part G – Take-Home: Upload to GitHub
Do this part when you have Internet access (at home, on campus Wi-Fi, or on your phone's
browser in desktop mode).
 20.  Go to github.com and click Sign up. Use an email you check regularly and choose a
    professional username, such as your name. Verify your email address.
 21.   Click the + button at the upper right and choose New repository. Type cc101-portfolio as
    the Repository name, choose Public, and leave Add a README file unchecked. Click
    Create repository.
 22.  On the setup page, click the link uploading an existing file. Drag your README.md (and
    your week07-algorithms folder, if it has files) onto the page.
 23.  Under Commit changes, type Add initial README as the message and click Commit
    changes.
 24.   Open your repository's main page and check that the README appears formatted.
    Copy the repository URL (for example, https://github.com/username/cc101-portfolio),
    record it in Table 7, and submit it through the LMS.
         Note: GitHub does not store empty folders. The link to week07-algorithms will work after that
         folder contains at least one file, and the image will appear after you upload images/my-
         pc.jpg.


    V. Data and Findings

Table 1. Problem Analysis for Problem 1 (Part A)

 Item                            Your Answer

                                 The program asks the user for a whole number in decimal (0 or
 Restated problem (your
                                 greater), converts it to binary by dividing by 2 again and again,
 own words)
                                 and displays the binary result.

 Input                            A decimal whole number, n (n ≥ 0)


 Output                           The binary equivalent of n

                                 n MOD 2 to get the remainder; n DIV 2 to get the new n; put
 Processes (operations)
                                 each remainder at the left of the binary digits found so far

 Loop condition (when the
                                  The loop repeats while n > 0 and stops when n = 0
 loop stops)

 Variables needed                 n, remainder, binary

 13 and 25 in binary
                                  13 = 1101, 25 = 11001
 (computed by hand)
                                       Republic of the Philippines
                                      Sorsogon State University
                               COLLEGE OF INFORMATION
                           AND COMMUNICATIONS TECHNOLOGY
                                             Bulan Campus
                                          Zone 8, Bulan, Sorsogon
                         Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph




Box 1. Pseudocode for Problem 1 (Part B)

  START
   DISPLAY "Enter a whole number (0 or greater): "
   INPUT n
   IF n = 0 THEN
     SET binary = "0"
   ELSE
     SET binary = ""
     WHILE n > 0 DO
      SET remainder = n MOD 2
      SET binary = remainder + binary
      SET n = n DIV 2
     ENDWHILE
   ENDIF
   DISPLAY binary
 END



Figure 1. Flowchart for Problem 1 (Part C)
                                        Republic of the Philippines
                                       Sorsogon State University
                                COLLEGE OF INFORMATION
                            AND COMMUNICATIONS TECHNOLOGY
                                               Bulan Campus
                                           Zone 8, Bulan, Sorsogon
                          Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


Table 2. Trace of Problem 1 with Input 13 (Part C)

                                           n MOD 2
 Pass               n (before)                                  n DIV 2 (new n)      binary (so far)
                                           (remainder)

 1                  13                     1                    6                    1


 2                   6                     0                    3                    01


 3                   3                     1                    1                    101


 4                   1                     1                    0                    1101


 5                   0                     none                 none                 1101

Value displayed at the end: _1101___________________

Table 3. Test Cases for Problem 1 (Part C)

                                                                      Binary From Your        Match?
 Case          Decimal Input           Binary (by hand)
                                                                      Pseudocode              (Y/N)

 1             0                       0                              0                        Y


 2             5                       101                            101                      Y


 3             13                      1101                           1101                     Y


 4             25                      11001                          11001                    Y


 5             255                     11111111                       11111111                 Y



Box 2. Pseudocode for Problem 2 (Part D)

  START
   DISPLAY "Enter a binary number: "
   INPUT binary
   SET decimal = 0
   SET place = 1
   WHILE binary > 0 DO
    SET digit = binary MOD 10
    SET decimal = decimal + (digit * place)
    SET binary = binary DIV 10
    SET place = place * 2
   ENDWHILE
   DISPLAY decimal
 END
                                        Republic of the Philippines
                                       Sorsogon State University
                                  COLLEGE OF INFORMATION
                              AND COMMUNICATIONS TECHNOLOGY
                                             Bulan Campus
                                           Zone 8, Bulan, Sorsogon
                          Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


Figure 2. Flowchart for Problem 2 (Part D)




Table 4. Test Cases for Problem 2 (Part D)

                                                                      Decimal From Your   Match?
 Case          Binary Input            Decimal (by hand)
                                                                      Pseudocode          (Y/N)

 1             1101                    13                             13                  Y


 2             101010                  42                             42                  Y


 3             11111111                255                            255                 Y


 4             10000000                128                            128                 Y
                                         Republic of the Philippines
                                        Sorsogon State University
                                COLLEGE OF INFORMATION
                            AND COMMUNICATIONS TECHNOLOGY
                                               Bulan Campus
                                          Zone 8, Bulan, Sorsogon
                         Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


Bonus Box. Extended Pseudocode: Decimal to Base 2, 8, or 16 (Optional)

 START
  DISPLAY "Enter a whole number (0 or greater): "
  INPUT n
  DISPLAY "Enter the base (2, 8, or 16): "
  INPUT base
  IF n = 0 THEN
    SET result = "0"
  ELSE
    SET result = ""
    WHILE n > 0 DO
     SET remainder = n MOD base
     IF remainder < 10 THEN
       SET digit = remainder
     ELSE
       SET digit = letter for remainder (10=A, 11=B, 12=C, 13=D, 14=E, 15=F)
     ENDIF
     SET result = digit + result
     SET n = n DIV base
    ENDWHILE
  ENDIF
  DISPLAY result
 END

Table 5. README.md File Check (Part E)

 Item                                      Your Findings

 Full folder path of cc101-portfolio       "C:\Users\lenovo\Documents\cc101-portfolio”


 File name shown in File Explorer          README.md

 Type shown in File Explorer (Details
                                           Markdown File
 view)

 Size of README.md shown by dir
                                           12,905
 (bytes)

 Does type README.md show your
                                           Y
 Markdown text? (Y/N)

 Notepad formatted view
                                           Y
 available? (Y/N)

                                            Headings in bold/darker text; bold and italic text styled;
 Elements that appeared
                                           lists indented; code blocks with distinct background.
 formatted in Notepad (if
                                           Tables, links, and images still appear as plain symbols —
 available)
                                           full formatting appears on GitHub.



Table 6. Peer Review Checklist (Part F)
Reviewer's name: Dane Josephine L. Fernandez Owner of the README: Francine L.
                                        Republic of the Philippines
                                       Sorsogon State University
                               COLLEGE OF INFORMATION
                           AND COMMUNICATIONS TECHNOLOGY
                                                Bulan Campus
                                          Zone 8, Bulan, Sorsogon
                         Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


Carilla______________________________

                                                                              Present and Correct?
 Element                      Markdown Used
                                                                              (Y/N)

 Level-1 heading              #                                               Y


 Level-2 headings             ##                                              Y


 Paragraph                    Text with a blank line before and after         Y


 Bold and italic text         **bold** *italic*                               Y


 Bulleted list                - item                                          Y


 Numbered list                1. item                                         Y


 Table                        | --- | header separator                        Y


 Link                         [text](url)                                     Y


 Image                        ![alt](path)                                    Y

                              Lines between two lines of three
 Code block                                                                   Y
                              backticks

 Horizontal rule              ---                                             Y

 File saved as
                              —                                               Y
 README.md (not .txt)



Table 7. GitHub Submission (Part G, Take-Home)

 Item                                       Your Answer

 GitHub username                            carilla26117604


 Repository URL                             httpls://github.com/26117604/cc101-portfolio


 Date uploaded (YYYY-MM-DD)                 2008-10-20

 Does the README display
                                            Y
 formatted on GitHub? (Y/N)

                                             The image and week07-algorithms link are not active —
 Elements that did not display as
                                            the folder is empty and the photo hasn't been
 expected, and why
                                            uploaded. All other elements appear correctly.
                                      Republic of the Philippines
                                     Sorsogon State University
                              COLLEGE OF INFORMATION
                          AND COMMUNICATIONS TECHNOLOGY
                                           Bulan Campus
                                         Zone 8, Bulan, Sorsogon
                        Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


    VI. Realization (Reflection)

In two to four sentences each, answer the following in your own words.

1. Which was easier for you to create, the pseudocode or the flowchart? Why?

  Pseudocode was easier for me to create because it uses simple English like words
 and familiar keywords that I can write step by step without worrying about drawing
 shapes or arranging arrows. I could focus on the logic first and adjust the sequence
 easily, whereas the flowchart required careful planning to place symbols neatly and
 make sure all the arrows connected correctly without crossing.

2. Did tracing and testing reveal any errors in your pseudocode or flowcharts? Describe what
you found and how you corrected it.

  Yes, testing revealed that my first version did not handle the number 0 correctly, it
 would show nothing instead of displaying 0. I also noticed that remainders were
 being added to the right instead of the left, which reversed the binary result. I fixed
 these by adding a separate condition that checks if the input equals 0 and
 immediately displays "0", and I changed how I stored remainders so each new one
 goes to the front of the binary string instead of the end.

3. How is writing a README in Markdown different from typing a document in Microsoft Word?

  Writing in Markdown is different because I cannot see the formatting right away. I
 type special symbols like # and * to style text, and it only looks formatted when
 viewed on GitHub. In Word, I use buttons and menus to make text bold or create
 tables, and I see the result instantly. Also, Markdown creates a plain text file with no
 hidden codes, while Word saves extra formatting information that makes the file
 larger and not readable by GitHub.

4. How can a GitHub portfolio help you as a future computing professional?

 A GitHub portfolio acts as a public, permanent collection of my actual work that
 anyone can view to see my skills and progress. Employers often check GitHub to
 understand how I think, write code, and document projects. It also helps me track my
 own learning over time, practice writing clear documentation, and share my projects
 easily with classmates, instructors, or future teams.
                                      Republic of the Philippines
                                     Sorsogon State University
                               COLLEGE OF INFORMATION
                           AND COMMUNICATIONS TECHNOLOGY
                                           Bulan Campus
                                         Zone 8, Bulan, Sorsogon
                        Tel. No.; 056 311-0103; Email Address: cict@sorsu.edu.ph


   VII. Scoring Guide

Criteria                    Description                                            Points

                            Table 1 is complete; the pseudocode for both
Problem Analysis &          conversions is correct (correct use of MOD, DIV,
                                                                                   25
Pseudocode                  and the loop), uses proper keywords, and is
                            indented.

                            Both flowcharts use the correct symbols with
                            labeled decisions and a clear loop; the trace
Flowcharts & Testing                                                               25
                            (Table 2) and test cases (Tables 3 and 4) are
                            correct.

                            The file is saved correctly as README.md, uses
README.md                   all required Markdown elements, and passes             25
                            the peer review in Table 6.

                            The README is uploaded to a public cc101-
GitHub Upload               portfolio repository and the URL is submitted          10
                            (Table 7).

                            Answers are thoughtful, specific to the student's
Realization / Reflection                                                           10
                            own work, and well written.

                            Worksheet is legible/well-formatted and
Neatness & Timeliness                                                              5
                            submitted on time.

Total                                                                              100
```

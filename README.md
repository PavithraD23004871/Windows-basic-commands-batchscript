## Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

## AIM:
To execute Windows basic commands and batch scripting

## DESIGN STEPS:

## Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

## Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
## Step 3:

Execute the necessary commands/batch file for the desired output. 

## WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT

```
mkdir my-folder
```

<img width="1059" height="76" alt="screen1" src="https://github.com/user-attachments/assets/5cf80808-24c1-4dcb-a7fd-4544602cd5dc" />


Remove the directory "my-folder"

## COMMAND AND OUTPUT

```
rmdir my-folder
```

<img width="1147" height="73" alt="screen2" src="https://github.com/user-attachments/assets/fa2126ad-3476-4263-b190-db060211db87" />

Create the file Rose.txt

## COMMAND AND OUTPUT

```

COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
^Z

dir Rose.txt

```

<img width="1260" height="373" alt="screen3" src="https://github.com/user-attachments/assets/33bcbc76-03fd-4716-8788-dcd38f27f3a2" />


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT

```
echo “hello world” > hello.txt
type hello.txt

```

<img width="1695" height="126" alt="screen4" src="https://github.com/user-attachments/assets/efec450b-b4c8-40c7-a205-69d3cb1a4544" />


Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT

```
copy hello.txt hello1.txt

```
<img width="1695" height="126" alt="screen4" src="https://github.com/user-attachments/assets/87fa1dea-db78-4211-9981-815c0f4c57f5" />

Remove the file hello1.txt

## COMMAND AND OUTPUT

```
del hello1.txt
```

<img width="1134" height="70" alt="screen6" src="https://github.com/user-attachments/assets/063f5e7a-b8c7-4539-8d0c-c964f18cf631" />


List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT

```

dir hello1.txt

```
<img width="1429" height="157" alt="screen7" src="https://github.com/user-attachments/assets/7386818f-0e67-47d2-9b38-4741d0305c51" />


List out all the associated file extensions 

## COMMAND AND OUTPUT

```
assoc | more
```
<img width="1520" height="923" alt="screen8" src="https://github.com/user-attachments/assets/0c77a32f-6ccf-4891-9a8d-fc81e542ae4c" />


Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT

```
fc hello.txt Rose.txt

```
<img width="1520" height="923" alt="screen8" src="https://github.com/user-attachments/assets/6be66469-f7b0-47a1-aa05-46f6285853c7" />


## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".

```


@echo off
set name=John
echo Hello, %name%!
pause


```
## OUTPUT

<img width="909" height="179" alt="screen10" src="https://github.com/user-attachments/assets/00b5d026-74bf-4700-bba3-3607cdc68f4a" />


Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.

```


@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause

```

## OUTPUT

<img width="909" height="179" alt="screen10" src="https://github.com/user-attachments/assets/40b63df3-9b9f-460f-b740-35f56e395cec" />


Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.

```

@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause

```



## OUTPUT

<img width="913" height="164" alt="screen12" src="https://github.com/user-attachments/assets/6bf23c61-358e-4188-b4f3-b58b6da1f5e9" />


Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

```
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause

```

## OUTPUT

<img width="1178" height="276" alt="screen13" src="https://github.com/user-attachments/assets/b00b20e0-20f5-4700-b687-844284611296" />

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.

```

@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause

```

## OUTPUT

<img width="1114" height="395" alt="screen14" src="https://github.com/user-attachments/assets/6dba6a01-8e8e-46a4-b1b0-b8bde0da2b3e" />


## RESULT:
The commands/batch files are executed successfully.


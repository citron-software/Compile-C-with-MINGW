# Compile C with MINGW
Hello!
# Step 1: Install MinGW-w64 via MSYS2
The most modern and stable method for installing MinGW on Windows is to use the MSYS2 package manager.
1. Go to the official MSYS2 website and download the installer (.exe file).

<a href="https://github.com/citron-software/Compile-C-with-MINGW/releases/download/MSYS2-1/msys2-x86_64-20260927.exe">
  <kbd>➔ Click here for download x86_64</kbd>
</a>

<a href="https://github.com/citron-software/Compile-C-with-MINGW/releases/download/MSYS2-2/msys2-arm64-20260927.exe">
  <kbd>➔ Click here for download arm64</kbd>
</a>

2. Run the installer and follow the instructions, keeping the default installation folder (C:\msys64).
3. At the end of the installation, check the box to open the MSYS2 UCRT64 terminal (or search for “MSYS2 UCRT64” in your Start menu).
4. In the terminal that opens, type the following command to install the GCC compiler and the essential development tools:

   pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain

5. Press Enter to confirm the default selections, then type Y (Yes) to start the download and installation.
# Step 2: Add MinGW to the environment variables (PATH)
To use the gcc command from any Windows terminal (Command Prompt or PowerShell), you must set the compiler path.
1. In the Windows search bar, type “Environment Variables” and click Edit system environment variables.
2. In the window that opens, click the “Environment Variables...” button in the lower-right corner.
3. In the “System Variables” section (at the bottom), locate the line labeled “Path” and double-click it.
4. Click the “New” button on the right, then paste the exact path to the “bin” folder of the installed compiler. By default with MSYS2, this is:

   C:\msys64\ucrt64\bin

5. Click OK in all open windows to save the changes.
# Step 3: Check the installation
1. Open a new Command Prompt (cmd) or a new PowerShell window (required to load the new PATH).
2. Type the following command:

   gcc --version

3. If everything is correct, the terminal will display the GCC version (e.g., gcc (Rev...) 13.x.x). If you see an error message stating that the command is not recognized, restart your PC.
# Step 4: Write the source code
1. Open a simple text editor (Notepad, Notepad++, or Visual Studio Code).
2. Copy and paste this minimal test code:
----------------------------------------------
#include <stdio.h>

int main() {
    printf("Bravo, MinGW fonctionne parfaitement !\n");
    return 0;
}

----------------------------------------------
3. Save the file as main.c in an easily accessible folder (for example: C:\Projects). Make sure the file is not named main.c.txt.
# Step 5: Compile and run the program
1. Open the Command Prompt (cmd).
2. Navigate to the folder where you saved your main.c file using the cd command:

   cd C:\Projets

4. Compile the file using the following command:

   gcc main.c -o mon_programme.exe

• main.c : the name of your code file.
• -o mon_programme.exe : Ask GCC to create an executable file named mon_programme.exe.
 4. Run your compiled program by simply typing its name:

   mon_programme.exe

The message “Great job! MinGW is working perfectly!” will then appear in your console.

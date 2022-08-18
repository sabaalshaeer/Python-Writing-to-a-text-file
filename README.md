# Python-Writing-to-a-text-file
Add code to format the input file name.

Position the insertion point at the end of line 108, and press Enter twice.

Enter the code as shown, including the blank line at the end.

Lines 110 through 113 get the name for the log file.

The file name will be based on the name of the original manuscript file.
Line 111 splits the user's input. When you provide an argument to the split() method, you can tell Python where to start splitting, rather than the default of using spaces. The [-1] tells Python to start at the end of the string, so in this case, Python will split everything before the last forward slash, leaving only the file name and its extension.
Line 112 uses rsplit(), which differs from split() in that it starts splitting to the right. The first argument tells Python to split at periods, and the second argument tells Python how many times to do this split. So, Python will only split the very last period in file_name, removing the file extension.
Line 113 appends "_results.txt" to the base name extracted from the manuscript file. The join method is then called to append the file name to the output folder path. The log file will be saved in the Wordcount Output folder on the desktop.
Lines 115 through 120 actually save the file.

Line 116 opens a file for writing. The first argument in open() is the file name, and the second argument tell how the file will be used ("w" for writing to the file).
Line 117 uses the write_file file object to write the first line of text to the output file. This will act as a header for anyone who needs to read the file.
Line 118 and 119 iterate through each item in the results list, writing it out to the file in its own line.
Line 120 closes the file.
Test the program with a missing output folder.

On the Windows desktop, make sure the Wordcount Output folder doesn't exist.

If the directory does exist, delete it or rename it so you can test what happens if the output folder is missing.

Select the wordcount.py tab, and run wordcount.py.

At the three prompts, enter fakefile, y, and y, as shown.

The program runs and processes the word counts, but it fails when it attempts to save the log file.
File operations are especially prone to runtime errors since the ability to complete an operation is subject to missing directories and files, file permissions, and various other problems, so it is very important to add good error-handling capabilities to routines like this.
For now, you can temporarily work around this flaw by ensuring the output folder exists.
Create a new folder on the Windows desktop, and name it Wordcount Output.

Note: To avoid errors, make sure the folder is named exactly as shown.

Test the program.

In PyCharm, select the wordcount.py tab, and run wordcount.py.

At the three prompts, enter fakefile, y, and y, as shown.

This time, the program saves the log file successfully, and finishes with an exit code of 0.
Note: You still have a TO-DO placeholder for "Save the results to a log file and copy to an archive file." The code you have added here partially completes this task. It saves a log file, but it does not yet copy the log file to a dated archive file. You won't delete this placeholder until you complete the entire task.

Confirm that the output log has been written.

On the Windows desktop, open the Wordcount Output folder, and examine the log file.

The output file has been saved.
The file name is based on the name of the manuscript file you passed into the input prompt.
Double-click fakefile_results.txt to open it in your text editor.

The results have been written to the file.

Exit the text editor.

In File Explorer, delete the fakefile_results.txt file. Leave the Wordcount Output folder in place, though.

Close the File Explorer window and return to PyCharm.

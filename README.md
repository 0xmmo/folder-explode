# Folder Explode

A simple Windows utility that adds a context menu option to explode folders. (that is copy folder's contents into parent and delete folder itself)

Works on Windows XP, 7, 8+.
Tested on Windows 8.1 only.

### How to install
Run install.bat  

### How it works
When you run the install.bat file, a registry key is created under 
> HKEY\_CLASSES\_ROOT/Folder/shell/Explode/command

with a default value of the command
> ``` cmd.exe /s /k xcopy /w /e /h /-y "%V" "%W" &  rmdir /s /q "%V" & exit ```

which is invoked when the context menu option is clicked.

+ **cmd.exe** Opens the command shell  
	- **/s /k** Carries on the commands following  
+ **xcopy** Copies files and directories, including subdirectories  
	- **/w** Pauses for confirmation  
	- **/e** Copies empty subdirectories  
	- **/h** Copies files with hidden and system file attributes  
	- **/-y** Asks before overwriting files in destination  
	- **"%V"** Source directory, %V is the variable for the directory passed to the   command shell	  
	- **"%W"** Destination directory, %W is the variable for the current working directory in the command shell  
+ **rmdir** Removes/deletes a directory  
	- **/s** Removes the specified directory and all subdirectories including any files  
	- **/q** Runs rmdir in quiet mode  
	- **"%V"** 	Location of directory to be deleted

### Why?
Because no one else did.

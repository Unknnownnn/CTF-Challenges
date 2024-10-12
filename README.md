
# <p align="center"> ZypherQuest </p>


### $${\color{red}Overview:}$$
We are given a file named “ZypherQuest”. The file extension is not visible and no specific details are provided. We need to decipher this file and get the answer in zyp{XXXX} form.

### $${\color{red}Theory:}$$
To traverse directories, cd command is used. To copy a file, cp command is used like cp <filename> <new file location>. To rename a file, mv command is used like mv <oldname> <newname>. This can also be used to add an extension to a file without on for example a file named ‘picture’ can rename to ‘picture.png’ and be opened.

File command followed by file name, for example: file picture, returns the type of file it is. In the given example the command will tell us it is a png file and we may use this information as we prefer.

Tar is archiving utility which groups together multiple files in a .tar format. Tar can also be used with a compressing utility such as bzip2 or gzip. 

Chmod (change file mode bits) is used to change the permission of a given file for different users such as reading, writing and executing a file.




### $${\color{red}Solution:}$$
Firstly, since we don’t know what kind of file ZypherQuest is, we check its type using
file ZypherQuest

We see it is a zip file. Now use Unzip ZypherQuest to unzip the file. Now we check the extracted files using ls.
 
We can see the extracted file is a gzip file which is archived using tar. Extracting the file, we see 3 new files have been extracted 2 of which are directories. Using tree command, we see these directories hold 2 text files.
 
 
(Here tar -xzf uncompresses a gzip archived file directly. The “z” in “-xzf” is used for gzip.)

You may want to read the following files but skipping that, we check the file type for Seal.
 
The given file is a bzip2 compressed data. To unzip the file, we can firstly rename the file to add .bz2 extension and proceed to unzip it using bzip2. This gives us a tar file which can be further extracted using tar.
mv Seal Seal.bz2
bzip2 -d Seal.bz2
tar -xvf Seal
Instead of these 3 steps we can directly uncompressed the given data “Seal” using tar -xjf command.
 
(Here tar -xjf uncompresses a bzip2 archived file directly. The “j” in “-xjf” is used for bzip2.)

We can see new files have been uncompressed. We also see a file named Start.sh which is a script file. We can try running this using ./Start.sh. Running it essentially does nothing but delete old files cluttering the screen if they weren’t already deleted. We can try and read some files to try and get some clues. Here the file Admin looks interesting. Checking its file type, we see it is another tar file.
 
 

Extracting it gives us a file name Z0d1aCisWatching. We again check the file type and try decompressing it.
 
 

Further checking the decompressed file (data in this case) We see a tar file again. Decompressing it gives an interesting file.
 
Checking its file type shows there are no permissions assigned to the given file. So, we used chmod 444 or chmod +r to make the file readable.
 
Now we can read the contents of the file and get the answer to this level.

## $${\color{red}Answer: }$$
## $${\color{lightgreen}zyp(L0S7)}$$ 

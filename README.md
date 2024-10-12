
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
```file ZypherQuest```

![image](https://github.com/user-attachments/assets/76665b5f-8acf-45d4-adcd-618dede6f607)

We see it is a zip file. Now use Unzip ZypherQuest to unzip the file. Now we check the extracted files using ls.


![image](https://github.com/user-attachments/assets/b5d8b6ec-0756-4c4a-84e1-0e6d0332e164)
 
We can see the extracted file is a gzip file which is archived using tar. Extracting the file, we see 3 new files have been extracted 2 of which are directories. Using tree command, we see these directories hold 2 text files.

  

![image](https://github.com/user-attachments/assets/0642919b-87d1-4b08-9b9c-1aeb9bba6b8f)
![image](https://github.com/user-attachments/assets/a71e47a7-a156-47c5-926a-7ade55a4cf9c)
 
(Here tar -xzf uncompresses a gzip archived file directly. The “z” in “-xzf” is used for gzip.)

You may want to read the following files but skipping that, we check the file type for Seal.

![image](https://github.com/user-attachments/assets/52c28e43-80f1-4dd6-ad76-3375e05e0621)
 
The given file is a bzip2 compressed data. To unzip the file, we can firstly rename the file to add .bz2 extension and proceed to unzip it using bzip2. This gives us a tar file which can be further extracted using tar.
```
mv Seal Seal.bz2
bzip2 -d Seal.bz2
tar -xvf Seal
```
Instead of these 3 steps we can directly uncompressed the given data “Seal” using tar -xjf command.


![image](https://github.com/user-attachments/assets/5ad85f0d-c004-414a-ba9e-f24d543a0cc5)
 
(Here tar -xjf uncompresses a bzip2 archived file directly. The “j” in “-xjf” is used for bzip2.)


We can see new files have been uncompressed. We also see a file named Start.sh which is a script file. We can try running this using ./Start.sh. Running it essentially does nothing but delete old files cluttering the screen if they weren’t already deleted. We can try and read some files to try and get some clues. Here the file Admin looks interesting. Checking its file type, we see it is another tar file.
 

![image](https://github.com/user-attachments/assets/5b9361d8-11fc-4bef-8ae4-e54effee3c70)
![image](https://github.com/user-attachments/assets/00d215ed-1c3e-4c9f-a75c-cc90d4562ad7)

Extracting it gives us a file name Z0d1aCisWatching. We again check the file type and try decompressing it.

![image](https://github.com/user-attachments/assets/e0b630ee-6819-4770-b5cb-9872a5b22a73)
![image](https://github.com/user-attachments/assets/7f70d368-f9cd-4c61-8450-a146d79dae6b)
 
 

Further checking the decompressed file (data in this case) We see a tar file again. Decompressing it gives an interesting file.

![image](https://github.com/user-attachments/assets/686c59f8-e0e3-47af-9f30-6ab5063af8aa)
 
Checking its file type shows there are no permissions assigned to the given file. So, we used chmod 444 or chmod +r to make the file readable.

![image](https://github.com/user-attachments/assets/31f58bcf-4e6d-4826-a994-d6ccd637d34f)
 
Now we can read the contents of the file and get the answer to this level.

![image](https://github.com/user-attachments/assets/d4d1be82-7dfa-4bf1-b5d1-64a05584619d)

## $${\color{red}Answer: }$$
## $${\color{lightgreen}zyp(L0S7)}$$ 

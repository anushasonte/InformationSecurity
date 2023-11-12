Task 1: Generating Two Different Files with the Same MD5 Hash
In this task, we will generate two different files with the same MD5 hash values. The beginning parts of these
two files need to be the same, i.e., they share the same prefix. We can achieve this using the md5collgen
program, which allows us to provide a prefix file with any arbitrary content. The way how the program
works is illustrated in Figure 1.
The following command generates two output files, out1.bin and out2.bin , for a given a prefix file
prefix.txt :
$ md5collgen -p prefix.txt -o out1.bin out2.bin
Figure 1: MD5 collision generation from a prefix
We can check whether the output files are distinct or not using the diff command. We can also use the
md5sum command to check the MD5 hash of each output file. See the following commands.
$ diff out1.bin out2.bin
$ md5sum out1.bin
$ md5sum out2.bin
Since out1.bin and out2.bin are binary, we cannot view them using a text-viewer program, such as cat
or more ; we need to use a binary editor to view (and edit) them. We have already installed a hex editor
software called bless in our VM. Please use such an editor to view these two output files, and describe
your observations. In addition, you should answer the following questions:
• Question 1. If the length of your prefix file is not multiple of 64 , what is going to happen?
• Question 2. Create a prefix file with exactly 64 bytes, and run the collision tool again, and see what
happens.
• Question 3. Are the data ( 128 bytes) generated by md5collgen completely different for the two
output files? Please identify all the bytes that are different.
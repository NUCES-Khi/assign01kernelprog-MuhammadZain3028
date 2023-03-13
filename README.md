<h1>Assignment No.1 K21-4729</h1>
<h2>Preparation</h2>
OS used : Ubuntu 16.04
<ul>
  <li>sudo apt-get install gcc</li>
  <li>sudo apt-get install libncurses5-dev</li>
  <li>sudo apt-get install bison</li>
  <li>sudo apt-get install flex</li>
  <li>sudo apt install make</li>
  <li>sudo apt-get install libssl-dev</li>
  <li>sudo apt-get install libelf-dev</li>
  <li>sudo add-apt-repository "deb http://archive.ubuntu.com/ubuntu $(lsb_release -sc) main
universe"</li>
  <li>sudo apt-get update</li>
  <li>sudo apt-get update</li>
</ul>
<h2>Step 1: Downloading Kernel</h2>

![image](https://user-images.githubusercontent.com/126277547/224710415-8351f68b-3764-42bd-b2c3-b417cc2b7641.png)

<h2>Step 2:</h2>
Extract the kernel and make a folder named "hello" and make two files inside that folder makefile, and hello.c

![hello folder](https://user-images.githubusercontent.com/126277547/224712827-b71f27d4-6b54-4b2f-bedd-95b7085fac1f.PNG)

![insindehellofolder](https://user-images.githubusercontent.com/126277547/224712860-a87c87fe-2cd7-4524-aec9-20eea0fed380.PNG)

![hellocode](https://user-images.githubusercontent.com/126277547/224712874-5768bd07-1896-43fa-902c-e11b322fd7cb.PNG)

![makefilecode](https://user-images.githubusercontent.com/126277547/224712881-35b99eec-d1d2-418d-8e81-e6c7bb01eaca.PNG)

<h2>Step 3:</h2>
Next we add new code in the system table file, and add a prototype of the hello system call, to system calls header file and change the version and add hello folder in makefile 

![makefilerollno](https://user-images.githubusercontent.com/126277547/224713963-bfaa9f15-6c8a-4f34-ba99-67ee905075c0.PNG)

![makefilehello](https://user-images.githubusercontent.com/126277547/224713985-849d83cd-6f2d-4b30-994e-8dac5189fb81.PNG)

<h2>Step 4:</h2>
Create an old config by using "yes"" | make oldconfig -j"n" ", replace "n" with the amount of cores you have
then we clean the old files using "make clean -j"n" " then use "make -j"n" " to build the kernel and then install modules using "make modules_install install" once it says done restart the pc and select the new kernel

![image](https://user-images.githubusercontent.com/126277547/224715087-b546982c-17ed-4ebc-b525-867d9bc22dab.png)

![image (1)](https://user-images.githubusercontent.com/126277547/224715119-42b0d328-a4c0-4423-9e5e-32858a3f117b.png)

![image (2)](https://user-images.githubusercontent.com/126277547/224715184-cf1155ad-5458-4038-a2c3-4655a3b88ca9.png)

![unnamed](https://user-images.githubusercontent.com/126277547/224715580-817686c0-919c-4878-8721-d494505fe0a2.png)

<h2>Step 5:</h2>

Create a new c file with the code : 

#include <stdio.h>
#include <linux/kernel.h>
#include <sys/syscall.h>
#include <unistd.h>
int main()
{
long int i = syscall(335);
printf("System call sys_hello returned %ld\n", i);
return 0;
}

We will compile the file ussing gcc "namehere".c and execute it using ./a.out if it returns 0 then the code has compiled succesfully then we run dmesg to see the Hello World at the end of the kernel messages
and uname -r  to see the version number we added

![image (3)](https://user-images.githubusercontent.com/126277547/224716286-dce00cbc-fb72-435c-a2d5-a4af54504262.png)

![image (4)](https://user-images.githubusercontent.com/126277547/224716336-befcbded-0ab5-48f0-872f-4f01b930e31f.png)

![f7f29d6e-7095-4171-8fb4-540bad67cfae](https://user-images.githubusercontent.com/126277547/224716403-cd046b04-8561-456e-8a51-358bc8a21c34.png)








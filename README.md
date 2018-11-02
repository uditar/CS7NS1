# CS7NS1
Scalable Computing
Practical Assignments
1. Assignment 1 : Register with RosettaHub, set up AWS, install linux and compile John the Ripper. Running a benchmarking script.
Steps for setting up AWS and running benchmarking scripts
a. Creating an instance
1.	Open RH and create a linux instance -> in this case search for Ubuntu 18.04 image from images and click on launch
2.	It will prompt you to select spot instance type and other settings, leave them as is
3.	Once created the image appears in the top under “Sessions”
4.	Right click on the image and click check connectivity info
5.	Download the private keys .pem and .ppk and rename them to something memorable and easier
6.	Download WinSCP and putty (for windows os)
b. Setting up WinSCP and putty
1.	Open WinSCP and log in by entering the host name, port number and ppk downloaded from step 5 above.
 
![Screenshot](tempsnip.png)
 

2.	Once this is done clone the John the Ripper git repo into the home directory i.e. ubuntu/home/code/JohnTheRipper
3.	Open Putty.exe (in my case I could not open it directly from my WinSCP for some reason). Connect to putty by entering the port number, name and keys as follows 
 

4.	Open putty and login as : ubuntu
c. Installing JohnTheRipper and running the benchmarking script
1.	Copy the benchmarking scripts to the run folder
2.	cd into the src folder (ex. ubuntu@ip-172-30-2-21:~/code/JohnTheRipper/run$ cd /home/ubuntu/code/JohnTheRipper  path of benchmark script)
3.	Run the following scripts in order
i.	mkdir -p ~/src
ii.	sudo apt-get install build-essential libssl-dev git
iii.	cd ~/src/john/src
iv.	sudo chmod +x ./configure  had to set permissions for configure command
v.	./configure && make -s clean && make -sj4
vi.	$ ../run/john --test=0  test the build and run step vii if successful
vii.	$ ../run/john –test  runs the benchmarking script

Ex.
ubuntu@ip-172-30-2-21:~/code/JohnTheRipper$ ./as2-bench.sh 
Will run 2 OpenMP threads
./as2-bench.sh: line 121: ./as2-validator.sh
Your output is in as2-output.bench
viii.	Uploaded the .bench file successfully to submitty
ix.	Create an image of the machine and stop the instance

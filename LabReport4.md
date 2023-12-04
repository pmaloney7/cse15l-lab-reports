# Lab Report 4

## Step 4
To log into ieng6 I opened the terminal on visual studio code and typed ssh cs15lfa23lx@ieng6.ucsd.edu<enter>. It logged me in without a password because I set up the public and private keys from a previous lab.
![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/2b09ab11-4326-4250-bffd-d83a852c7fed)

## Step 5
When first doing this lab on the CSE computers, I typed git clone https://github.com/ucsd-cse15l-s23/lab7 like it says at the beginning of the lab report in order to clone the repository. It already exists, but in this screenshot I am showing how I would've cloned lab7 using the ssh method that the lab later talks about.
![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/12988074-c754-4feb-bece-d7ecfe2caa0f)
![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/4503d4bd-6e2c-4617-aaec-4140d7ecf72c)

## Step 6
I typed bash test.sh in order to run the unit tests, and they fail because there is a bug.
![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/fd1cb128-e511-487d-bd75-57dea6902f94)

## Step 7
a. type vim ListExamples.java to open the file

b. press j 43 times to get to line 44

c. press l 11 times to get to what we need to delete

d. press x or del key to delete '1'

e. press i to insert a new character

f. press 2 to insert 2 at that spot

g. press escape key to exit the insert mode

h. type :wq to save and exit the file

Here's the finished result
![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/7432b942-d506-4ae3-ac33-d951188b2104)

## Step 8
I used the up arrow key to bring back bash test.sh which I typed before, and ran it again. Now I get a different result because the file has been updated.

![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/fa1d4d73-5249-4415-9f1d-cbbf6c5382a2)


## Step 9 
I used git add, git commit, and git push to complete this step. git add ListExamples.java stages the file for changes. git commit -m "bug fixes" saves the file changes locally under with the note "bug fixed". Lastly, git push origin main uploads the committed changes to the original repository in the main branch. This all happens remotely.

![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/f3dd956e-a17a-42b4-8b8e-2eec388ae9a2)

![image](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/c28a3c50-e257-49b1-a67b-34623a021d06)

# Lab Report 1
## The cd command: 
1. input: `[user@sahara ~]$ cd`
  
   output: `[user@sahara ~]$`

   pwd was /home. Nothing happened because no argument was provided, so it just defaults to the same directory. No error here.
   
2. input: `[user@sahara ~]$ cd lecture1`

   output: `[user@sahara ~/lecture1]$`

   pwd was also /home. It changed the directory now to lecture1 because that's what was asked of it. No error here.

3. input: `[user@sahara ~/lecture1]$ cd Hello.java` 

   output: `bash: cd: Hello.java: Not a directory` 

   pwd was /home/lecture1. It tried changing the directory to Hello.java but realized that is not a directory to go to, but rather a file. It errored because Hello.java is a file and the cd commmand does not open files. 

## The ls command: 
4. input: `[user@sahara ~]$ ls` 
   output: `lecture1` </br>
   pwd was /home. Returned lecture1 because that is the only file at the home level in my workspace. No error here. 
   </br>
5. input: `[user@sahara ~]$ ls lecture1` 

   output: `Hello.class  Hello.java  messages  README  temp.md` 
   
   pwd was also /home. These were all of the files/folders in the lecture1 folder. No error. 
   

6. input: `[user@sahara ~/lecture1]$ ls Hello.java` 

   output: `Hello.java` 
   
   pwd was /home/lecture1. Returned Hello.java because that's the only file in Hello.java (I actually didn't think this would happen). No errors. 
   
## The cat command:
7. input: `[user@sahara ~]$ cat` 

   output: > 
   
   pwd was /home. After pressing enter, the command does not return anything but it opens a new line and repeats anything entered from that point on. Although this isn't an error, I wasn't expecting this to happen and had to google how to exit this mode (ctrl D). 
   
8. input: `[user@sahara ~]$ cat lecture1` 

   output: `cat: lecture1: Is a directory` 
   
   pwd was /home. Cat takes files as arguments and it realized that lecture1 is a directory and not a file, so it returned an error message instead. 
  
9. input: `[user@sahara ~/lecture1]$ cat Hello.java` 

   output: `import java.io.IOException;`
   `import java.nio.charset.StandardCharsets;`
   `import java.nio.file.Files;`
   `import java.nio.file.Path;`
   `public class Hello {`
   `public static void main(String[] args) throws IOException {`
    `String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);`    
    `System.out.println(content);
  `}` 

   pwd was /home/lecture1. Returned the contents of Hello.java because that is what was asked. No error.

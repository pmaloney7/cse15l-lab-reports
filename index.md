#The cd command: 
[user@sahara ~]$ cd 
pwd was /home. Nothing happened because no argument was provided, so it just defaults to the same directory. No error here.

[user@sahara ~]$ cd lecture1 
[user@sahara ~/lecture1]$ 
pwd was also /home. It changed the directory now to lecture1 because that's what was asked of it. No error here.

[user@sahara ~/lecture1]$ cd Hello.java 
bash: cd: Hello.java: Not a directory 
pwd was /home/lecture1. It tried changing the directory to Hello.java but realized that is not a directory to go to, but rather a file. It errored because Hello.java is a file and the cd command does not open files.

#The ls command: 
[user@sahara ~]$ ls 
lecture1 
pwd was /home. Returned lecture1 because that is the only file at the home level in my workspace. No error here.

[user@sahara ~]$ ls lecture1 
Hello.class Hello.java messages README temp.md 
pwd was also /home. These were all of the files/folders in the lecture1 folder. No error.

[user@sahara ~/lecture1]$ ls Hello.java 
Hello.java 
pwd was /home/lecture1. Returned Hello.java because that's the only file in Hello.java (I actually didn't think this would happen). No errors.

#The cat command: 
[user@sahara ~]$ cat
pwd was /home. After pressing enter, the command does not return anything but it opens a new line and repeats anything entered from that point on. Although this isn't an error, I wasn't expecting this to happen and had to google how to exit this mode (ctrl D).

[user@sahara ~]$ cat lecture1 
cat: lecture1: Is a directory 
pwd was /home. Cat takes files as arguments and it realized that lecture1 is a directory and not a file, so it returned an error message instead.

[user@sahara ~/lecture1]$ cat Hello.java 
import java.io.IOException; 
import java.nio.charset.StandardCharsets; 
import java.nio.file.Files; 
import java.nio.file.Path;

public class Hello { 
  public static void main(String[] args) throws IOException { 
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);
    System.out.println(content); 
  }
}
pwd was /home/lecture1. Returned the contents of Hello.java because that is what was asked. No error.

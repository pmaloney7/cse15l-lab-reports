#The cd command: \n
[user@sahara ~]$ cd \n
pwd was /home. Nothing happened because no argument was provided, so it just defaults to the same directory. No error here. \n
\n
[user@sahara ~]$ cd lecture1 \n
[user@sahara ~/lecture1]$ \n
pwd was also /home. It changed the directory now to lecture1 because that's what was asked of it. No error here. \n
\n
[user@sahara ~/lecture1]$ cd Hello.java \n
bash: cd: Hello.java: Not a directory \n
pwd was /home/lecture1. It tried changing the directory to Hello.java but realized that is not a directory to go to, but rather a file. It errored because Hello.java is a file and the cd command does not open files. \n
\n
#The ls command: \n
[user@sahara ~]$ ls \n
lecture1 \n
pwd was /home. Returned lecture1 because that is the only file at the home level in my workspace. No error here. \n
\n
[user@sahara ~]$ ls lecture1 \n
Hello.class Hello.java messages README temp.md \n
pwd was also /home. These were all of the files/folders in the lecture1 folder. No error. \n
\n
[user@sahara ~/lecture1]$ ls Hello.java \n
Hello.java \n
pwd was /home/lecture1. Returned Hello.java because that's the only file in Hello.java (I actually didn't think this would happen). No errors. \n
\n
#The cat command: \n
[user@sahara ~]$ cat \n
pwd was /home. After pressing enter, the command does not return anything but it opens a new line and repeats anything entered from that point on. Although this isn't an error, I wasn't expecting this to happen and had to google how to exit this mode (ctrl D). \n
\n
[user@sahara ~]$ cat lecture1 \n
cat: lecture1: Is a directory \n
pwd was /home. Cat takes files as arguments and it realized that lecture1 is a directory and not a file, so it returned an error message instead. \n
\n
[user@sahara ~/lecture1]$ cat Hello.java \n
import java.io.IOException; \n
import java.nio.charset.StandardCharsets; \n
import java.nio.file.Files; \n
import java.nio.file.Path; \n
\n
public class Hello { \n
  public static void main(String[] args) throws IOException { \n
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8); \n
    System.out.println(content); \n
  } \n
} \n
pwd was /home/lecture1. Returned the contents of Hello.java because that is what was asked. No error. \n

# Lab Report 2
```
import java.io.IOException;
import java.net.URI;
import java.util.Scanner;
class Handler implements URLHandler {
    String str = "";
    int num = 0;
    public String handleRequest(URI url) {
        if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                num += 1;
                String num1 = Integer.toString(num);
                str += num1 + ". " + parameters[1] + "\n";
                return str;
            }
        }
        return "404 Not Found!";
    }
}
class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number!");
            return;
        }
        int port = Integer.parseInt(args[0]);
        Server.start(port, new Handler());
    }
}
```

![a](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/80dcca3b-5466-43ce-a842-b27e62d7427d)
handleRequest is called on the URL. The url argument is the URI object that contains the path /add-message and the query string s=Hello. The parameters are "s" and "Hello." The str field is initally an empty string, and once the method is called, it becomes "1. Hello\n". The num field is initally 0 and increments by 1 once the method is called.

![b](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/27d27212-3f6d-4a71-b85b-39f806871164)
handleRequest is called on the URL. The url agument is the URI object that contains the path /add-message and the query string s=How%20are%20you. The parameters are "s" and "How%20are%20you". Previously, num was 1 and str was "1. Hello\n", but now, num increments to 2 and str becomes "1. Hello\n2. How are you"

To summarize, each request to /add-message with a query parameter s increments the num field and appends a new line with the current num and the provided message to the str field. The handleRequest method checks the path and the query parameters, performs the needed operations, and alters the str and num fields accordingly. The Server.start method would have been called before any of these requests to initialize the server with the given port, but this is not part of the screenshots provided.

![c](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/cdc86de8-e33a-49cd-9867-5a7cebf373fc)

![d](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/58a77a50-914c-421c-95b4-63b0f8e85fe3)

![e](https://github.com/pmaloney7/cse15l-lab-reports/assets/146884245/aee3bb7a-a647-45e7-b460-501e848bdbdf)


I learned how to better log into remote computers from my own desktop. I also learned that because my computer user name has a space inbetween my first and last name, that causes a lot of problems when running commands because the terminal thinks I am separating arguments with that space. Overall, the ssh makes your life easier since you don't have to type the password every time.

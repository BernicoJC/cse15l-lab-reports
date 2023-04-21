# CSE 15L Lab Report 2

Hi, my name's Bernico and today I will continue showing my progress in this class. Particularly, I will be showing what I've learned about setting up my own simple server and debugging. I will also be reflecting on what I've learned so far in these past two weeks.

## Part 1: Setting up My Own Server

On Lab 2, I learned about setting up my own local / remote server through the course's ssh. I will be showing the server I created that would display the strings the server stores after inputting said strings through the query of the server link. Basically, it's a server that's storing data of strings. The code that I wrote uses the Server.java file that the professor gave. This file handles the server starting and the handling of the backend program behind my server. I use it in the form of Server class's static method of `.start(int port, URLHandler handler)` that I use in my main method. The code that I wrote are displayed below.

  ![Image](Images/StringServerCode1.png)

  ![Image](Images/StringServerCode2.png)
  
To briefly explain this code, it contains my implementation of the `URLHandler` interface's method `handleRequest(URI url)`. It detects the `url` parameter's path content using `.getPath()`. If this is just `"/"`, then the server should show the default home page. If it's anything else, then it gets to the `else` statement, which is only there to detect for the path `"add-message"`. If after that, the URL contains `s` as its query, then the string after it will be appended to the `ArrayList dataList`. If none of this activated, it will throw the "Page not found" error page. Meanwhile, the second screenshot just starts the server with the port that's asked in the main's argument.
  
Meanwhile, the working implementation of this code are shown below.

  ![Image](Images/StringServerRunning0.png)
  ![Image](Images/StringServerRunning0.5.png)
  
  ***
  
  ![Image](Images/StringServerRunning1.png)
  
When the `java StringServer.java` is run, the `main` method is run, then `println()` method for the missing port in `args` message if nothing is in args, or `parseInt()` and `.start` method when there is an existing `args`. The `.start()` method also runs a lot of other methods that I won't be explaining.

When the URL is entered like in the screenshot, the methods that will run from my code are the several `url.getPath()` that read the URL's path, `.contains()` and `.equals()` that compare the URL's path to the intended value like `/add-message` and `s`, `.getQuery()` that gets the query from the URL's path, the `.split()` method that's splitting the query path (to get the string before and after the `=`). And, last but not least, it's also using the method `.add()` to add the string from the URL to the ArrayList.

The relevant arguments and fields' values during that whole methods activation are:
1. `ArrayList<String> dataList= new ArrayList<>();` that initiates the array list to store the strings
2. The `url` parameter for `handleRequest()`
3. `"/"` for `.equals()` to detect the home page
4. `"/add-message"` for `.contains()` to detect path; `"="` and `url.getQuery().split("=");` to split the query; `"s"` to detect the query's keyword
5. `String r = ""`, `r = r + strs + "\n"`, and the for loop's field `String strs: dataList` to iterate through and print 
6. Here are also the relevant values from the main method (for the server starting): `String[] args` the main argument (parameter), `args.length == 0` to test if no port is inputted and `"Missing port number!"` for the message, the field `int port = Integer.parseInt(args[0]);`and the server starter's parameter `port, new Handler()`.

The values that changed after me entering the new URL are:
1. `ArrayList<String> dataList` that got a new value `"Hello World"` in it
2. `String strs: dataList` inside the for loop changed every iteration, with now specifically getting `"Hello World"`
3. `r` got changed every loop iteration, concatenating the `strs` and `\n` to create new line of all of the strings stored for returning what's displayed.
  
  ***
  
  ![Image](Images/StringServerRunning2.png)

When the URL is entered like in the screenshot, the methods that will run from my code are the same as the ones in the first screenshot, that being: `url.getPath()`, `.contains()` and `.equals()`, `.getQuery()`, `.split()`, and `.add()`.

Likewise, the relevant arguments and fields' values during this screenshot's whole methods activation are similar to the previous one with a few no longer relevant, being:
1. The `url` parameter for `handleRequest()`
2. `"/"` for `.equals()` to detect the home page
3. `"/add-message"` for `.contains()` to detect path; `"="` and `url.getQuery().split("=");` to split the query; `"s"` to detect the query's keyword
4. `String r = ""`, `r = r + strs + "\n"`, and the for loop's field `String strs: dataList` to iterate through and print the result

The values that changed after me entering the new URL are:
1. `ArrayList<String> dataList` that got a new value `"My name is Bernico"` in it
2. `String strs: dataList` inside the for loop changed every iteration, with now specifically being `"Hello World"` and `"My name is Bernico'`
3. `r` got changed every loop iteration, concatenating the `strs` and `\n` to create new line of all of the strings stored for returning what's displayed.

## Part 2: Debugging

On this part, I will choose to debug the List Methods part.
1. One failure inducing input to each of the List Methods are:
```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.ArrayList;
import java.util.List;

public class ListTests {
    @Test 
	public void testFilter() {
  
        // StringChecker sc = new ListExamples();
        List<String> input3 = new ArrayList<>();
        input3.add("abcd");
        input3.add("abcdefg");
        input3.add("abcdefgh");

        List<String> test3 = new ArrayList<>();
        test3.add("abcdefg");
        test3.add("abcdefgh");
        
        assertEquals(test3, ListExamples.filter(input3, null)); // replace null with sc after the code is fixed to get accurate result
	}

    @Test 
	public void testMerge() {
        List<String> input1 = new ArrayList<>();
        input1.add("a");
        input1.add("a");
        input1.add("a");

        List<String> input2 = new ArrayList<>();
        input2.add("abcdef");
        input2.add("abc");
        input2.add("a");
  
        assertEquals(new ArrayList<>(), ListExamples.merge(input1, input2));
	}
}
```
Quick note: for the testFilter, it failed because there's simply no StringChecker-implemented-class yet to fill in the `static List<String> filter(List<String> list, StringChecker sc)` `sc` parameter with. However, filling it with null only makes the problem worse as `sc.checkString(s)` is called later. As such, any possible input will be failure-inducing. The comment line ``StringChecker sc = new ListExamples();`` will be used instead and the null will be replaced with `sc`.

2. One input that doesn't cause a failure for each of the List Methods are:
```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.ArrayList;
import java.util.List;

public class ListTests {
    @Test 
	public void testFilter() {
        // NO INPUT FOR THIS METHOD THAT DOESN'T CAUSE A FAILURE WITHOUT ANY MODIFICATION TO THE BUGGED PROGRAM
	}

    @Test 
	public void testMerge() {  
        assertEquals(new ArrayList<>(), ListExamples.merge(new ArrayList<>(), new ArrayList<>()));
	}
}
```
As mentioned before, `testFilter` is just completely impossible to function without at least a modification. As such, if we have modified it a bit just so it can run, but still has bugs, then I might be able to show at least one example of successful input. Since, as mentioned above, there isn't an implementation of `StringChecker` yet, we can make it so that `ListExamples implements StringChecker` and then implement the `checkString` method. Then, `ListExamples.java` will be like below.
```
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples implements StringChecker{

  // implementing checkString
  public boolean checkString(String s) {
      if(s.length() > 5){
        return true;
      }
      return false;
  }

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }
  
  static List<String> merge(List<String> list1, List<String> list2) {
    // merge method, irrelevant for now
  }
}
```

In this, I defined `checkString` as returning true if the parameter's length is strictly above 5, and false otherwise. This way, with something to work with, at least this input will be succesful (however the code from point 1. will still result to failure, even after creating the new StringChecker as commented before).

```
import static org.junit.Assert.*;
import org.junit.*;
import java.util.ArrayList;
import java.util.List;

public class ListTests {
    @Test 
	public void testFilter() {
        StringChecker sc = new ListExamples();
        List<String> input1 = new ArrayList<>();
        input1.add("a");
        input1.add("a");
        input1.add("a");

        List<String> test1 = new ArrayList<>();
        
        assertEquals(test1, ListExamples.filter(input1, sc));
	}
```

3. The symptom of the code are that for `filter`, like mentioned before, `null` can't be used for the `sc` parameter, while no `StringChecker` has been implemented yet; OR, for the extra that has already implemented one, the order of the list will be in reverse (list returned not following the expected). Meanwhile, for `merge`, the terminal will run forever, not allowing any test to result. The output of the JUnit code can be seen below.
  - `filter` failure (because `null`)
  
  - `filter` failure (after the implementation of `StringChecker`)
  - `filter` success (after the implementation of `StringChecker`)
  - `merge` failure
  - `merge` success

4. 

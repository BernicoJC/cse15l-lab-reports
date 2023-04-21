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
  ![Image](Images/StringServerRunning2.png)

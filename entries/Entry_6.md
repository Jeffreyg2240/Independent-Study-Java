### Week 6:
During we 6 our group decided that we needed to take a stand to what game we are making. After 3 days of bickering, we settled in programming a variation of “bomber-man”. We haven’t assigned roles yet, although we really need to since this is already over two-thirds of the way into the 9-week independent study.
<br>
Here are the beginnings of our pseudocode.<br>
<img src = "https://raw.githubusercontent.com/Jeffreyg2240/Independent-Study-Java/master/images/psu1.JPG">
<img src = "https://raw.githubusercontent.com/Jeffreyg2240/Independent-Study-Java/master/images/psu2.JPG">
<br><br>
As we started writing down ideas, we noticed that many of the things that we wrote down would have to come after the MVP, like the items.
<br>
We’re planning to start working on the project next week, with this __week concluding our “Independent Study” and turning it towards “Group Study”__. To prepare for the game, I’ve decided to take a risk - making the game multiplayer. At first, I needed to learn the concepts of a client and server and it’s usability in Java. With this, I came across a few online lessons that taught the basics of “sockets”, which allows multiple connections from clients to one server. After 4 days of testing and learning, I’ve noticed that I’ve barely scratched the surface, I could use the command prompt to get user input and display it to the other client applications. Since then(Friday), I’ve also added a way for the user to add their own user name in the beginning and also text and to limit the number of users who can connect to 4.



##### Sidenote:
If you are running your server locally, you can get use __"localhost"__ or use the __IP of your personal computer_. **Look at the screenshot if you are using windows**<br>
If you are on a windows device and you want to find your local IP, not host IP, then type __“ipconfig/all”__ in the command prompt.<br>
Here is what I got up to so far this week, I can enable 4 people to connect to a chat client with the prompt.
<img src = "https://raw.githubusercontent.com/Jeffreyg2240/Independent-Study-Java/master/images/ipcongif.JPG">
<br>
<img src = "https://raw.githubusercontent.com/Jeffreyg2240/Independent-Study-Java/master/images/server-client%20chat.gif">
<br>If you have over 4 people on the server.
<img src = "https://raw.githubusercontent.com/Jeffreyg2240/Independent-Study-Java/master/images/Limit.gif">
<br>How I limited the # of people on the server to 4 using a __"for"__ function.
<img src = "https://raw.githubusercontent.com/Jeffreyg2240/Independent-Study-Java/master/images/howlim.gif">
<br>One of my biggest bugs is my method of limiting the number of people within the server. Example: say the limit is 4 clients, 4 clients join, then 1 leaves, but the next person who joins is registered as the 5th number of the array, I could remove the 4th person of the array, but all the names of the clients would be clustered, thus removing the value from the # that the client was would do no benefit since the next client would still have to mark as the last, 4th. My one solution in mind is to limit the clients from the game, instead of the server side, over 4 people can connect, but only the first 4 can be players, the rest can spectate only, or use the chat client.


*For the next week, I hope to polish up the little chat client and to test it across different computers since I haven't gotten a chance to test it yet. After that, I hope to create a chat client on the front end. Catching up on JavaFX would come after all this.*
<br>Once I have a better understanding of sockets and serverSockets and are able to use them in the front end, then I'll write add them into my blog entry.
<br>

#### Converting to JavaFX:

Unfortunately, during we weekend, we decided to proceed with JavaFX, which means I have to backtrack 2 weeks of work since I was only learning swing and AWT. JavaFX was removed from JDK 11 but could be imported externally. JavaFX was the “successor” to swing and AWT. To make our lives simpler, we decided to transport everything back to JDK 8, before JavaFX was removed.


<br>From here I had to relearn all the basics of JavaFX, from creating a new frame like JFrame in swing to animations. Since writing this blog, I still have more work to catch on. 
<br><img src = "https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/s2048x2048/60384231_2325709027452249_3926603296940228608_n.jpg?_nc_cat=100&_nc_ht=scontent-lga3-1.xx&oh=c9a2f31e53b85173070494663debeb6b&oe=5D6B1744" width = "900px">


#### Takeaways:
__Things will always not go as expected__, espically if you move too far ahead without a goal. In my case I didn’t have a endgame goal/idea. When we decided to start working, Wei found it much easiler to use JavaFX, while I was already a few weeks within swing and AWT, but after a bit of researched I found that they’ve stopped updating swing and AWT and moved on to JavaFX. Although I was suprising to see that JavaFX was remoed in JDK for some unbeknownst reason.

####  Notes:

<br>
This took way to much time for me to learn about how to run multiple instances of the same class on __IntelliJ__.
<br>The following is a GIF to show to enable parallel run and make compounds, which allows for multiple files to be run with one click.
<img src = "https://raw.githubusercontent.com/Jeffreyg2240/Independent-Study-Java/master/images/multi-inst.gif">
<br>
For anyone curious, I am running my Java program based of a server-client system
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Client-server-model.svg/1200px-Client-server-model.svg.png">
Although I'll still have to test this on the school computers to see if it works.

<br>
<b>[&larr; Back](Entry_5.md)  | [Next &rarr;](Entry_7.md) | [README](../README.md)</b>
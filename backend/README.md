<h1>HQ Trivia - NodeJS</h1>

<h3>The story behind this repo</h3>
I saw my friend playing this game and I asked him what is it? He explained to me that it was a game where you can win real cash. I didn't believe it at first but I gave it a chance and tried it. It was 2:57pm and I was waiting for the game to start. The game starts ... and I lost after three questions. - By the way, the mobile app looked really good ( really nice job UI/UX ) - I was really curious about how the platform is able support that many people at the same time. I was asking myself what protocol did they use to do so? After digging, I found out they're using WebSockets. One questions bringing another, I decided to challenge myself and try to create my own HQ Trivia client before the next game which was the same day at 9pm. I had fewer than 6 hours to find out how everything was done. And I did...

<h3>Why am I putting this public ?</h3>
At first, I wanted to create a web platform where people could have helped each other by clicking the answers they think's good and see the counter in real time. But I changed my mind and I just decided to put this code public for people to learn how big apps communicate with a server. Another reason, is that I tried to contact HQ Trivia many times, but no answer. So I guess this might draw their attention.

<h3>How to install the packages ?</h3>
Assuming that you already have [NodeJS](https://nodejs.org/en/download/) installed and cloned this repo locally, here's the first command to install the packages needed.

``
npm install
``


<h3>How to run the script ?</h3>
As simple as it is with NodeJS, all you have to do is run this command:

``
node HQTrivia.js
``

After running this command, you'll need to insert your phone number in the terminal. Once it's done, the script will try to send a request to HQ Trivia server's asking it to send you a verification code. Once you receive the verification code on your phone, insert it in the terminal. Then it should log you in and retrieve your Authkey.

This Authkey is going to be useful for the client connection protocol and sockets transfers. You actually need only to login only once since the Authkey doesn't expire (weirdly......)

Then the script waits for a game. Once there's an active game, the script will run the next script, which is **HQClient.js**. This is the client that communicates with the game server.



<h3>What does the HQClient.js do ?</h3>

Basically, once there's an active game, it'll get the Authkey previously set by HQTrivia.js in a text file and will try to login to the current live broadcast. Then the magic happens, once some questions will be asked by the host, they'll appear in the console and wait for you to answer.


<h3>What can you do more ?</h3>
You can easily use the script to make Google Searches, or whatever you think is relevent (keywords extraction and comparaison..), I started creating a machine learning feature that could be helpful to predict the answers based on the correlation between the sentence and each words, giving it a score. Since it can be mainly used to cheat, I didn't add this to the repo but it wouldn't be hard, since you already have the questions and the choices of answers, to reproduce what I did.


<h3>Anything better than the real client ?</h3>
What's good about getting the requests and display the question right away is that you don't have to wait for any animation to be done or for the host to read the question. So sometimes, you have the question one second before the host announces it. What is good also, is that, I don't know why but the server returns the category of the question. Not being used by the client, as far as I know, it shouldn't be something that is sent by the server.


<h5>If you need private discussions about this script, how I traied the model to predict the answers or anything related to reverse engineering, I will be glad to help you. The best way is to contact me throught email: sofiane.soufi@mone.ca</h5>
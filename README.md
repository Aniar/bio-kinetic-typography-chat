# Physiological Kinetic Typography Chat

This is an instant messenger which currently just operates between multiple browsers, pointing to localhost:3000, on one computer. After setting a username, by clicking on the '+' tab on the left hand sign you will be able to see your messages animated based on your physiological state. If you go back into the message history, you can click on any of the messages to see it animated again based on your physiological state at that point in time. Whenever a user sends a message, it is animated and overrides whatever animated message is currently playing. Messages are assigned a numerical ID and they are assigned an animation which is stored in an array based on their ID number. The assigned animation is determined by the most dominant relative band power at that current moment, but if the user's heart rate and skin conductance are above average levels then the assigned animation will be the 'stress' animation.

# Instructions for Testing:

1. cd bio-kinetic-typography-chat
2. node index.js
3. Go to http://localhost:3000 in a browser
4. Open another browser with the same url to communicate between the two browsers

# Instructions for Running with Muse and Empatica E4:

1. In index.js, uncomment the code to send Muse data and comment out the setInterval function. In the text folder, delete all the data in ibiData.txt and gsrData.txt and leave them blank.
2. Do the above instructions 
3. Pair the Muse headset with the computer via Bluetooth
4. In new tab on terminal: npm install
5. npm start
6. After logging in, click on the 'Connect to Muse' button to start sending the data
7. If the Muse keeps disconnecting, try repairing it on Bluetooth or check to see if there are extra Muse processes running, ps aux | grep 'muse-io', and stop them
8. Next, open a browser at your computer's IP address at port 8080
9. Turn on a smartphone and hook it up to your computer via USB
10. Open EmpApp in Android Studio
11. In MainActivity.java, method didVolleyPost(), set the 'url' variable equal to your IP address at port 8080
12. In new tab on terminal: cd bio-kinetic-typography-chat/public
13. php -S {IP address}:8080
14. In Android Studio, run the code and turn on the E4 wristband once the white screen pops up on the phone
15. All the data should show up on the phone screen, but it takes 20-60 seconds for IBI data to show up. The data won't be sent to the server until IBI data is read
16. After you are finished with the chat, stop the app and make sure to clear the text files for the next time around

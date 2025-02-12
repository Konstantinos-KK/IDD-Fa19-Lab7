# Video Doorbell, Lab 7

*A lab report by Konstantinos Karras Kallidromitis*

### In This Report

1. Upload a video of your version of the camera lab to your lab Github repository
1. As usual, update your class Hub repository to add your [forked IDD-Fa18-Lab7](/FAR-Lab/IDD-Fa18-Lab7) repository.
1. Answer the questions in-line below on your README.md.

## Part A. HelloYou from the Raspberry Pi

**a. Link to a video of your HelloYou sketch running.** [Video](https://www.youtube.com/watch?v=QEEFubCHCh4)

## Part B. Web Camera

**a. Compare `helloYou/server.js` and `IDD-Fa18-Lab7/pictureServer.js`. What elements had to be added or changed to enable the web camera? (Hint: It might be good to know that there is a UNIX command called `diff` that compares files.)**
To add a webcam functionality the file also includes the webcam variable "var NodeWebcam" as well as the deafualt parameters and fucntion "'takePicture', function()".

**b. Include a video of your working video doorbell** [Video](https://www.youtube.com/watch?v=oabhYpd3rR8)


I added the socket.emit('takePicture') in the case "light":
```js
socket.on('server-msg', function(msg) {
  msg = msg.toString();
  console.log('msg:', msg);
  switch (msg) {
    case "light":
      socket.emit('takePicture')
      document.body.style.backgroundColor = "black";
      console.log("white")
      break;
    case "dark":
      document.body.style.backgroundColor = "rgb(255,0,0)";
      console.log("black");
      break;
    default:
      //console.log("something else");
      break;
  }
});
```

## Part C. Make it your own

**a. Find, install, and try out a node-based library and try to incorporate into your lab. Document your successes and failures (totally okay!) for your writeup. This will help others in class figure out cool new tools and capabilities.**
I decided to go a doorbell related to elon musk memes. I changed the html file. I also used the fswebcam library and changed brightness (fswebcam −−set brightness=50%) and other settings to improve the resolution.

**b. Upload a video of your working modified project** [Video](https://www.youtube.com/watch?v=Xn53MSCFeng)

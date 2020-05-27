# gopherdance
some dancing gophers in your terminal, my followup to terminalman..

heres how I make these files.. find a nice image, or animated gif that you want to use in your terminal.
download and compile pixterm --> https://github.com/eliukblau/pixterm

then find your image, split it into the individual frames (gif2jpeg or whatever tool you want to use)

use pixterm to display a frame in your terminal... where frame.jpg is on of your image frames
```./pixterm -s 2 -tc 25 -tr 25 frame.jpg```

if it looks good, run

```./pixterm -go -s 2 -tc 25 -tr 25 frame1.jpg >> frames.go```
```./pixterm -go -s 2 -tc 25 -tr 25 frame2.jpg >> frames.go```
.. run the command for each frame in your animation, it saves it all in the frames.go file..

the frames.go file, convert the fmt.Printf("") statements to a string array, use your text editors column edit function (shift + right click in sublime) to easily edit the file into this format:

```var animationFrames = []string {
       "",
       "",
       "",
   }```
   





# gopherdance
some dancing gophers in your terminal, my followup to ![terminalman](https://github.com/80at8/terminalman)..
![dancing gophers](https://github.com/80at8/gopherdance/blob/master/gopherdance.gif)

heres how I make these files.. find a nice image, or animated gif that you want to use in your terminal.
download and compile pixterm --> https://github.com/eliukblau/pixterm

then find your image, split it into the individual frames (gif2jpeg or whatever tool you want to use)

use pixterm to display a frame in your terminal... where frame.jpg is on of your image frames such as:

```./pixterm -s 2 -tc 25 -tr 25 frame.jpg```

if it looks good, run

```./pixterm -go -s 2 -tc 25 -tr 25 frame1.jpg >> frames.go```

```./pixterm -go -s 2 -tc 25 -tr 25 frame2.jpg >> frames.go```

.. run the command for each frame in your animation, it saves it all in the frames.go file..

the frames.go file, convert the fmt.Printf("") statements to a string array, use your text editors column edit function (shift + right click in sublime) to easily edit the file into this format:

```
   var animationFrames = []string {
       "",
       "",
       "",
   }
 ```
   
replace the "" with the ansi-escaped Printf strings that pixterm generates.. you should now have a string array of each animation frame. 

To figure out your individual frame sizes.. use a helper function such as

```
   func drawFrameIndex() {
       for i,v := range animationFrames {
          fmt.Printf("%d %v",i,v)
       }
   }
```

Then run it and it will print out all the frames, with the index values.. figure out the start/end ranges of each frame (I do it by hand but I suppose you could do it programmatically)..

as for the rest.. check out the code to see how it draws the frames based on the counters. It just does a lookup on the initial index and adds the frame length, and draws it at the l,c (line,column or x,y) on the terminal.











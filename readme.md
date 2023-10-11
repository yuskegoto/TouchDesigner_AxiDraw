# About
A TouchDesigner project to control AxiDraw directly. It take sound input and draw a spiral. Pen position is controlled by sound volue, resulting an interesting sound record look drawing, although it is not the sound recording in strict sense.

Background: I've been interested in generative plotting but the projects you can find on the internet are almost all pre-rendered, means you need to prepare source data in advance. I'm rather interested in realtime interaction using TouchDesigner. I've built several realtime motor control projects using G-Code before, so I thought it should be possible to realtime-control AxiDraw too.

## Disclaimer
**This is a simple hobby project and I did not build any safe measurement or done tests. Please understand that I'm unable to take responsibility for any damage caused by this project.**


![Dots](https://raw.githubusercontent.com/yuskegoto/TouchDesigner_AxiDraw/main/Pics/dots.jpg)

![Spiral](https://raw.githubusercontent.com/yuskegoto/TouchDesigner_AxiDraw/main/Pics/spiral.jpg)

![Control Interface](https://raw.githubusercontent.com/yuskegoto/TouchDesigner_AxiDraw/main/Pics/interface.png)

## Basic Idea
Since all plotters including AxiDraw need moving data in advance, it is not inherently adequate for realtime control. My workaround is to split the movement in small time frames, around 10Hz and able to move the head in quasi-realtime. 

## Project
Project is build on TouchDesigner 2022.33910
3D folder contains jig I built for the pen holder.

## How to use
1. Open AxiDraw.toe
1. Open /project1/container2/audiodevin1 and select your sound device.
1. Connect the AxiDraw to your computer.
1. Goto /project1/container1/serial1 and select the plotter device from Port.
1. Go up to /project1 and click OpenWidow button. window1 and 2 will pop up.
1. Before opening serial, move the plotter head to bottom left, where the main board controller is.
1. In widow1 click 'OpenSerial'. Click 'EnableMotors' and make sure that the head is locked now.
1. Clicking Go_Centre will bring the head to plotfield centre.
1. Set parameters in window2. It is recommended to run tests before plotting on the actual paper.
1. Reset the drawing.
1. Make sure pen and paper are set correctly, and click 'EnableMovement'.
1. Click run in the window2. You don't need to lower the pen, it should automatically move to the drawing position.
1. In case anything happened, click Stop botton. Or probably you would rather want to jump on to the plotter.

## Pens I used
- Pilot Juice up 04
- Bic Easy Glide
- Stabilo Point 88
- Mitsubishi Uni Signo DX 0.28

# Known Issue
- Pen delays about 10 sec after running more than 10 min. Presumably due to unexeuted and buffered moving commands. Reduing conrol frequency from 20Hz to 10 Hz won't change the situation.
- Patch is hard to read and messy. The author should spend more time for cleaning up and documentation.

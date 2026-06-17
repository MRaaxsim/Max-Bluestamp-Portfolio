


# Blue Stamp Robotic Arm
During this project I built and modified a robotic arm to perform better in the ability to lift irregular objects and grip strength. In order to do this I design a 3d printed part that is able to morph to objects the arm is picking up. Throughout the project I learned the basics of C++ code and ciurcutry while exploring the field of mechanical engineering. 

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Max R| Las Lomas | Mechanical Engineering | Incoming Junior

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

- I have installed and coded a button that can set the arm to a home position. This contributes to my final goal by reducing variability in my testing because now I know exactly where the claw will be for each test.
- I have designed a modification to the claw where TPU (flexible fillament) can exented about a milimeter beyond the end of the claw to hopefully give extra grip. I went through a design process that included 3 improvements the first design consisted of two parts that I would have had to glue together to instal. In the second itteration I improved the design by changing it so that the print slid directly onto existing hex nuts. Then the last itterition I included a honeycomb hole design that would hopefully allow the TPU to bend and deform more. 
<img width="837" height="360" alt="Screenshot 2026-06-15 at 1 28 36 PM" src="https://github.com/user-attachments/assets/b6f88237-30cd-4753-90e4-d4799cd7a8ea" />

- Top part of first itteration

<img width="864" height="210" alt="Screenshot 2026-06-15 at 1 28 59 PM" src="https://github.com/user-attachments/assets/c13d155b-2383-4bd0-8b1b-3a617ddea629" />

- Bottom part of first itteration

<img width="814" height="425" alt="Screenshot 2026-06-15 at 1 29 13 PM" src="https://github.com/user-attachments/assets/d7a2e012-37bb-4fba-ad02-f4985cf5248e" />

- Seccond itteration

<img width="806" height="424" alt="Screenshot 2026-06-15 at 1 29 35 PM" src="https://github.com/user-attachments/assets/3ade97c9-9904-4ec6-8995-cfff8270253c" />

- Third itteration
(all images are just one side of the claw)

- It has surprised me how much progress I can make by just continueing to work and not making excusses. Before starting, I viewed circuitry and programming as highly complex subjects. However, by working with them directly and learning through experimentation, I found that both became much more approachable than I originally expected. This experience has increased my confidence in my ability to learn new technical skills and solve engineering problems independently.
- The most challenging part of these modifications where figuring out exactly how far apart the hex columns in the arm so that the print can slide onto them freely. 
- Before my final milestone video I need to design and run tests to see if there is any improvement in my design compared to the base project in areas like grip strength 

# First Milestone


<iframe width="560" height="315" src="https://www.youtube.com/embed/ooU_6ly1Pko?si=njtz1Ol57xPyF3qm" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


- There are three main components in this project: the controller, the circuitry, and the robotic arm. The controller allows the user to input the desired position of the arm, which is sent as electrical signals to the circuitry. The Arduino processes these signals and sends instructions to the servo motors, which control the movement of the arm's joints. Together, these components form an integrated system that converts user input into precise physical movement. 
- So far I was able to fully assemble the robotic arm and I have uploaded the code that came with this project to my Arduino. I have also learned how the code translates joystick movements into the movement of the actual arm. Understanding the software allows me to modify the arms behavior or add new features in the future. 
- Throughout this project I have learned the basics on how to use tinkerCAD to create schematics (seen bellow) and I gained a foundational understanding of C++ to by examining the arm code.
- My plan to complete this project is in three stages: firstly I to complete the base project, hardware and software, next I want to focus on brainstorming and developing modifications to my project that may include an addaptive 3d printed gripper design that can conform to the shape of the objects it picks up, lastly I want test the modifications I made to see if they actually help in areas of grip strength, grip duration and the ability to hold irregular objects. 

# Schematic 
A few notes about the schematic:
1. There are four potentiometers (dials) and each pair represents one joystick moving in the x and y directions.
2. The battery regulator is built into the Nano Sensor shiled but they dont have this in TinkerCAD so I had to use a seperate batery regulator.
3. To replecate the embeded internal power tracers of the Nano both the ground and power cables for the actuators (servos) and analog inputs (potentiometers) are connected together before attaching to the nano this eliminates the need for an extra breadboard. 
<img width="1064" height="822" alt="Screenshot 2026-06-16 at 1 21 42 PM" src="https://github.com/user-attachments/assets/29a25a96-401a-45ce-af5a-9966fdce5165" />


# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
#include "src/CokoinoArm.h"
#define buzzerPin 9

CokoinoArm arm;
int xL,yL,xR,yR;

const int act_max=10;    //Default 10 action,4 the Angle of servo
int act[act_max][4];    //Only can change the number of action
int num=0,num_do=0;
const int buttonPin = 8;
///////////////////////////////////////////////////////////////
void turnUD(void){
  if(xL!=512){ //  512 is the middle value or when the joystick is centered it ranges from 0 all the way left to 1024 all the way right
    if(0<=xL && xL<=100){arm.up(10);return;}
    if(900<xL && xL<=1024){arm.down(10);return;} 
    if(100<xL && xL<=200){arm.up(20);return;}
    if(800<xL && xL<=900){arm.down(20);return;}
    if(200<xL && xL<=300){arm.up(25);return;}
    if(700<xL && xL<=800){arm.down(25);return;}
    if(300<xL && xL<=400){arm.up(30);return;}
    if(600<xL && xL<=700){arm.down(30);return;}
    if(400<xL && xL<=480){arm.up(35);return;}
    if(540<xL && xL<=600){arm.down(35);return;} 
    }
}
///////////////////////////////////////////////////////////////
void turnLR(void){
  if(yL!=512){
    if(0<=yL && yL<=100){arm.right(0);return;}
    if(900<yL && yL<=1024){arm.left(0);return;}  
    if(100<yL && yL<=200){arm.right(5);return;}
    if(800<yL && yL<=900){arm.left(5);return;}
    if(200<yL && yL<=300){arm.right(10);return;}
    if(700<yL && yL<=800){arm.left(10);return;}
    if(300<yL && yL<=400){arm.right(15);return;}
    if(600<yL && yL<=700){arm.left(15);return;}
    if(400<yL && yL<=480){arm.right(20);return;}
    if(540<yL && yL<=600){arm.left(20);return;}
  }
}
///////////////////////////////////////////////////////////////
void turnCO(void){
  if(xR!=512){
    if(0<=xR && xR<=100){arm.close(0);return;}
    if(900<xR && xR<=1024){arm.open(0);return;} 
    if(100<xR && xR<=200){arm.close(5);return;}
    if(800<xR && xR<=900){arm.open(5);return;}
    if(200<xR && xR<=300){arm.close(10);return;}
    if(700<xR && xR<=800){arm.open(10);return;}
    if(300<xR && xR<=400){arm.close(15);return;}
    if(600<xR && xR<=700){arm.open(15);return;}
    if(400<xR && xR<=480){arm.close(20);return;}
    if(540<xR && xR<=600){arm.open(20);return;} 
    }
}
///////////////////////////////////////////////////////////////
void date_processing(int *x,int *y){
  if(abs(512-*x)>abs(512-*y))
    {*y = 512;}
  else
    {*x = 512;}
}
///////////////////////////////////////////////////////////////
void buzzer(int H,int L){
  while(yR<420){
    digitalWrite(buzzerPin,HIGH);
    delayMicroseconds(H);
    digitalWrite(buzzerPin,LOW);
    delayMicroseconds(L);
    yR = arm.JoyStickR.read_y();
    }
  while(yR>600){
    digitalWrite(buzzerPin,HIGH);
    delayMicroseconds(H);
    digitalWrite(buzzerPin,LOW);
    delayMicroseconds(L);
    yR = arm.JoyStickR.read_y();
    }
}
///////////////////////////////////////////////////////////////
void C_action(void){
  if(yR>800){
    int *p;
    p=arm.captureAction();
    for(char i=0;i<4;i++){
    act[num][i]=*p;
    p=p+1;     
    }
    num++;
    num_do=num;
    if(num>=act_max){
      num=0;
      buzzer(600,400);
      }
    while(yR>600){yR = arm.JoyStickR.read_y();}
    //Serial.println(act[0][0]);
  }
}
///////////////////////////////////////////////////////////////
void Do_action(void){
  if(yR<220){
    buzzer(200,300);
    for(int i=0;i<num_do;i++){
      arm.do_action(act[i],15);
      }
    num=0;
    while(yR<420){yR = arm.JoyStickR.read_y();}
    for(int i=0;i<2000;i++){
      digitalWrite(buzzerPin,HIGH);
      delayMicroseconds(200);
      digitalWrite(buzzerPin,LOW);
      delayMicroseconds(300);        
    }
  }
}
///////////////////////////////////////////////////////////////
void setup() {
  //Serial.begin(9600);
  //arm of servo motor connection pins
  arm.ServoAttach(4,5,6,7);
  //arm of joy stick connection pins : xL,yL,xR,yR
  arm.JoyStickAttach(A0,A1,A2,A3);
  pinMode(buzzerPin,OUTPUT);
  pinMode(buttonPin, INPUT_PULLUP);
}
///////////////////////////////////////////////////////////////
void loop() {
  xL = arm.JoyStickL.read_x();
  yL = arm.JoyStickL.read_y();
  xR = arm.JoyStickR.read_x();
  yR = arm.JoyStickR.read_y();
  date_processing(&xL,&yL);
  date_processing(&xR,&yR);
  turnUD();
  turnLR();
  turnCO();
  C_action();
  Do_action();
 // Senses if the button is pressed if so it sets it to this position
  if (digitalRead(buttonPin) == LOW) {
    arm.servo1.write(88);
    arm.servo2.write(41);
    arm.servo3.write(145);
    arm.servo4.write(60);
  }
 // To be able to read and set the home positoin based off of the values set
 Serial.print("S1: ");
 Serial.print(arm.servo1.read());
 Serial.print("  S2: ");
 Serial.print(arm.servo2.read());
 Serial.print("  S3: ");
 Serial.print(arm.servo3.read());
 Serial.print("  S4: ");
 Serial.println(arm.servo4.read());


}
```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| LK COKOINO Robot Arm for Arduion | Base Kit for the Project | $46.99 | <a href="https://www.amazon.com/LK-COKOINO-Compliment-Engineering-Technology/dp/B081FG1JQ1"> Link </a> |
| California JOS 2 Pack 9V Battery Clip | Used to Connect Battery to Sensor Shield | $3.97 | <a href="https://www.amazon.com/Battery-Connector-Electronics-Experiment-Research/dp/B0D9VT2FMF/ref=sr_1_1?crid=163U4V185H3VT&dib=eyJ2IjoiMSJ9.tSn2e_UkWDzCZbfpVAtZGGpFSYNcVSV206P6mVl5W2890YLrZEJwCMCcgaNoeMYG6sv0KorBMH46WX143ip1fG_5ebjl6_xCWz60HfTHpexF_DrRpBPTeTTwBvj7wUA3X1MjOQbh52LUd15TQ9XzdLA1LuKLL7lLQF5A7QLAeZBeht3m-VdLn7aI1mCKjVl8UTi1KsDJJDEqfEPpZDE7jyWYzm26GFnq1CIpUss6oqg.9hBGbQx2V1LHHN5BNhFL85fRLKkV6ZEbRv4Pqp6K1_8&dib_tag=se&keywords=california%2Bjos%2B2%2Bpack%2B9v%2Bbattery%2Bconnector%2Bwith&nsdOptOutParam=true&qid=1781119176&sprefix=%2Caps%2C215&sr=8-1&th=1"> Link </a> |
| 5pcs Nano UNO I/O Extended Sensor Shield for Arduino | Used to replace sensor shield that came with the kit to be compatable with new battery | $9.96 | <a href="https://www.amazon.com/5pcs-Extended-Sensor-Shield-Arduino/dp/B0DCK1WKVW/ref=sr_1_6?dib=eyJ2IjoiMSJ9.Q7dsWH-xBzEBF88Afm5zKf8SCNNT4cDD8eynTINNc2AoQiNvshUWWA7WoRWGRZL-wgSXF7YTYVNwBFTs2BcgxIlzWY7TbNoo1PbbN6GHBNqrphe3r1ogdwkevMicshdU9XlPAYBlETU7Anmz-GrY-0RY8xM5xuyC1eem0On8-3QjOAQVXZ3qOnjpuQPNyI_m7rP5ukVbw1pGa782Jek06mEsSCAu_V_B0OlyAHbV13E.TqA2yU_d1S4defV1_9lY2zHV12ZUOZT82NbyhfgGJ6w&dib_tag=se&keywords=5+pcs+arduino+nano+shield&qid=1781119101&sr=8-6"> Link </a> |
| Amazon Basics 8-Count 9 Volt Alkaline Performance All-Purpose Batteries | Used as a safer battery alternative than the litium that came with the kit | $12.69 | <a href="https://www.amazon.com/Amazon-Basics-Performance-All-Purpose-Batteries/dp/B00MH4QM1S/ref=sr_1_1?"> Link </a> |
| WWZMDiB 6 Pcs Mini Small Breadboard kit White 170 Tie Points | Used as a small breadboard for both button and buzzer | $5.99 | <a href="https://www.amazon.com/WWZMDiB-SYB-170-Breadboard-Plates-Multicolored/dp/B09YXQJMTG/ref=pd_sbs_d_sccl_1_1/141-5358882-0016108?pd_rd_w=NMs12&content-id=amzn1.sym.aa738fbd-ad05-4d11-aae2-04b598db6305&pf_rd_p=aa738fbd-ad05-4d11-aae2-04b598db6305&pf_rd_r=F12TJX750FKJCJ3ZVT5M&pd_rd_wg=gA9dh&pd_rd_r=3dc6270d-0229-4ba0-a953-e2ca7123292f&pd_rd_i=B09YXQJMTG&psc=1"> Link </a> |

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.

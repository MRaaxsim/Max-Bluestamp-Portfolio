
# Blue Stamp Robotic Arm
Replace this text with a brief description (2-3 sentences) of your project. This description should draw the reader in and make them interested in what you've built. You can include what the biggest challenges, takeaways, and triumphs from completing the project were. As you complete your portfolio, remember your audience is less familiar than you are with all that your project entails!

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

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your first milestone, describe what your project is and how you plan to build it. You can include:

- There are three main components in this project: the controller, the circuitry, and the robotic arm. The controller allows the user to input the desired position of the arm, which is sent as electrical signals to the circuitry. The Arduino processes these signals and sends instructions to the servo motors, which control the movement of the arm's joints. Together, these components form an integrated system that converts user input into precise physical movement. 
- Technical progress you've made so far
- Challenges you're facing and solving in your future milestones
- My plan to complete this project is in three stages: firstly I want to focus on hardware completing the actual arm, next I want to focus on coding and testing the arm to make sure that my base project works, lastly I want to add some extensions that may include having a wireless control and and a 3d printed gripper design that can conform to the shape of the objects it picks up. 

# Schematics 
A few notes about the skematic:
1. There are four potentiometers (dials) and each pair represents one joystick moving in the x and y directions.
2. The battery regulator is built into the Nano Sensor shiled but they dont have this in TinkerCAD so I had to use a seperate batery regulator.
3. To replecate the embeded internal power tracers of the Nano both the ground and power cables for the actuators (servos) and analog inputs (potentiometers) are connected together before attaching to the nano this eliminates the need for an extra breadboard. 
<img width="1056" height="811" alt="Screenshot 2026-06-09 at 2 30 11 PM" src="https://github.com/user-attachments/assets/6b040867-40fd-48e8-adb4-464591d8a8b3" />
[Robotic Arm Wiring.pdf](https://github.com/user-attachments/files/28771700/Robotic.Arm.Wiring.pdf)


# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

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
| Amazon Basics 8-Count 9 Volt Alkaline Performance All-Purpose Batteries | Used as a safer battery alternative than the litium that came with the kit | $12.69 | <a href="https://www.amazon.com/Amazon-Basics-Performance-All-Purpose-Batteries/dp/B00MH4QM1S/ref=sr_1_1?"> Link </a>

# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.

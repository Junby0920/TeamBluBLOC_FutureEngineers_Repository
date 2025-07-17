The Arduino powered self driving car which the BluBLOC team
representatives designed for the PRO Future Engineers "Self Driving Car"
competition has several modules and Arduino components designed to
replicate the fundamentals of autonomous driving.

The Arduino board connects with different sensors and motors on the car.
These parts work together to help the vehicle move forward, backward,
steer, and detect surroundings/obstacles The main components we used
include a servo motor (SG90 servo) for steering, a TT DC Gearbox Motor
for driving forward and backward, ultrasonic sensors (HC-SRO4) for
obstacle detection, and a color sensor (TCS3200) for recognizing the
colors of the pieces on the board. Lastly, a Motor Driver Shield ( Dual
Channel DC Motor Driver), connected directly onto the Arduino was used
to send data for the movement of the DC motors.

The team designed their own chassis for this project, encasing the
breadboard with its wires in a snug compartment for stability. It was
designed with a shelf-like compartment above the main chassis, to encase
their Arduino Uno, the Motor Driver Shield modifier, and the 9V battery
to power the entire mechanism. Underneath the main body, encased a servo
motor and the Gearmotor modules for the steering and movement of the
car. Around the frame, the team also secured the four distance sensors
of all directions and the color sensor. This entire schematic was
constructed from scratch by the members of the team and was then 3D
printed.

First, we used the servo motor connected to analog pin A0. This motor
helps steer the wheels left and right. The code tells the servo to move
to a certain angle, which turns a gear in a "rack and pinion" system,
where the pinion connected to the servo meshes with a rack, sliding it
left or right. This sliding motion is connected to a steering hinge
mechanism placed parallel to the rack. The rack is attached to a
hinge-like part, which acts as the steering arm where the wheel is
connected and free to rotate. As the rack moves, the hinge twists
slightly, causing the front wheels which are mounted on the hinge to
turn left or right. This setup allows the servo to indirectly steer the
wheels by converting its rotational motion into a side to side motion
and then angular turning.

The DC motor, controlled through the Out A and Out B pins on the arduino
shield, was responsible for making the car go forward or backward. The
code adjusts the motor speed and directions which are depending on the
sensor reading around the vehicle. A simple gearbox system was put under
the chassis of the car, where a small gear is directly connected to the
motor. A bigger gear is meshed to this small gear to add more torque.
The bigger gear is connected to an axle which powers the drive wheels at
the back.

The ultrasonic sensors help the car know how close it is to walls or
obstacles. The car has four sensors: one in the front, one in the back,
one on the left side, and one on the right side. The echo pins of the
left, right, front and rear servo are connected to pin 3, 4, 7, and 9
respectively. Their trig pins are connected to pins A1, 5, 6, and 8 in
the same order. These sensors work by sending out sound waves and
measuring how long it takes for them to bounce back. From this, Arduino
can calculate the distance of the nearest object. All sensors activate
when something is around 15-20cm away. In the code, if the rear sensor
detects something that is very close (such as a wall), the car moves
forward. If the front sensor detects something close, the car moves
backward. If something is close to the right or left side, the car
steers in the opposite direction to avoid it.

The color sensor was stationed in front of the car in a way that it will
recognize the colors of the map without obstruction of the main chassis
and proper distancing from the obstacles. As the rules describe, this
will be the main recognition method in the obstacle round, where the car
will turn left when the obstacle is green, and right if red. The team
also plans to apply the color recognition to the magenta walls that will
guide the car to its parallel parking sequence. Upon the completion of
one lap, when the car recognizes the magenta walls, it will repeat its
driving sequence until it completes three laps. Only when it completes
the laps required, will it begin a parallel parking sequence.

The code is uploaded into the Arduino Uno through an Arduino Uno USB
cable connecting the system to the team's laptop. Here, the team could
verify and upload the code.

Overall, this project created by the BluBLOC varsity team of the Ateneo
de Manila involves combining sensory modules with motors using code to
create a basic self-driving car that can steer, avoid obstacles, and
keep track of laps for a parallel parking at the end. The code is
designed to run in real time and constantly read data from its
surroundings. By reacting to this data, the car can move around the
course on its own. This shows how programming and electronics, even done
using the most basic components of Arduino, can work together to make a
robot car that behaves like a smart vehicle, being able to do complex
tasks such as avoiding obstacles and performing a parallel park.

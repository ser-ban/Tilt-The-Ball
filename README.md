# Tilt the Ball Maze Game

## Bill of Materials

**Electronics:**
- 1× Arduino Uno
- 1× Analog joystick module
- 2× Servo motors (SG90 or similar, need enough torque for the platform)
- Jumper wires

**Mechanical:**
- Platform material (wood, acrylic, or sturdy cardboard, ~15x15cm)
- Ball (marble or small steel ball, 20-25mm diameter)
- Material for walls (same as platform or popsicle sticks)
- Servo mounting brackets (3D print or DIY from wood/cardboard)
- Base board for mounting everything

**Hardware:**
- Screws for servo mounting
- Glue (wood glue or hot glue depending on materials, TBD)

**Tools:**
- Hole saw or drill for cutting circular hazards
- Saw for cutting platform and walls
- Screwdriver
- Optional: 3D printer for brackets

**Optional:**
- Buzzer for sound effects
- LEDs for visual feedback
- External 5V power supply if servos cause voltage drop

---

## Preliminary Questions

**Q1 - What is the system boundary?**

The system includes the Arduino, joystick input, two servos controlling a platform, and the physical maze with a ball. It doesn't include the maze design/fabrication tools, external sensors, or any automated ball tracking.

**Q2 - Where does intelligence live?**

All intelligence is in the Arduino code. It reads the joystick position, maps those values to servo angles, and handles smoothing to prevent jittery movement. Optional features might include dead zones, acceleration limits, and custom control curves.

**Q3 - What is the hardest technical problem?**

The mechanical design and calibration. You need to mount the servos at the right angles, balance the platform weight so the servos can actually move it, tune the control sensitivity so it's playable (not too sensitive, not too sluggish), and set angle limits so the platform doesn't tilt so far that the ball flies off.

**Q4 - What is the minimum demo?**

A platform (around 15x15cm) that tilts in two axes controlled by the joystick, with at least one hole that the ball can fall through and one wall obstacle. The ball should visibly respond to tilting and be able to navigate around the wall or fall in the hole.

**Q5 - Why is this not just a tutorial?**

You have to design and build the actual physical maze - cutting holes, placing walls, figuring out servo mounting. The control algorithm needs tuning specific to your setup (dead zones, smoothing factors, angle limits). Solving real mechanical and control problems is a must, as opposed to just copying code.

**Q6 - Do you need an ESP32?**

No. Arduino Uno is fine. You only need 2 analog inputs for the joystick and 2 PWM outputs for the servos. ESP32 would only be useful if you wanted WiFi features like remote control or leaderboards.
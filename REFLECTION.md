# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Reflection on PID-Project

### What effects do P, I and D component have?

* The **P-component (Kp)** is responsible for how hard the vehicle steers back to the center. If this value is chosen to high, the vehicle starts oscillating. If this value is chosen to low, the vehicle needs longer to steer back to the center - This could be problematic espacially in turns.
* The **I-component (Ki)** is responsible for dealing with a systematic bias. In a real life situation, it occurs that the alignment of the wheels are not perfect - with the I-component, it is possible to deal with such biases.
* The **D-component (Kd)** is responsible for reducing the oscillation.

This graph from Sebastian's course visualizes the components very nicely:

<img src="PID.png" width="800">

### My Parameter

I used manual tuning for parameter optimization. I started with the following parameters:
``` c++
  double Kp = 1;
  double Ki = 1;
  double Kd = 1;
``` 

I run the simulation with these parameters - The car started to turn to the left, leaving the road. Then it turned back to the road and leaving the road on the right side. Obviously these parameters were not optimal so I used a manual, twiddle-like approach by increasing / decreasing each single parameter and observed the results in the simulation. 

**My final parameter are:**
``` c++
  double Kp = 0.2;
  double Ki = 0.0004;
  double Kd = 3;
``` 

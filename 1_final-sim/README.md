# Neural Body N-Body Simulator

An n-body simulator powered by a neural network.

Neural Body is an n-body simulator currently as an alpha demonstration of substituting 
calculations for planetary motion with a neural network.  Currently, the neural 
networks can predict the position of Mars or Pluto given the rest of the positions
in the planetary system from a simulator.

The eventual goal is to replace the physics simulator that calculates the positions
of other bodies  completely with neural networks that take in an acceleration 
vector on each body along with a desired simulation time step and perform the 
integration necessary to calculate the displacement of the body.

Considerable time was put into training the first version of the neural network 
which was a simple, 2 layer, feedforward neural network with 300 nodes per layer
that performed multiple-output regression on the x, y, z coordinates of the body
being predicted.  Input to the network was the position of every other body in the 
system at each time step of a previously run simulation.

Below is a Google Colab notebook that shows the output of a training run for the 
neural network that predicts Mars' position.  Code that generated the training 
data and performed preprocessing is not included.  Data file is also not included.
The link is purely to view code, learning curves, and results.

<a href="https://colab.research.google.com/drive/19-pUEmro6ajxLlUAPunM66i42gAaqrPz?usp=sharing" target="_blank"> Mars Neural Network Training </a>
<br>

---
## Table of Contents
- Installation
- Usage
- Documentation
- Team
- License

[![Game Overview Image](https://raw.githubusercontent.com/nedgar76/neural-body/demo-sim/0_demo-sim/readme_resources/overview_screenshot.png?token=ALC2NMM5G56RZFD237TQX32677FSA)]()
---
## Installation
### Requirements
- Compatible debian-based Linux distro.  Ubuntu 20.04 Preferred.
- Python 3.8 or higher.
- PyGame 2.0.0.dev10 or higher.
- TensorFlow 2.2.0
- Pandas 1.0.5
- Numpy 1.19.0
All dependencies above except for Python 3.8 should install when `pip install` is run.

### Setup

Installing from .tar.gz:
- Download `neural_body-0.1.2.tar.gz` from the `dist` directory.
- Navigate to local folder where download is located.
- Use `pip install neural_body-0.1.2.tar.gz`
- Use the `neural_body` command to run the simulator from terminal.

Installing from PyPi:
- PyPi project page is located <a href="https://pypi.org/project/neural-body/" target="_blank"> here </a>
- Use `pip install neural-body`
- Use the `neural_body` command to run the simulator from terminal.

---
## Usage
This selection includes an overview of all menu buttons and functionality of the simulator.

### Pause / Play
The simulation can be paused at any point.
![Setup Overview GIF](https://github.com/nedgar76/neural-body/blob/demo-sim/0_demo-sim/readme_resources/play_pause.GIF?raw=true)
### Toggle View
The simulation view can be toggled from overhead to side view.
![Setup Overview GIF](https://github.com/nedgar76/neural-body/blob/demo-sim/0_demo-sim/readme_resources/toggle_view.GIF?raw=true)
### Adjust Speed
The simulation can be sped up or slowed down.
![Setup Overview GIF](https://github.com/nedgar76/neural-body/blob/demo-sim/0_demo-sim/readme_resources/adjust_speed.GIF?raw=true)
### New Simulation
The initial state of all bodies in the system are contained in CSV files packaged
with the simulator.  Whichever planet is designated as the "satellite" tells the 
simulator which neural network to use for planetary motion prediction.  This early 
demo can only predict the motion of Mars or Pluto given the positions of the other
planets in the system.  In later releases, the neural network will be updated to 
accommodate predicting the motion of any body.

Current Config File Options:
- mars_sim_config.csv
- pluto_sim_config.csv

![Config File Overview](https://github.com/nedgar76/neural-body/blob/demo-sim/0_demo-sim/readme_resources/config_overview.png?raw=true)
![Setup Overview GIF](https://github.com/nedgar76/neural-body/blob/demo-sim/0_demo-sim/readme_resources/new_simulation.GIF?raw=true)
### Is NASA Right?
If you disagree with NASA, you can bring Pluto back as a planet.  
![Setup Overview GIF](https://github.com/nedgar76/neural-body/blob/demo-sim/0_demo-sim/readme_resources/is_nasa_right.GIF?raw=true)
### Show Planet Key
Hovering over this option displays a color coded key of all planets in the system.
![Setup Overview GIF](https://github.com/nedgar76/neural-body/blob/demo-sim/0_demo-sim/readme_resources/show_planet_key.GIF?raw=true)
### Travel to a Day
Selecting this option allows the user to rewind or fast forward the simulation by 
entering the day they would like to jump to.  There is a heavy delay for fast forwarding
as the simulator right now must inefficiently calculate every frame between the current
day and the day you entered.  Negative time values will be treated as reverting 
back to 0 day.
![Setup Overview GIF](https://github.com/nedgar76/neural-body/blob/demo-sim/0_demo-sim/readme_resources/travel_to_a_day.GIF?raw=true)


## Documentation
To view the documentation online, go to the following URL: \
<a href="https://nedgar76.github.io/neural-body/" target="_blank"> Neural Body Sphinx Documentation </a>

Documentation for the source compiled with Sphinx is included in the `neural-body/0_demo-sim/docs/_build/html/`
folder.  You will need to download and host yourself by running `python3 -m http.server --directory _build/html`
---
## Team
The AstroGators formed as a result of the "CIS4930 - Performant Python Programming" 
course at the University of Florida developed by 
<a href="https://www.eng.ufl.edu/eed/faculty-staff/jeremiah-blanchard/" target="_blank"> Jeremiah Blanchard </a>

Team members include:
- Nathaniel Edgar
- Craig Boger
- Gary Jones
- Cory Robertson
- Andrew Sowinski
 
The Github repo for this initial demonstration is located at: 
<a href="https://github.com/nedgar76/neural-body/tree/demo-sim/0_demo-sim" target="_blank"> https://github.com/nedgar76/neural-body/tree/demo-sim/0_demo-sim </a>

## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
- Copyright 2020 ©
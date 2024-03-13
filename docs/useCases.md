# Use Case Specification

This file documents potential use cases for the SPA ontology.

### Use Case 1: An autonomous robot wants to pass through an automatic door.

<ins>Description:</ins> A robotic agent is in an environment consisting of two IoT devices: an intelligent power supply and an automatic door controller. 
Both devices need to be controlled by appropriate requests. To interact with these devices, the robotic agent must be able to parse the available interaction 
affordances and evaluate the preconditions and effects of each interaction to achieve its goal of opening the door.

<ins>Actors:</ins> robotic agent, automatic door controller, intelligent power supply. 

<ins>Flow:</ins> Arobotic agent sets the goal of opening the door, discovers and consumes the TD of the automatic door controller, and finds a link to the TD 
of the intelligent power supply, which the agent also consumes. Next, the agent evaluates all affordances, associated preconditions, and effects, and maps them to a 
PDDL planning problem. A PDDL planner then solves the planning problem and returns the sequence of interactions required to achieve the goal.

### Use Case 2: A sensor requires initialization before reading a property.

<ins>Description:</ins> A temperature sensor robotic agent wants to use a sensor that measures temperature. But the sensor needs to be initialized before the current measured temperature can be read.

<ins>Actors:</ins> robotic agent, temperature sensor. 

<ins>Flow:</ins> A robotic agent sets the goal of reading the current temperature of the temperature sensor. The agent discovers and consumes the TD of the sensor and evaluates all preconditions and effects, creates a PDDL planning problem,
and sets the goal to read the WoT temperature property. The PDDL planner solves the problem and tells the robot that the sensor needs to be initialized first and then the temperature property can be read.


### Use Case 3:  Material Handling in a Smart Factory.
<ins>Description:</ins> In a smart factory environment, a robotic agent is tasked with transporting raw materials to various processing machines. 
The environment includes three actors: a smart inventory management system, two smart processing machines, and a smart storage unit. The robotic agent, equipped with capabilities to interpret WoT TDs, evaluates to which processing machine the next raw material should be transported.
This is achieved by finding the processing machine where all the required preconditions are met.

<ins>Actors:</ins> robotic agent, smart inventory management system, smart processing machines, smart storage units.

<ins>Flow:</ins> The robotic agent sets the goal of transporting materials to the processing machine that can handle more raw materials. The robotic agent begins by consuming the TDs of the smart inventory management system, the smart processing machines, and the smart storage unit to understand all affordances, preconditions (e.g., machine readiness, material availability), and effects (e.g., machine processing time, storage capacity changes), and creates two PDDL planning problems, one for each processing machine. The planning problems are solved, and the robotic agent selects the one processing machine where all preconditions are already met.

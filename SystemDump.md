PROGmasters Exam – System Dump
You have been given the task to gather statistics about The System. The System is a network 
of components, connected together to build something which functions logically, but you 
don’t need to know that. You need to build a program which processes statistics about The 
System.
Overview
The System consists, mainly, of two types of components – Hardware and Software 
components.
Hardware components have a name, a maximum capacity and a maximum memory.
There are 2 types of Hardware components:
 Power Hardware – decreases 75% of its given capacity, and increases its memory 
by 75%.
 Heavy Hardware – doubles its given capacity, and decreases 25% of its given 
memory 
Software components have a name, capacity consumption and memory consumption.
 Express Software – doubles its given memory consumption.
 Light Software – increases its given capacity consumption by 50% and 
decreases its given memory consumption by 50%.
Example 1.: If a Power Hardware has 150 given capacity, his capacity will be – 75% 
from 150 =
150 – ((150 * 3) / 4)   =   
150 – (450 / 4)   =   
150 – 112 = 38
Note that you are working with INTEGERS.
Example 2.: If a Heavy Hardware has 200 maximum memory, his memory will be -25% 
from 200 =
200 – ((200 * 1) / 4)   =   
200 – (200 / 4)   =   
200 – 50 = 150
Note that you are working with INTEGERS.
Example 3.: If a Light Sotfware has 10 given capacity consumption, his real capacity 
consumption will be 10 + 50% of 10 = 15.
Software components are stored on Hardware components. Each Software component 
takes up a specific amount of capacity and a specific amount of memory from the 
Hardware, in order to function properly. When registered, a Software component is stored on
a specified Hardware Component.
There are several main commands you should configure in order for your program to function 
as needed.
Commands
 RegisterPowerHardware(name, capacity, memory)
 RegisterHeavyHardware(name, capacity, memory)
o Registers a Hardware component of the specified type on The System with the 
given name, capacity, and memory.
 RegisterExpressSoftware(hardwareComponentName, name, capacity, 
memory)
 RegisterLightSoftware(hardwareComponentName, name, capacity, memory)
o Registers a Software component of the specified type on the given Hardware 
component, with the
given name. The Software Component takes up from the hardware’s 
capacity and memory – the given capacity and memory.
o If the given Hardware component does NOT exist in The System, the command
should do nothing.
o If the given Hardware component does NOT have enough capacity or 
memory to contain the Software component, the command should do nothing.
 ReleaseSoftwareComponent(hardwareComponentName, 
softwareComponentName)
o Destroys the Software Component with the given name, from the Hardware 
Component with the given name.
o In case there is NO such Hardware Component, in The System, the 
command should do nothing.
o In case there is NO such Software Component, on the given Hardware 
Component, the command should do nothing.
 Analyze()
o Shows statistics about the components currently in The System in the 
following format:
“System Analysis
Hardware Components: {countOfHardwareComponents}
Software Components: {countOfSoftwareComponents}
Total Operational Memory: {totalOperationalMemoryInUse} / 
{maximumMemory}
Total Capacity Taken: {totalCapacityTaken} / {maximumCapacity}”
o The total operational memory in use and total capacity taken is calculated from 
all the Software components currently in The System. You must also print the 
maximum memory and capacity available from all the Hardware 
Components currently in The System.
 Dump()
o This command finalizes the work of the program, and prints information about 
the whole System.
o The System is closed, and all of the Hardware components are to be printed one
by one.
o The format of printing is the following:
“Hardware Component – {componentName}
Express Software Components: 
{countOfExpressSoftwareComponents}
Light Software Components: {countOfLightSoftwareComponents}
Memory Usage: {memoryUsed} / {maximumMemory}
Capacity Usage: {capacityUsed} / {maximumCapacity}
Type: {Power/Heavy}
Software Components: {softwareComponent1, 
softwareComponent2…}”
o Power Hardware Components must be printed before the Heavy Hardware
Components.
o When printing the Software Components, print only their names.
o In case the Hardware component does not have any Software Components, 
print “None”. 
o The general (secondary) order of output for all of the components is – by 
order of entrance.
Input
 The input will come in the form of commands, in the format – specified above.
 The input will consist only of the commands specified above.
 The input ends when you receive the command “Dump”.
Output
 The only output you must print is the one specified for the Analyze command, and the 
f
inal output.
 All of the output must be exactly in the format specified above.
Constraints
 The names of the components will be strings, and will consist of English alphabet 
letters and digits.
 The names of the Hardware Components will always be unique.
 The names of the Software Components will be unique for every Hardware 
Component.
 The memory and capacity of each component will be integer numbers in range [0, 231 - 
1].
 The type of a Hardware Component can be “Power”or “Heavy”.
 The type of a Software Component can be “Express” or “Light”.
 There will be NO invalid input commands.
Examples
Hint: Test2 software is not registered, becuase HDD has not enough capacity to run.
Input
Output
RegisterPowerHardware(HDD, 200, 200)
RegisterHeavyHardware(SSD, 400, 400)
Analyze()
RegisterLightSoftware(HDD, Test, 0, 10)
RegisterExpressSoftware(HDD, Test2, 100, 100)
RegisterExpressSoftware(HDD, Test3, 50, 100)
RegisterLightSoftware(SSD, Windows, 20, 50)
RegisterExpressSoftware(SSD, Linux, 50, 100)
RegisterLightSoftware(SSD, Unix, 20, 50)
Analyze()
ReleaseSoftwareComponent(SSD, Linux)
Dump()
System Analysis
Hardware Components: 2
Software Components: 0
Total Operational Memory: 0 / 650
Total Capacity Taken: 0 / 850
System Analysis
Hardware Components: 2
Software Components: 5
Total Operational Memory: 455 / 650
Total Capacity Taken: 160 / 850
Hardware Component - HDD
Express Software Components - 1
Light Software Components - 1
Memory Usage: 205 / 350
Capacity Usage: 50 / 50
Type: Power
Software Components: Test, Test3
Hardware Component - SSD
Express Software Components - 0
Light Software Components - 2
Memory Usage: 50 / 300
Capacity Usage: 60 / 800
Type: Heav

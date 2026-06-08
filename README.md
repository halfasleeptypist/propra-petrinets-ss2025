# propra-petrinets-ss2025
This is a little GUI program I made during my Java programming lab course at the FernUniversität in Hagen in the summer semester of 2025.

By loading in PNML files, you can analyze the structure of petri nets as well as its behaviour as you move tokens through the petri net.

The program can also algorithmically analyze a petri net on its boundedness by constructing its reachability graph.

More information about petri nets can be found at https://en.wikipedia.org/wiki/Petri_net.

<img width="984" height="692" alt="petri" src="https://github.com/user-attachments/assets/f0733ca3-ce98-41cb-8e92-4af2346b41ce" />

# Installation
The runnable .jar file was compiled in an execution environment JRE JavaSE-21 (class file version 65.0). 

Your system needs to have a version of **Java SE Development Kit 21 or newer** installed, in order to run the file. 

The version can be downloaded at https://www.oracle.com/java/technologies/downloads/.

# How to use
In the menu bar, go to **Menu → Open File…** to load up a PNML file and display a petri net.

There are four main panels of the GUI: the **petri net panel** (middle left), the **reachability graph panel** (middle right), the **info box** (bottom), and the **tools panel** (left). 

Below the info box is also a **status bar** that displays the file name of the current petri net and indicates if the petri net has been modified by the user.

In the **petri net panel**, any squares (transitions) that are green can be clicked on. This will move the tokens around the petri net and change which of the squares are green and clickable.

The **reachability graph panel** shows a single node when you load in a PNML file. With every click of a green transition, more nodes are added to the graph to represent the states the tokens inside the petri net. Click on a node to switch between these states. The starting node is gold and bigger than any nodes created after that. A node has a dashed border if not all green squares in the petri net have been clicked on. Otherwise it will turn gray and have a full border.

The **info box** displays status messages whenever you have made an action in the program.

**The tool panel** on the right gives various functions you can use on the petri net and reachability graph.
- With **Previous petri net** and **Next petri net** you can swap in other PNML files from the directory the current petri net is in.
- **Erase reachability graph** resets the reachability graph to its starting node and resets the state of the petri net to the one defined in the PNML file.
- Click on a circle in the petri net to select it and **Add a token** or **Remove a token**. This also resets the reachability graph to its starting node.
- **Reset to initial marking** resets the petri net to its starting state but doesn’t erase the reachability graph.
- **Analyse for boundedness** constructs the full reachability graph if the petri net is bounded. Otherwise, it will construct the reachability graph until it realizes the petri net is unbounded. Then it will highlight two nodes and the path between them in red to indicate which states of the petri net trip the unboundedness condition.
- **Undo marking** and **redo marking** undo or redo any state changes to the petri net.
- **Clear text area** clears the info box.

The menu bar contains three tabs: **Menu**, **Settings**, and **Help**.
- **Menu** contains the option to open a PNML file, reload the current file to reset everything to its initial state, and to exit the program.
- When you click on **Menu → Analyse multiple files for boundedness**, you select one or more PNML files for the program to analyze each of their petri nets for boundedness. It will then display a table, indicating which petri nets are bounded, how many vertices and edges their respective reachability graph contains if bounded, and otherwise which vertices trip the unboundedness condition and how long the path between them is. It will not change nor erase the petri net and the reachability graph.
- When **Settings → Automatic unboundedness detection** is turned on, the program will automatically detect the petri net’s unboundedness as you build up the reachability graph.
- **Settings → Enable tree layout** arranges the nodes of the reachability graph top-down in a breadth-first-search-style tree graph.
- **Help → Info** shows the file path of the working directory, the java version, and the file path of the used java environment.

# Known bugs
This program has not been worked on since the end of the programming course in July 2025. Most of the functions work but there are some bugs that have made their way into the program. Known bugs are listed below, but there are probably more hidden somewhere in the program.
- If you add a token into the petri net, click on some transitions, undo markings, and click on different transitions, it could happen that the reachability graph starts modifying its own labels, making the correspondence between it and the petri net invalid.

# Automata Diagram Type Recognition Challenge 

# Overview
This challenge asks participants to determine which family of finite automaton is shown in a diagram image: dfa, nfa, or epsilon_nfa. 
The dataset consists of rendered automata diagrams generated from a controlled pipeline that constructs machines and exports them as PNG images.

This task is a computer vision classification problem. The input to the model is an image containing a state machine diagram, 
and the goal is to classify the automaton family represented in that image. However, the visual signal in this dataset 
is not based on ordinary photographic features such as texture, color, or object appearance. Instead, the relevant 
information is contained in the diagram structure of the automaton.

Each diagram encodes a finite state machine using standard conventions:

* states are represented as nodes
* accepting states appear as double circles
* directed edges represent transitions
* edge labels correspond to input symbols
* epsilon transitions may appear in some machines

The classification therefore depends on how these structural elements interact. For example:

a deterministic finite automaton (dfa) has at most one outgoing transition per symbol from each state
a nondeterministic finite automaton (nfa) may allow multiple transitions on the same symbol
an epsilon_nfa may additionally contain transitions labeled with the epsilon symbol
Because of this, solving the task requires recognizing the structural properties of the diagram, 
not simply detecting visual patterns. A successful system must interpret the graphical elements in
the image and infer the type of machine being represented.

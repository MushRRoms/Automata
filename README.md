-Class Automaton and program

Stores all info about the chosen Automaton. When initiated reads the file line by line and stores all infos as lists of strings. Also creates a list of every state as strings. All operation to be performed on an Automaton are in the class as methods for an easy access to all the necessary info. The program is placed in two loops, the first one to change Automaton without having to restart the program each time, the second to perform as many operations as we'd like on a choosen automaton. To create the execution traces that were asked, the output is directed to both the console and a file which changes with the automaton

-Standardization

First check whether standard or not: is_standard verifies whether one of the rule of standard automaton is broken and stores it as an info in the automaton object. First is checked using the length of the initial state list to see whether there's more than one. Second is checked by using the initial state list and looking for a transition to any of in the transition list.if the automaton is not standard, we ask whether the user wants to standardize it. If yes: We add a state I then build all its transitions by checking and copying the transitions of initial states and finish by setting I as the only initial state

-Determinization

the process of converting a non-deterministic automaton (usually a Non-Deterministic Finite Automaton, or NFA) into an equivalent deterministic automaton (usually a Deterministic Finite Automaton, or DFA). 

-Completion

Can only be lauched from a deterministic automaton and only after the automaton has been identified as not complete. is_complete creates a Matrix that counts the number of transition for a given symbel per state, similar to is_deterministic, and check whether 0 is in that matrix highlighting the lack of completeness. If the automaton fills those two conditions, we build the transition table of the automaton as a matrix and check for empty slot in each row. if an empty spot is detected, it gets filled with the newly created state P and a new transition is added. The transition of P are also added.

-Word Recognition and Complementary language:

Word Recognition:
The user is prompted and enters a word they want to check. The word is then check by using every letter as a transition symbol. To simplify this part, we use a complete deterministic automaton since they read the same language as the originals. If the word is not finished but we can't advance anymore in the automaton, the word is not recognized. If we managed to reach the end of the word but we ended up at a non-termiinal state, the word is not recognized. If the word is finished and the final state is terminal, the word is recognized.

Complementary language:
We create a new automaton object and copy all the info stored in the studied automaton. From a complete deterministic version of it, we create the complement by checking for and storing in a list  all the states that aren't in the terminal state list with a comparison to the list of all states. the resulting list replaces the original terminal state list, making non terminal, terminal and vice versa.
From there, since the complement is an Automaton object we can call the function for word recognition to read the complementary language.

# Class Scheduling

Solution to the Clever class scheduling coding challenge. 

## Implementation

My solution, written in **Python**, makes use of **topological sorting** with an adjacency list to schedule classes. Classes without prerequisites are slotted to be taken first, with classes that have one already-taken prerequisite following and so on, until every class can be accommodated. Eligible classes at every stage are kept track of using a depth 'degree' which indicates how many of each class' prerequisites are already in the schedule. In the event of every class not making it into the schedule, an error is raised.

 The was the most intuitive way of thinking about the solution for me was as a graph with vertices (classes) at different 'heights' (number of prerequisites) that can be accessed once vertices at lower 'heights' close to them have been reached. 

## Instructions 
The program can be run from within the scheduler directory by typing 
``
./scheduler <input file name>
`` which invokes the scheduler executable. Building the executable is not required. The use of Python version 3.0 and higher is recommended.
## Files 

**<span>scheduler.py</span>**: Driver file for the scheduler executable

**sched_util.py**: File that contains helper methods as well as my implementation of a 		scheduling algorithm. 

**test_scheduler.py**: Unit tests for the sched_util helper methods and the scheduling method using custom edge-case inputs. 
Use the command ``python ./test_scheduler.py`` from within the scheduler repo to run basic unit tests.

**valid_examples**: Folder containing valid JSON files that can be used to test the program. 

**invalid_examples**: Folder containing JSON files designed in ways to prompt various errors to test the program's error handling capabilities. 

## Time Complexity
The algorithm runs in O(V+E) time where V is the number of vertices or classes ad E is the total number of prerequisite relationships between classes. Each class is looked at exactly once by successive popping from a queue and for each class, the program looks at its neighboring classes which equates to the total number of edges. 

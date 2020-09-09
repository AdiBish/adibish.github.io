### PAGE UNDER CONSTRUCTION 
## Neat Coding Practices to minimize errors

I will be using analysis of experimental data that I do routinely as an example. 

Where to start:
Assuming that you have collected some interesting data and want to see if there are particular trends in your data. 
1. Identify the type of raw data that you need to work upon and identify its structure: For neural data, do you need spike data, local field potentials, calcium imaging. Are there any behavioural data to correlate: video frames for position, TTL timestamps for various events etc. 
2. Prepare the raw data: check if any preprocessing would be required e.g. spike data needs to be sorted into various session types or the gains of local field potentials need to be matched across channels and animals. 
All these are crucial in order to ensure that the data set you are setting with in the first place is correct. 
3. Pen and paper for psuedoalgorithm: sketch out the outline of the calculations that would be needed and the basic algorithm before setting out on writing the final code.

Neat writing to minimize errors and increase readability:

4. Modular approach, Create Functions: Most of the times, you would have to do very different calculations within the same algorithm. Also, many calculations might have to be repeated at various steps. In such cases, its better to put these calculations in separate functions to make your scripts more legible and avoid errors due to copy paste in the respective cases. Have a separate file for the main code and another file for all the functions. Its better to have all functions in one file labelled utilities as it makes tracking versions also easier and reduces the mess of organizing files. 

5. Writing Utility functions in pyhton ( include link here) and in Matlab (include link here)

a) do  not have redundant or confusing function or variable names

b) better to write them in the order in which they would be called in the main code so as to maintain the readability

c) include sanity checks for all the input and output parameters for every function. Include checks to ensure that there are no negative or NAN values where there shouldnt be.
Its crucial to have these checks pop errors and stop excution as compared to warnings as you cannot afford them to go unnoticed and accumulate. 

d) for the variables that are being called in multiple functions, it would be better to set them as global variables else a sanity check for them in each function they are called in becomes utmost necessary. 

e) avoid same local variable names across different functions

f) comment. specially at critical places

g) VERY IMPORTANT: before going for a finalizing your functions, check each function individually on some simulated or surrogate data to validate that the calculations follow expectations. 

h) once done with initial tests, set breakpoints at critical points as well so that debugging along with the main code becomes easy ( see point 6f).

6. Writing the main code
Here the basic flow would be to load preprocessed data (or if your code is not very lengthy, you can load raw data and run preprocessing as mentioned in #2 through separate functions within the first few lines itself), plot figures and save all necessary intermediate and final variables.
a) Do not have irrelevant data loaded into workspaces. Also, keep clearing variables that are obsolete or are going to change their value in the rest of the code. 
b) avoid hard coded values
c) do not have redudant variable names
d) maintain readability by keeping different businesses separate. eg. I would keep lines that call rate map generation functions spaced out from parts that deal with theta phase precession. 
e) comment at critical places
f) MOST IMPORTANT: before going into a full blown run, set breakpoints at all critical places in order debug. To set breakpoints in python (link here) and in matlab (link here). 

7. how to debug.
once all break points are set, run your script one an example or simulated data set. Have manually calculated results as well and as you debug so that you can validate at every step. 

I am hoping this will help all potential coders. Any feedback or inputs are welcome. 

Happy Coding :)




Reference: 
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4269119/


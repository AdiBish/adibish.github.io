
*How to start:*

I will be using analysis of experimental data that I do routinely as an example. Assuming that you have collected some interesting data and want to see if there are particular trends in your data. 
1. Identify the type of raw data that you need to work upon and identify its structure: For neural data, do you need spike data, local field potentials, calcium imaging. Are there any behavioural data to correlate: video frames for position, TTL timestamps for various events etc. 
2. Prepare the raw data: check if any preprocessing would be required e.g. spike data needs to be sorted into various session types or the gains of local field potentials need to be matched across channels and animals. 
All these are crucial in order to ensure that the data set you are setting with in the first place is correct. 
3. Pen and paper for psuedoalgorithm: sketch out the outline of the calculations that would be needed and the basic algorithm before setting out on writing the final code.

*Neat writing to minimize errors and increase readability:*

4. Modular approach, Create Functions: Most of the times, you would have to do very different calculations within the same algorithm. Also, many calculations might have to be repeated at various steps. In such cases, its better to put these calculations in separate functions to make your scripts more legible and avoid errors due to copy paste in the respective cases. Have a separate file for the main code and another file for all the functions. Its better to have all functions in one file labelled utilities as it makes tracking versions also easier and reduces the mess of organizing files. 

5. Writing all utility functions in a single function file.  

    1. Do  not have redundant or confusing function or variable names

    2. Better to write them in the order in which they would be called in the main code so as to maintain the readability
    
    3. Include sanity checks for all the input and output parameters for every function. Include checks to ensure that there are no negative or NAN values where there shouldnt be.
  Its crucial to have these checks pop errors and stop excution as compared to warnings as you cannot afford them to go unnoticed and accumulate. 

    4. For the variables that are being called in multiple functions, it would be better to set them as global variables else a sanity check for them in each function they are   called in becomes utmost necessary. 

    5. Avoid same local variable names across different functions

    6. Comment. specially at critical places

    7. VERY IMPORTANT: Before going for a finalizing your functions, check each function individually on some simulated or surrogate data to validate that the calculations follow expectations. 

    8. Once done with initial tests, set breakpoints at critical points as well so that debugging along with the main code becomes easy ( see point 6(vi)).
    
How to have all important functions in the same file in python:      
    
        ```python
        def firstfunction (a,b):
            #c = do sometihng with a and b
            return c
        def secondfunction(c,d):
            #e = do something with c and d
            return e

        # to call: 

        import utils as ut # the name of the file will be utils.py in this case
        c = ut.firstfunction(a,b)
        ```

In matlab: 

    ```matlab
    function f = utils % the name of the file will be utils.m in this case
        f.firstfunction = @firstfunction;
        f.secondfunction = @secondfunction;
    end

    function c = firstfunction(a,b)
        %do something 
    end

    function e = secondfunction(c,d)
        %do something
    end

    % To call:
    ut = utils;
    c = ut.firstfunction(a,b);  
    ```
  
6. Writing the main code
Here the basic flow would be to load preprocessed data (or if your code is not very lengthy, you can load raw data and run preprocessing as mentioned in #2 through separate functions within the first few lines itself), plot figures and save all necessary intermediate and final variables.

    1. Do not have irrelevant data loaded into workspaces. Also, keep clearing variables that are obsolete or are going to change their value in the rest of the code. 

    2. Avoid hard coded values

    3. Do not have redudant variable names

    4. Maintain readability by keeping different businesses separate. eg. I would keep lines that call rate map generation functions spaced out from parts that deal with theta phase precession. 

    5. Comment at critical places

    6. MOST IMPORTANT: before going into a full blown run, set breakpoints at all critical places in order debug. You can set breakpoints in [Python](https://poweruser.blog/setting-a-breakpoint-in-python-438e23fe6b28) and in [MATLAB](https://in.mathworks.com/help/matlab/matlab_prog/set-breakpoints.html) though I have only tested it in Matlab. 

7. How to debug.
Once all break points are set, run your script one an example or simulated data set. Have manually calculated results as well and as you debug so that you can validate at every step. 

Hoping this will help all potential coders. Any feedback, questions or inputs are welcome. 

Happy Coding :)




Reference: 
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4269119/


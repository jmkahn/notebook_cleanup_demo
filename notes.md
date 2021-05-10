# A workflow for editing a data analysis pipeline notebook  

You've jotted down some exploratory code and figured out how to do the 
analyses you're interested in. Now it's time to go back and clean up the
notebook! This is important so that: 

- other people can understand what you did and why 
- you can reuse your code later without too much difficulty 
- you can extend your code to other data sets 
- prevent incorrect results due to bugs 

Here is a sample set of steps that you can use to clean up a notebook. 
Feel free to edit it based on your needs. 

1. Write comments on what you did and why 
    - comment the "big picture" of each section of code 
    - add code-level comments explaining rationale for any choices you made in
      how to analyze 
    - the comments don't need to be polished (bullets/notes is fine). The goal
      is to lose any knowledge
    - __HINT__: if you're not sure what's worth commenting, put your code down for a
      day and then come back to it. This is long enough that you'll have to
      're-orient' yourself, but short enough that you (hopefully) still remember
      what you did. Add comments to anything that isn't obvious as you're
      reading your code again 

1. Delete any code that you don't need anymore 
    - this could be analyses or visualizations you tried but didn't go anywhere,
      etc. 

2. Put repeated/reusable code into functions 
    - A rule of thumb: if code is repeated 3+ times, make into function (or make  code that should be
    executed a single block and could potentially be reused) - some judgement
    call 

    - when you're making code into functions, this is a good time to see if you
    can rewrite any code in a cleaner way 
    - move the functions to the top of the relevant section 


3. Split each step of pipeline into its own, atomic notebook 
    - move all import statements to the first block of the notebook 

5. Write more  Someone
looking at this for the first time should be able to follow what you do without
any specific background

6. Making code easy to run on variations on data: 
    - save results rather than printing them 
        - allows you to compare results between variations 
    - add a `data_id` at the top of the notebook 
        - use the `data_id` as part of the file name for all saved functions 
    - can check that the functions have gone well if it's easy to run on any
    set and you get the results without changing lots of stuff 

Frequently run notebook all the way through/reset kernel to make sure there
aren't any hidden already assigned things messing you up 


### How to reformat existing code into a function: 

1. Identify what the function does 
    - use this to write the **function definition and docstring**
    - _Hint_: what is the general task that is being repeated?
2. Identify the the values that change from one usage of the function to the
   next
    - these are the values that you want to pass in as **parameters** 
3. Identify what values you need for the next steps of the analysis 
    - these values should be what the function **returns**
4. Put existing functional code inside the funciton definition 
5. Generalize hard-coded values  
    - for example: instead of just writing `4` if that's the number of
      columns in this particular dataset, extract that value from the dataset
      with `len(df.columns))`
    - things like "figure size" can stay hardcoded since they are unlikely to
    cause confusing errors in the future 
    - _Hint_: you want to get rid of any 'magic values' that could potentially confuse a
    future user who's not familiar with the code


Problems with first notebook 
- all code cells not run before publishing (things could have changed since you
last ran and you don't remember - always run one time)
- lots of copy pasted, repeat code with slight differences (opportunity to
introduce bugs/forget to change the right thing)
- a sequence broken across multiple cells -> opportunity to accidententally
shuffle them/run them out of order. things that should always be run together,
put them in one block 
- hardcoded values (eg number of columns in dataset represented as "4") (unclear
what these values refer to, confuses next user, harder to generalize )



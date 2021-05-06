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


To write a function: 
- generalize all the hardcoded values that may change in the future (eg instead of just writing "4" since
that's the number of columns in this particular dataset, extract that value from
the dataset with len(df.columns))
    - things like "figure size" can stay hardcoded since they are unlikely to
    cause confusing errors in the future 
    - you want to get rid of 'magic values' that could potentially confuse a
    future user (or you in a month) who's not familiar with the code
- put the functional code inside a function definition 
- replace all things that are specific in the code (eg data frame ) with
inputs/add parameters to function 


Editing 
0. Write down what you did and what the point of it was in a basic way 

1. delete redundant analyses that you don't need anymore 

2. Put code into functions 

    - if repeated 3+ times, make into function (or make  code that should be
    executed a single block and could potentially be reused) - some judgement
    call 
    - identify all the values that should get passed in (hint: these are often
    the things you changed in the copypasted code)
    - make these into functions 
    - move the functions to the top of the relevant section 
    - what values from this code do you use in next steps? this is what the
    function should return 

    - when you're making code into functions, this is a good time to see if you
    can rewrite any code in a cleaner way 


3. Split each step of pipeline into its own, atomic notebook 
- move all the import statements to the first block 
4. Write a description of each step that you do 
5. Present methods and results as if they're going into a report. Someone
looking at this for the first time should be able to follow what you do without
any specific background

6. Making code good for subsetted data: 
    - save results rather than printing them 
    - data_id at the top of the notebook 
    - use that data id in saving 
    - can check that the functions have gone well if it's easy to ru non any
    set and you get the results without changing lots of stuff 


Frequently run notebook all the way through/reset kernel to make sure there
aren't any hidden already assigned things messing you up 
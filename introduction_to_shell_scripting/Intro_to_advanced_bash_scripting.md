# Conditionals
if [ condition ]
then
    statement_block_1
else
    statement_block_2
fi

# Check if the Number of Commands-line arguments read by some Bash script $# is equal to 2
if [[ $# == 2 ]]
then
    echo "number of arguments is equal to 2"
else
    echo "number of arguments is not equal to 2"
fi

# Using the "and" Operator && the "or" operator || 
if [ condition1 ] && [ condition2 ]
then
    echo "conditons 1 and 2 are both true"
else    
    echo "one or both conditions are false"
fi
-------------------------------------------
if [ condition ] || [ condition ]
then    
    echo "conditions 1 or 2 are true"
else
    echo "both conditions are false"
fi

## ADVANCED BASH SCRIPTING GUIDE
>> https://tldp.org/LDP/abs/html/comparison-ops.html

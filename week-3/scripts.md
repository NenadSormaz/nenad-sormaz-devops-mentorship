# Chapter 13  
### test1  
> [centos@ip-172-31-34-106 week--3]$ cat test1.sh   
> #!/bin/bash  
> #basic for command  
> for test in Alabama Alaska Arizona Arkansas California Colorado  
> do  
> echo The next state is $test  
> done  

### test1b
> #!/bin/bash  
> #testing the for variable after the looping  
> for test in Alabama Alaska Arizona Arkansas California Colorado  
> do  
> echo "The next state is $test"  
> done  
> echo "The last state we visited was $test"  
> test=Connecticut  
> echo "Wait, now we're visiting $test"  

### badtest1
> #!/bin/bash/  
> #another example of how not to use the for command  
> for test in I don't know if this'll work  
> do  
> echo "word:$test"  
> done  

### test2
> #!/bin/bash/  
> #another example of how not to use for command  
> for test in I don\'t know if "this'll" work  
> do  
> echo "word:$test"  
> done  

### badtest2
> #!/bin/bash/  
> #another example of how not to use the for command  
> for test in Nevada New Hampshire New Mexico New York North Carolina  
> do  
> echo "Now going to $test"  
> done  

### test3
> #!/bin/bash/  
> #an example of how to properly define values  
> for test in Nevada "New Hampshire" "New Mexico" "New York"  
> do  
> echo "Now going to $test"  
> done  







# Chapter 14  

# Chapter 15  

# Chapter 16  
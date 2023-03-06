# Chapter 13  
### test1  
> [centos@ip-172-31-34-106 week--3]$ cat test1.sh   
> #!/bin/bash  
> #basic for command  
> for test in Alabama Alaska Arizona Arkansas California Colorado  
> do  
> echo The next state is $test  
> done  
!(https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test1.png?raw=true)  

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
!(https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test1b.png?raw=true)  

### badtest1
> #!/bin/bash/  
> #another example of how not to use the for command  
> for test in I don't know if this'll work  
> do  
> echo "word:$test"  
> done  
!(https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/badtest1.png?raw=true)  

### test2
> #!/bin/bash/  
> #another example of how not to use for command  
> for test in I don\'t know if "this'll" work  
> do  
> echo "word:$test"  
> done  
!(https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test2.png?raw=true)  

### badtest2
> #!/bin/bash/  
> #another example of how not to use the for command  
> for test in Nevada New Hampshire New Mexico New York North Carolina  
> do  
> echo "Now going to $test"  
> done  
!(https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/badtest2.png?raw=true)  

### test3
> #!/bin/bash/  
> #an example of how to properly define values  
> for test in Nevada "New Hampshire" "New Mexico" "New York"  
> do  
> echo "Now going to $test"  
> done  
!(https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test3.png?raw=true)  

### test4
> #!/bin/bash/  
> #using a variable to hold the list  
> list="Alabama Alaska Arizona Arkansas Colorado"  
> list=$list" Connecticut"  
> for state in $list  
> do  
> echo "Have you ever visited $state?"  
> done 
!(https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test4.png?raw=true)  

### 







# Chapter 14  

# Chapter 15  

# Chapter 16  
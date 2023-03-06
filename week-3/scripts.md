# Chapter 13  
### test1  
> [centos@ip-172-31-34-106 week--3]$ cat test1.sh   
> #!/bin/bash  
> #basic for command  
> for test in Alabama Alaska Arizona Arkansas California Colorado  
> do  
> echo The next state is $test  
> done  
![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test1.png?raw=true)  

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
![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test1b.png?raw=true)  

### badtest1
> #!/bin/bash/  
> #another example of how not to use the for command  
> for test in I don't know if this'll work  
> do  
> echo "word:$test"  
> done  
![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/badtest1.png?raw=true)  

### test2
> #!/bin/bash/  
> #another example of how not to use for command  
> for test in I don\'t know if "this'll" work  
> do  
> echo "word:$test"  
> done  
![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test2.png?raw=true)  

### badtest2
> #!/bin/bash/  
> #another example of how not to use the for command  
> for test in Nevada New Hampshire New Mexico New York North Carolina  
> do  
> echo "Now going to $test"  
> done  
![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/badtest2.png?raw=true)  

### test3
> #!/bin/bash/  
> #an example of how to properly define values  
> for test in Nevada "New Hampshire" "New Mexico" "New York"  
> do  
> echo "Now going to $test"  
> done  
![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test3.png?raw=true)  

### test4
> #!/bin/bash/  
> #using a variable to hold the list  
> list="Alabama Alaska Arizona Arkansas Colorado"  
> list=$list" Connecticut"  
> for state in $list  
> do  
> echo "Have you ever visited $state?"  
> done  
![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test4.png?raw=true)  

### test5
> #prethodno je potrebno kreirati states fajl  
> #!/bin/bash/  
> #reading values from a file  
> file="states"  
> for state in $(cat $file)  
> do  
> echo "Visit beautiful $state"  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test5.png?raw=true)  

### test5b
> #!/bin/bash/  
> #reading values from a file  
> file="states"  
> IFS=$'\n'  
> for state in $(cat $file)  
> do  
> echo "Visit beautiful $state"  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test5b.png?raw=true)  

### test6
> #!/bin/bash/  
> #iterate through all the files in a directory  
> for file in /home/centos/*  
> do  
> if [ -d "$file" ]  
> then  
> echo "$file is a directory"  
> elif [ -f "$file" ]  
> then  
> echo "$file is a file"  
> fi  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test6.png?raw=true)  

### test7  
> #!/bin/bash/  
> #iterating through multiple directiories  
> for file in /home/centos/* /home/centos/week--3/*  
> do  
> if [ -d "$file" ]  
> then  
> echo "$file is a directory"  
> elif [ -f "$file" ]  
> then  
> echo "$file is a file"  
> else  
> echo "$file doesn't exist"  
> fi  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test7.png?raw=true)  

### 










# Chapter 14  

# Chapter 15  

# Chapter 16  
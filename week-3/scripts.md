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

### test8  
> #!/bin/bash/  
> #testing the C-style for loop  
> for ((i=1; i<=10; i++))  
> do  
> echo "The next number is $i"  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test8.png?raw=true)  

### test9  
> #!/bin/bash/  
> #multiple variables  
> for ((a=1, b=10; a <=10; a++, b--))  
> do  
> echo "$a-$b"  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test9.png?raw=true)  

### test10  
> #!/bin/bash/  
> #while command test  
> var1=10  
> while [ $var1 -gt 0 ]  
> do  
> echo $var1  
> var1=$[ $var1 - 1 ]  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test10.png?raw=true)  

### test11
> #!/bin/bash/  
> #testing a multicommand while loop  
> var1=10  
> while echo $var1  
> [ $var1 -ge 0 ]  
> do  
> echo "This is inside the loop"  
> var1=$[ $var1 - 1 ]  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test11.png?raw=true)  

### test12
> #!/bin/bash/  
> #using the until command  
> var1=100  
> until [ $var1 -eq 0 ]  
> do  
> echo $var1  
> var1=$[ $var1 - 25 ]  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test12.png?raw=true)  

### test13
> #!/bin/bash/  
> #using the until command  
> var1=100  
> until echo $var1  
> [ $var1 -eq 0 ]  
> do  
> echo Inside the loop: $var1  
> var1=$[ $var1 - 25 ]  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test13.png?raw=true)  

### test14
> #!/bin/bash/  
> #nesting for loops  
> for (( a=1; a<=3; a++ ))  
> do  
> echo "Starting loop $a:"  
> for (( b=1; b<=3; b++ ))  
> do  
> echo "	Inside loop: $b"  
> done  
> done  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test14.png?raw=true)  

### test15
> #!/bin/bash/  
> #placing a for loop inside a while loop  
> var1=5  
> while [ $var1 -ge 0 ]  
> do  
> echo "Outer loop: $var1"  
> for (( var2 = 1; $var2 < 3; var2++ ))  
> do  
> var3=$[ $var1 * $var2 ]  
> echo "	Inner loop: $var1 * $var2 = $var3"  
> done  
> var1=$[ $var1 - 1 ]  
> done

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/week-3-branch/week-3/screenshots/test15.png?raw=true)  

### test16
















# Chapter 14  

# Chapter 15  

# Chapter 16  
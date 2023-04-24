# TASK-8: Implement SSL Let's Encrypt, migrate to AWS ACM  
   
### - Od AMI image `ami-asg-ec2-web-server` napravljena je nova EC2 instancu `ec2-nenad-sormaz-task-8`  

### - Kreiran je DNS record `nenad--sormaz.awsbosnia.com` za Hosted Zone awsbosnia.com koji pokazuje na EC2 instancu `ec2-nenad-sormaz-task-8`. 

##### Koristene komande:
- `aws configure --profile aws-bosnia`  
Nakon unesene komande u konzolu sam unio sljedece podatke:  
    AWS Access Key ID  
    AWS Secret Access Key  
    Default region name  
    Default output format  
- `export AWS_PROFILE=aws-bosnia`  
- `aws configure list`  
- `aws route53 change-resource-record-sets --hosted-zone-id Z3LHP8UIUC8CDK --change-batch '{"Changes":[{"Action":"CREATE","ResourceRecordSet":{"Name":"nenad--sormaz.awsbosnia.com.","Type":"A","TTL":60,"ResourceRecords":[{"Value":"44.204.65.94"}]}}]}'`  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/task-8/week-9/screenshots/DNS.png?raw=true)   

### -  Ispisan Name i Value DNS-a uz pomoc komande aws route53 list-hosted-zones i alata jq gdje cete prikazati samo Name i Value za DNS record koji ste vi kreirali odnosno za vase domensko ime.  

#### Koristena komanda:  
- `aws route53 list-resource-record-sets --hosted-zone-id Z3LHP8UIUC8CDK | jq '.ResourceRecordSets[] | select(.Name == "nenad--sormaz.awsbosnia.com.") | {Name, Value}'`  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/task-8/week-9/screenshots/DNS2.png?raw=true)  


### - 

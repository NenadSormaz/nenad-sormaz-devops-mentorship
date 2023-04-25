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

### - Ispisan Name i Value DNS-a uz pomoc komande aws route53 list-hosted-zones i alata jq gdje cete prikazati samo Name i Value za DNS record koji ste vi kreirali odnosno za vase domensko ime.  

#### Koristena komanda:  
- `aws route53 list-resource-record-sets --hosted-zone-id Z3LHP8UIUC8CDK | jq '.ResourceRecordSets[] | select(.Name == "nenad--sormaz.awsbosnia.com.") | {Name, Value}'`  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/task-8/week-9/screenshots/DNS2.png?raw=true)  


### - Na instanci `ec2-nenad-sormaz-task-8` kreiran je Let's Encrypt SSL certifikat za moj domen. Omoguceno je da se nodejs aplikaciji moze pristupiti preko linka: `https://nenad--sormaz.awsbosnia.com`.

#### Pracene instrukcije sa `https://github.com/allops-solutions/devops-aws-mentorship-program/blob/main/devops-learning-path/ssl.md` i sa Office Hours video snimka.  

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/task-8/week-9/screenshots/certificatge.png?raw=true)  

### - Omogucen autorenewal SSL certifikata uz pomoc skripte:

#### `SLEEPTIME=$(awk 'BEGIN{srand(); print int(rand()*(3600+1))}'); echo "0 0,12 * * * root sleep $SLEEPTIME && certbot renew -q" | sudo tee -a /etc/crontab > /dev/null`

### - Koristeci openssl komande prikazao sam koji SSL certitikat koristim kao i datum njegovog isteka:  

#### Koristene komande:  

- `openssl s_client -showcerts -connect nenad--sormaz.awsbosnia.com:443`  
- `openssl s_client -showcerts -connect nenad--sormaz.awsbosnia.com:443 2>/dev/null | openssl x509 -noout -text`  

### - Importovan Lets Encrypt SSL certifikat unutar AWS Certified Managera

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/task-8/week-9/screenshots/importedCert.png?raw=true)

### - Kreiran novi SSL certifikat unutar AWS Certified Managera

- Komanda koju sam koristio:  

`aws route53 change-resource-record-sets --hosted-zone-id Z3LHP8UIUC8CDK --change-batch '{"Changes":[{"Action":"CREATE","ResourceRecordSet":{"Name":"_7ea6b55087340d053b9eb8a916fabe99.nenad--sormaz.awsbosnia.com.","Type":"CNAME","TTL":60,"ResourceRecords":[{"Value":"_3717279c8970f3fb6cd1c2b1353e50ab.tctzzymbbs.acm-validations.aws."}]}}]}' --profile aws-bosnia`

![](https://github.com/NenadSormaz/nenad-sormaz-devops-mentorship/blob/task-8/week-9/screenshots/certAWS.png?raw=true)  

### - Kreiran AMI image pod nazivom `ec2-nenad-sormaz-task-8`; terminirani resurse koje sam koristio za izradu taska.
# wafdashboard
WAF Dashboard Template baed on ElasticSearch Kibana.  This WAF Dashboard is created by Jason Xie from AWS Enterprise Support team.


## Abstract
IT System built on AWS usually enable WAF, Shield and other Security Service to protect DDoS attack.  However, many companies found it is hard to know the defense effect and performance after enabling the AWS WAF Service.  This is because they don't have an integrated log analysis system and a good visualization tool to analyze the attack their system is suffering.  Besides, it is hard for companies to make good use of those valuable log data to do further analysis to improve their service.  They can only follow the traditional IT maintenance model to handle the security event afterward, instead of doing protection in advance.  In obvious, this kind of handling methods is hard to be accepted by most of companies.

AWS Enterprise Support team bases on practice working experience with Enterprise customers to build an AWS WAF Log Analysis system based on Elasticsearch to tackle above problem.  With the help of this solution, AWS users can build an insightful WAF log analysis dashboard by few clicks.  Besides, with the help of this dashboard, risk and security administrators can easily analyze the network traffic from multiple perspectives that they can visualize the normal and attack traffic, analyze the attack patterns and trend, attack source IP and countries, vulnerable URL path, and so on.

Sample English Dashboard:
![image](https://github.com/xzp1990/wafdashboard/blob/master/English_blog_picture.png?raw=true)

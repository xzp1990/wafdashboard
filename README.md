# AWS WAF Dashboard
It's very easy to use Elasticsearch Kibana to build a WAF log dashboard, depending on customers' requirements.  In order to help companies to get started quickly and adopt the industry best practice easily, you can follow below the blog steps to adopt the WAF Log Visualize and Dashboard which is developed by Jason Xie from the AWS Enterprise Support team. 


## Abstract
IT Systems built on AWS usually enable WAF, Shield, and other Security services to protect against DDoS attacks.  However, many companies found it is hard to know the defense effect and performance after enabling the AWS WAF Service.  This is because they don't have an integrated log analysis system and a good visualization tool to analyze the attack their system is suffering.  Besides, it is hard for companies to make good use of those valuable log data to do further analysis to improve their service.  They can only follow the traditional IT maintenance model to handle the security event afterward, instead of doing protection in advance.  In obvious, this kind of handling methods is hard to be accepted by most companies.

AWS Enterprise Support team bases on practice working experience with Enterprise customers to build an AWS WAF Log Analysis system based on Elasticsearch to tackle the above problem.  With the help of this solution, AWS users can create an insightful WAF log analysis dashboard with few clicks.  Besides, with the help of this dashboard, risk and security administrators can easily analyze the network traffic from multiple perspectives that they can visualize the normal and attack traffic, analyze the attack patterns and trend, attack source IP and countries, vulnerable URL path, and so on.

## Sample WAF Dashboard Picture
![image](https://github.com/xzp1990/wafdashboard/blob/main/Kibana_dashboard_github.png)


## Index Template for ES 7.X
<pre><code>
PUT  _template/awswaf-logs
{
    "index_patterns": ["awswaf*"],
    "settings": {
    "number_of_shards": 5,
    "number_of_replicas": 1
    },
    "mappings": {
        "properties": {
          "httpRequest": {
            "properties": {
              "clientIp": {
                "type": "keyword",
                "fields": {
                  "keyword": {
                    "type": "ip"
                  }
                }
              }
            }
          },
          "timestamp": {
            "type": "date",
            "format": "epoch_millis"
          }
      }
  }
}
</code></pre>

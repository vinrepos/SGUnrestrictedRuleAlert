# SGUnrestrictedRuleAlert

*Use case:* To get notified of any unrestricted Security Group inbound rule (such as 0.0.0.0/0 or ::/0) through an email and a webhook.

*What does this deploy in the environment?*
1. Creates a Lambda Python function that sends email and webhook notifications upon getting triggered.
2. Creates a Metric filter on the AWS CloudTrail's CloudWatch Log Group.
3. Creates a CloudWatch Alarm that monitors the Metric filter every 5 minutes and triggers the SNS topic.
4. The SNS topic then triggers the attached Lambda function.
5. The IAM role used for Lambda has permissions only for SES, SNS, and CloudWatch Log Groups.

*Where to deploy:* In the AWS account that has the CloudWatch Log group for your organisation's main CloudTrail trail. Most likely it is going to be the management account.


*Example: When deploying the stack*

![image](https://github.com/vinrepos/SGUnrestrictedRuleAlert/assets/104124987/1b39c4fa-164f-4f1b-a42f-2571364a24a8)


*Expected Outcomes*

*Example: Email*

![image](https://github.com/vinrepos/SGUnrestrictedRuleAlert/assets/104124987/303a5418-d164-48b0-8545-bbf71c9fbdea)


*Example: Webhook*

![image](https://github.com/vinrepos/SGUnrestrictedRuleAlert/assets/104124987/db68645a-fd33-4570-9913-f6295347cf07)



Please create an issue for any sort of help with this.

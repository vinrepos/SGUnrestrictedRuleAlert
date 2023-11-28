# SGUnrestrictedRuleAlert

*Use case:* To get notified of any unrestricted Security Group inbound rule (such as 0.0.0.0/0 or ::/0) through an email and a webhook.

*What does this deploy in the environment?*
1. Creates a Lambda Python function that sends email and webhook notifications upon getting triggered.
2. Creates a Metric filter on the AWS CloudTrail's CloudWatch Log Group.
3. Creates a CloudWatch Alarm that monitors the Metric filter every 5 minutes and triggers the SNS topic.
4. The SNS topic then triggers the attached Lambda function.
5. The IAM role used for Lambda has permissions only for SES, SNS, and CloudWatch Log Groups.

*Example: When deploying the stack*

![image](https://github.com/vinrepos/SGUnrestrictedRuleAlert/assets/104124987/1b39c4fa-164f-4f1b-a42f-2571364a24a8)

*Example: Email*

![image](https://github.com/vinrepos/SGUnrestrictedRuleAlert/assets/104124987/9c7a3529-0fb8-4b12-8880-082b83d4f886)

*Example: Webhook*

![image](https://github.com/vinrepos/SGUnrestrictedRuleAlert/assets/104124987/e2bf1b80-57a8-4151-b020-043e51148f0f)


Please create an issue for any sort of help with this.

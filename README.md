# Creating-Billing-Budget-Alarms-On-AWS

# Intro
Your journey to becoming a Cloud Engineer most likely would involve experimenting with projects on major public cloud providers like Amazon Web Services (AWS). Fortunately, AWS provides Free Tier Usage for certain resources, however at times, it can be cumbersome to manually track all spending from deployed resources in your account. This may result in the incurring of unintended costs because of forgotten resources left running.

Today, I will show you how we can track your running spendings in your AWS account and be alerted via email once your cost reaches over a desired threshold amount. We will be using two effective services, AWS Budgets and Amazon CloudWatch, which will enable us to set up billing budgets and billing alarms.

# Background 

# AWS Budgets 
AWS Budgets is a feature in your AWS Account dashboard that is used to set custom billing budgets to track costs based on usage in your account. It can be configured to send alerts to your email using SNS notifications if the thresholds are exceeded so you can quickly respond.

# Amazom CloudWatch 
Amazon CloudWatch enables you to monitor applications, infrastructure, network and services and use alarms, logs and events data to take automated actions.

# Amazon SNS 
Amazon SNS makes it easy to set up, operate and send notifications from AWS. It provides message delivery from publishers to subscribers.

# Use Case
You are a Cloud SysOps Administrator working for Tatenda TECH. Your manager has informed you of a $10.00 AWS resource monthly spending limit she wants to place on your team’s account. She has tasked you to monitor the spending by tracking costs and has required that she be notified when it reaches a certain threshold before and when the spending limit is hit. You decided to use AWS Budgets, Amazon CloudWatch and Amazon SNS to accomplish this task.

# Enable billing access for IAM users and update billing preferences
Log into your AWS root account, click the root account name on the top right of the Management Console, then click “Account”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/a6f2c49a61e6e7bb220d23eede4d19df078cd396/Screenshot%202024-12-16%20165338.png)

Scroll down to “IAM User and Role Access to Billing Information”, then click “Edit” on the right side. Select “Activate IAM Access”, then click “Update”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/90f090e5cbcf5e3bf67b7cdf8e6d174c7f52e6a0/Screenshot%202024-12-16%20165526.png) 

Now let’s proceed to update our billing preferences.

Scroll up and click “Billing preferences” on the left pane.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/f2f1fefee7314e01871167ae94c6de3fa28b94a8/Screenshot%202024-12-16%20165730.png)

Now that we’ve enabled billing access for IAM users and updated billing preferences, we can proceed to actually creating the billing budgets and billing alarms.

# Create Billing Budgets with AWS Budgets

Sign into you IAM account, click the IAM account name on the top right of the Management Console, then click “Account”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/a6f2c49a61e6e7bb220d23eede4d19df078cd396/Screenshot%202024-12-16%20165338.png) 

Navigate to the left pane, click “Budgets”, then click “Create budget”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/bf41055d437eb9bc49e68463dcf46a9764026e40/Screenshot%202024-12-16%20170300.png) 

For “Budget setup”, we will use a simplified template and select “Monthly cost budget”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/7d8b2388d3d00e5abd589694fdec42055d62ea8d/Screenshot%202024-12-16%20170710.png)

Give the Budget a name, enter the budget amount, then type in the email address of the recipients to be notified when the threshold is exceeded.

As seen below, the recipients would be notified when spending has reached 85% and also when it reaches 100% or the forecasted spend is expected to reach 100%.

Proceed by clicking “Create budget”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/d5cdaa41825ee2068c240505a429610c9bfc5e10/Screenshot%202024-12-16%20170812.png)

Success!
You should now be able to see your newly created billing budget in the Budgets Overview.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/c51c6354f0c864a4b368004a8dfecfb48e0bfaab/Screenshot%202024-12-16%20170910.png)

# Create Billing Alarm with Amazon CloudWatch
Navigate to Amazon CloudWatch service in the Management Console, click “Billing” on the left pane, then click “Create alarm”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/fd2299c42341ec17c5296649ee98cc1816bb7a5e/Screenshot%202024-12-16%20171102.png)

Click “Select metric”, then click “Billing”. Click “Total Estimated Charge”, select “USD”, then click “Select metric”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/acb95ce741ec09823a794fbdc2a8dddf66e96bc6/Screenshot%202024-12-16%20171449.png)

Leave the “Metric” configurations as default, scroll down and choose a static threshold type. Set conditions whenever estimated charges are “Greater/Equal” and the threshold value to 10 USD, then click “Next”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/fa10a7369106ca094af5ba854491d1ec43ffd435/Screenshot%202024-12-16%20171457.png)

Scroll down, click “Next”, then give the alarm a name and description.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/13c581d673e1ae0cf365681b3566e279376a7bea/Screenshot%202024-12-16%20171857.png)

Click “Next” again, scroll down, then click “Create alarm”.

![image alt](https://github.com/Tatenda-Prince/Creating-Billing-Budget-Alarms-On-AWS/blob/5b947de6b65f5a825bad9fdf2e6703ec3ed5bfde/Screenshot%202024-12-16%20172421.png)

Note — the SNS subscription is pending confirmation. You need to head to the recipients email inbox, open the email you received, then click on the link to confirm your subscription to the SNS topic.

# Success!
Your alarm should now be configured and ready to work!















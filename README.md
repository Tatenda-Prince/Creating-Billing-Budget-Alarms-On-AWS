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

![image alt]()

Give the Budget a name, enter the budget amount, then type in the email address of the recipients to be notified when the threshold is exceeded.

As seen below, the recipients would be notified when spending has reached 85% and also when it reaches 100% or the forecasted spend is expected to reach 100%.

Proceed by clicking “Create budget”.

![image alt]()






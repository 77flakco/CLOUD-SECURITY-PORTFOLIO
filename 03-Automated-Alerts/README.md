# 🔔 Automated Cloud Alerting System

### **Project Overview**
In this project, I architected and deployed a serverless notification system on AWS. The goal was to establish a communication pipeline that automatically alerts security and operations teams when specific infrastructure events occur.

By integrating **Amazon EventBridge** with **Amazon SNS (Simple Notification Service)**, I created a scalable monitoring solution that decouples detection from notification, ensuring rapid response times for cloud events.

### **Architecture**
* **Amazon SNS:** Managed the delivery of messages to subscribers (Email protocol).
* **Amazon EventBridge:** Acted as the event bus to route system signals to the SNS topic.
* **Subscription Protocol:** Configured secure email endpoints for immediate alerting.

### **Key Achievements**
* ✅ **SNS Topic Configuration:** Created a standard SNS topic (`Tripwire-Alerts`) to serve as the central communication channel.
* ✅ **Endpoint Subscription:** Successfully subscribed and confirmed an external email address to the topic, overcoming anti-spam confirmation filters.
* ✅ **Event Routing:** Configured EventBridge rules to target the SNS topic, establishing a "Push" notification mechanism.
* ✅ **Pipeline Validation:** Verified the end-to-end flow of data by triggering test events and confirming delivery to the inbox.

### **Project Evidence**
*Below is the automated notification received from the AWS SNS pipeline, confirming the integration between the Event Bus and the Notification Service.*

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4de430d1-b5c0-40c8-b6d9-28c76439be24" />


### **Skills Demonstrated**
* **Cloud Operations:** Setting up monitoring and observability pipelines.
* **AWS Messaging:** Understanding Pub/Sub (Publisher/Subscriber) models with SNS.
* **Troubleshooting:** diagnosing subscription confirmation issues and validating event delivery.

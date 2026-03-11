# Automated-Incident-Response-System-using-CloudWatch-Alarms-and-Lambda-Remediation-

# Project Overview
This project implements an Automated Incident Response System in AWS that: Monitors EC2 CPU utilization Detects threshold breach Automatically triggers remediation Logs actions in CloudWatch The system prevents downtime by automatically rebooting an EC2 instance when CPU utilization crosses a defined threshold.

# Architecture Components Used
Amazon EC2 Amazon CloudWatch AWS Lambda

# Incident Flow
EC2 CPU usage increases CloudWatch Alarm detects threshold breach Alarm triggers Lambda Lambda reboots EC2 instance Action is logged in CloudWatch Logs

# Implementation Steps
1️⃣ Monitoring Setup – CloudWatch Alarm Configuration: Metric: CPUUtilization Threshold: Greater than 70% Period: 1 minute Evaluation Period: 1

<img width="1920" height="1020" alt="Screenshot 2026-03-08 203007" src="https://github.com/user-attachments/assets/bae096be-13f9-44c1-a720-72a7b2e83559" />

<img width="1920" height="1020" alt="Screenshot 2026-03-08 203032" src="https://github.com/user-attachments/assets/18e9644b-50c5-4ab7-8eb7-b4df7e18e7ec" />

# Lambda action
<img width="1920" height="1020" alt="Screenshot 2026-03-08 203032" src="https://github.com/user-attachments/assets/b4c969c3-0a96-4ea1-8499-1d725925399a" />

# 2️⃣ Lambda Remediation Function
Lambda function created to reboot EC2 instance automatically.
<img width="1920" height="986" alt="Select metric _ Alarms _ CloudWatch _ ap-southeast-2 - Google Chrome 11-03-2026 22_43_27" src="https://github.com/user-attachments/assets/5a1cf5e2-c2b7-48f4-9a85-90690213382f" />

# 3️⃣ Alarm → Lambda Trigger Configuration
CloudWatch Alarm configured to: State: In Alarm Action: Invoke Lambda Function

<img width="1272" height="527" alt="aws-automated-incident-response_README md at master · megha1002240_aws-automated-incident-response - Google Chrome 10-03-2026 22_09_28" src="https://github.com/user-attachments/assets/5cd997a8-526a-4b44-a852-273bced9aa74" />

# 4️⃣ Testing Procedure
To simulate high CPU usage: Installed stress tool on EC2 Generated artificial load CPU crossed 70%
<img width="1128" height="232" alt="aws-automated-incident-response_README md at master · megha1002240_aws-automated-incident-response - Google Chrome 10-03-2026 22_39_40" src="https://github.com/user-attachments/assets/088c7fb6-7a8c-4da2-8c20-f25308309108" />

# Alarm state changed to:
🔴 In Alarm
<img width="1263" height="533" alt="Select metric _ Alarms _ CloudWatch _ ap-southeast-2 - Google Chrome 11-03-2026 23_23_45" src="https://github.com/user-attachments/assets/1f5d700e-e4ad-49ca-9f37-36cdafbabecb" />
<img width="1265" height="542" alt="Select metric _ Alarms _ CloudWatch _ ap-southeast-2 - Google Chrome 11-03-2026 23_28_15" src="https://github.com/user-attachments/assets/42f326f7-2b73-42a5-9186-3d4945488aaf" />

# 5️⃣ Logging & Validation
Lambda execution logs stored in: CloudWatch → Log Groups → /aws/lambda/FunctionName Logs show: START Instance reboot initiated successfully END REPORT

<img width="1264" height="535" alt="aws-automated-incident-response_README md at master · megha1002240_aws-automated-incident-response - Google Chrome 10-03-2026 22_54_28" src="https://github.com/user-attachments/assets/4e48c7e8-afdf-441c-aaa4-9d60f8d4f6c5" />

<img width="1253" height="524" alt="aws-automated-incident-response_README md at master · megha1002240_aws-automated-incident-response - Google Chrome 10-03-2026 22_54_58" src="https://github.com/user-attachments/assets/09b954a0-04a5-4a6d-a566-f7ec10cadf21" />

<img width="1261" height="533" alt="Select metric _ Alarms _ CloudWatch _ ap-southeast-2 - Google Chrome 11-03-2026 23_40_26" src="https://github.com/user-attachments/assets/a2b27f5e-8e34-4ab0-9db9-fd3390e51cbf" />

<img width="1261" height="533" alt="Select metric _ Alarms _ CloudWatch _ ap-southeast-2 - Google Chrome 11-03-2026 23_40_26" src="https://github.com/user-attachments/assets/16aeba90-7872-42bf-8cfc-5c70a1359264" />

# Results
✔ CPU threshold breach detected ✔ Lambda triggered automatically ✔ EC2 reboot initiated ✔ Logs captured successfully ✔ No manual intervention required

# Key Benefits
Zero manual monitoring Faster incident resolution Reduced downtime Automated remediation Production-ready monitoring setup

# Conclusion
This project successfully demonstrates an automated incident response system using AWS services. The system ensures infrastructure reliability by automatically taking corrective action during high CPU usage events.




# ArchiCloudRNN
Possible cloud architecture for INGE3 project 

The purpose of this repo is to present a cloud architecture solution to our final year project at ESME Sudria. 

The project's name is : 'Robustness of neural networks against adversarial attacks' applied to the medical domain.

## Participants :
Louis Gidrol (Whaoo)

Florentin Flament (Florflam)

Méline Libert (melinelbt)

## Context

The project consists in training a neural network model to which different targeted and non-targeted attacks are applied and finding 'defending techniques" strengthening the model after each attack result and test its robustness. 

The model is trained on scan images of human brains, both healthy and with Alzheimer's disease.

## Project architecture 

<p align="center">
  <img width="800" height="475" src="https://github.com/Whaoo/ArchiCloudRNN/blob/main/images/Pr%C3%A9sentation2.jpg?raw=true">
</p>

## Technical Stack used

<p align="center">
  <img width="100" height="70" src="https://github.com/Whaoo/ArchiCloudRNN/blob/main/images/EC2_amazon.png?raw=true">
</p>
EC2 : Amazon EC2 is a cloud computing service that allows users to launch and scale virtual servers as needed. It offers various instance types and the ability to customize the operating system and software packages installed on the virtual servers. EC2 is pay-as-you-go, with users only paying for the resources they use while the virtual servers are running.

<p align="center">
  <img width="100" height="70" src="https://github.com/Whaoo/ArchiCloudRNN/blob/main/images/S3_amazon.png?raw=true">
</p>
S3 : Amazon S3 is a cloud storage service that offers scalable, high-durability storage for data. It is designed to store and retrieve any amount of data from anywhere on the web, and is commonly used by businesses of all sizes. S3 is pay-as-you-go, with no upfront fees or long-term commitments, and offers a range of storage classes for different data storage scenarios.

<p align="center">
  <img width="100" height="70" src="https://github.com/Whaoo/ArchiCloudRNN/blob/main/images/lambda.png?raw=true">
</p>
Lambda : Amazon Lambda is a serverless computing service that allows you to run code in response to events and automatically manages the underlying compute resources. It is pay-as-you-go, with no upfront costs or long-term commitments, and enables you to build and run event-driven applications and services without the need to worry about infrastructure.
It'as a FaaS : Function as a Service (FaaS) is a cloud computing model in which a provider allows users to run their own code in the cloud without worrying about infrastructure or maintenance. FaaS is cost-effective and convenient, abstracting away the underlying infrastructure and handling all deployment tasks. It is particularly useful for applications with variable or bursty workloads.

<p align="center">
  <img width="100" height="70" src="https://github.com/Whaoo/ArchiCloudRNN/blob/main/images/amazon_sns.png?raw=true">
</p>
SNS : Amazon SNS is a fully managed messaging service that allows you to send messages to multiple subscribers or other applications. It is pay-as-you-go and can be used to send notifications, alerts, and other types of messages to email, SMS, and other channels.

<p align="center">
  <img width="100" height="100" src="https://github.com/Whaoo/ArchiCloudRNN/blob/main/images/amazon-sqs_512.png?raw=true">
</p>
SQS : Amazon SQS is a fully managed message queuing service that allows you to decouple and scale microservices and applications. It offers standard and FIFO queues and is pay-as-you-go with no upfront costs or long-term commitments. SQS is reliable and scalable, making it easy to build and run highly available, fault-tolerant applications.

<p align="center">
  <img width="100" height="70" src="https://github.com/Whaoo/ArchiCloudRNN/blob/main/images/amazon_cloudwatch.png?raw=true">
</p>
CloudWatch : 
Amazon CloudWatch is a monitoring service for AWS resources and applications that provides data and operational insights, allows you to set alarms, and enables you to visualize, search, and analyze logs. It is pay-as-you-go with no upfront costs or long-term commitments.

## Why we choosed going with AWS :

## Architecture Worflow :


Src: https://aws.amazon.com/fr/pricing/

## Closer look at the lambda(s) : 

<p align="center">
  <img width="800" height="475" src="https://github.com/Whaoo/ArchiCloudRNN/blob/main/images/Pr%C3%A9sentation2_2.jpg?raw=true">
</p>

Each lambda is executing python3 code. 

## Other solutions :

We could also have choosen to use a VPS from a cloud provider like OVH, deployed an ubuntu server edition on it, launched a FastAPI/Flask server, that executed the python scripts and display the result on the webpage. But that would cost more than 10$, where the initial option will be way less, as it is a pay as you go, and we won't be using it that much. 


The project is located in a .ipynb file, and could be sufficient for personal, one-off use on a simple jupyter notebook localhost server. 

However, the subject of the Cloud Architecture rendering is to propose a cloud architecture solution for this solution.

The solution consists to use ServerLess Solutions from Amazon in addition to EC2. 

We don't want to have to manage a physical server, and the complexity of maintening it, and we want to be able to have a neer to 99% efficiency and availabilty, moreover, we want to be able to scale and clone easly the solution. 

So we choosed to go forward with AWS solution, as it's one cloud provider that meets our requirements, has a good integration between services, and has prices in range of the market.
AWS Lambda : First 6 Billion GB-seconds / month, $0.0000166667 for every GB-second.
SQS : Less than 1 Million entry is free
SNS : Publication API requests and batch publication requests are charged at USD 0.33 per million requests and USD 0.0187 per GB of payload data.
S3 : 5Go free per month, then 0,023$ per Gb
EC2 : One free per month.

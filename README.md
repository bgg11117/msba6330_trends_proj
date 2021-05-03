# Combatting Dashboard Fatigue: Voice-Powered Queries in AWS

## Introduction

Current business intelligence approaches face some issues. First, there’s a general over-reliance on dashboard-centric approaches to business intelligence. Dashboards can be great, but they may not be the best solution for every scenario. Secondly, with dashboards can come a steep learning curve. Technical and non-technical users alike have to learn how to physically log in to a dashboard, then figure out how to navigate the variety of controls, views, and other functions employed in the dashboard. This takes time and can leave users frustrated after struggling through the process, especially if the people building the dashboard design it how they like, not how the people who actually use the dashboard would like it. Lastly, dashboards can give a sense of information overload. There can be so many dashboards, and each dashboard can display a ton of information, leaving your specific KPI tough to find. This is amplified when the KPIs you’re interested in are spread across multiple dashboards. More logging in, more searching, more time consuming. All three of these issues combine to induce dashboard fatigue in business intelligence end-users. 

Voice-powered queries can streamline access to information, and can address areas where dashboard-centric approaches are lacking. Instead of companies solely relying on dashboards for their business intelligence needs, companies are afforded the flexibility of information on-the-spot, when quick answers are needed. For end users, there is far less of a learning curve since they can simply ask questions for the information they’re interested in. They also get back only the information they asked for, so there’s no need to sift through a bunch of visualizations or other KPIs that are irrelevant to the current situation. All this contributes to saving time and brain power, since answers are quick and to the point.

## Solution

In our solution, we will leverage S3, Athena, Lambda function, DynamoDB and Cloudwatch in the backend, and a voice-based user interface through a custom Alexa skill on the front end.

**Run our code with the following link**
- [infrastructure_setup](https://github.com/bgg11117/msba6330_trends_proj/blob/main/infrastructure_setup.md)

![pipeline chart](https://github.com/bgg11117/msba6330_trends_proj/blob/main/pipeline_chart.png)

## Business cases

![business application](https://github.com/bgg11117/msba6330_trends_proj/blob/main/business_application.png)


- [Handout](https://github.com/bgg11117/msba6330_trends_proj/blob/main/BDA_Handout.pdf)
- [Presentation Slide](https://github.com/bgg11117/msba6330_trends_proj/blob/main/BDA_Presentation.pdf)
- [Presentation Video](https://www.youtube.com/watch?v=qRmGPqDZKy8)

Ref from [voice-powered-analytics](https://github.com/awslabs/voice-powered-analytics)

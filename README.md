# AffectiveAI

This project is designed to model a concept wherein user video is analyzed for facial recognition, specifically for emotional analysis, the results of which will be streamed to a chat bot for testing of different response models. The goal is to apply increased emotional intelligence that would normally occur in face-to-face service situations to an automated AI context. 

As a starting point, I am implementing some features of the AWS Rekognition-based application described and provided here: https://github.com/brain-power/Brain-Power-Amazon-Fidgetology

This configuration will accept video uploaded to AWS S3, analyze frames for various emotional facial expressions, and output the resulting data to Kinesis. From there, a Botpress (https://botpress.io/) chat bot runs in a browser context, calls a Lambda function via API Gateway to query the emotion data, calls another Lambda to retrieve an A/B test assignment (via Sixpack http://sixpack.seatgeek.com/) and corresponding model. The chat bot then customizes its responses based on the assigned emotional model. The goal is to model a more empathetic response such that an effective service representative would provide.

## Brain-Power-Amazon-Fidgetology

For more background on the Fidgetology project and its implementation in AWS, see https://aws.amazon.com/blogs/machine-learning/building-automatic-analysis-of-body-language-to-gauge-attention-and-engagement-using-amazon-kinesis-video-streams-and-amazon-ai-services/.

## Overview

This is a serverless web application for streaming webcam feed from a browser to [Amazon Kinesis Video Streams](https://console.aws.amazon.com/kinesisvideo) and [Amazon Rekognition Video](https://docs.aws.amazon.com/rekognition/latest/dg/streaming-video.html). Body motion metrics can be then be visualized in web app with minimal delay.

AWS Technologies used:
* Kinesis Video Streams
* Rekognition Video
* Kinesis Data Streams
* API Gateway
* Lambda
* S3
* CloudFormation

## Components

<kbd>
 <img src="attachments/Brain_Power_fidgetology_02__SystemArchitectureDiagram_trans.png?raw=true">
</kbd>
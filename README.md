# Streamdata.io Stack Exchange Questions Streaming to AWS S3 Data Lake (Serverless)
<img src="https://s3.amazonaws.com/kinlane-productions/streamdata/streamdata-vertical.png" align="right" width="150" />This is a demo of delivering a stream of Stack Exchange questions using Streamdata.io running on AWS Lambda as a "serverless" function. It is designed to take this existing JSON API and turn it into a streaming API using Server-Sent Events (SSE), applying incremental updates using JSON Patch, and then stream the results into a data lake store on Amazon S3.

You will need a Streamdata.io account and application key to run this function, as well as an AWS account to run the Lambda function in, and AWS S3 to store the data. You can run this as stream for up to five minutes (the maximum timeout of a Lambda script), then rerun every X minutes, or other schedule using AWS CloudWatch Events. Providing an existing API stream that can be turned on or off as needed, delivering real time updates to your Amazon S3 data lake.

## Key Links:
- [Streamdata.io Service](http://streamdata.io)
- [Streamdata.io Account Signup](https://portal.streamdata.io/)
- [Stack Exchange API](https://api.stackexchange.com/docs)
- [Example API Call](https://api.stackexchange.com/2.2/questions?order=desc&sort=activity&site=stackoverflow&tagged=kafka)
- [AWS Serverless Application Repository](https://serverlessrepo.aws.amazon.com/applications/arn:aws:serverlessrepo:us-east-1:879370021840:applications~StreamData-IO-Stack-Exchange-Questions)
- [License: MIT License](https://github.com/streamdata-serverless/streamdata-io-basic-demo-stockmarket-prices/blob/master/LICENSE)

## Frequently Asked Questions:

- Where do I put my Streamdata.io key? In the appToken environment variable available in the settings for your function after you have installed in.
- Where does the data end up in Amazon S3? There are two environment variables for the function: 1) s3bucket, and 2) targetFolder, which will define your "data lake" destination on Amazon S3 -- you will need to create the bucket, but the folder will automatically be created.
- Where do I get support for this function? Submit your issues via [the Github repository for this project](https://github.com/streamdata-serverless/streamdata-io-basic-demo-stockmarket-prices/issues)
- Is access_token and key required? No, but if you want to have higher rate limits, you will need.
- How do I get a Stack Exchange key? You will have to [register an application yourself using Stack Exchange](https://stackapps.com/apps/oauth/register).
- How do I get a Stack Exchange access_token? You will need to setup an application, and perform the OAuth dance for your application. We could generate one for you, but then we'd have access to your token.

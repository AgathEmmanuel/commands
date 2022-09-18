


------------free tier  		      https://aws.amazon.com/pricing/
------------aws pricing calulator     https://calculator.aws/#/


https://aws.amazon.com/lambda/pricing/

AWS Lambda free usage tier includes 1M free requests per month and 400,000 GB-seconds of compute time per month.
Lambda counts a request each time it starts executing in response to an event notification or invoke call, including test invokes from the console.

Duration is calculated from the time your code begins executing until it returns or otherwise terminates, rounded up to the nearest 1ms*. The price depends on the amount of memory you allocate to your function. In the AWS Lambda resource model, you choose the amount of memory you want for your function, and are allocated proportional CPU power and other resources. An increase in memory size triggers an equivalent increase in CPU available to your function. To learn more, see the Function Configuration documentation.
https://docs.aws.amazon.com/lambda/latest/dg/resource-model.html


https://aws.amazon.com/ec2/pricing/
Amazon EC2 is free to try. There are five ways to pay for Amazon EC2 instances: 
On-Demand, 
Savings Plans, 
Reserved Instances, and 
Spot Instances. 
You can also pay for Dedicated Hosts which provide you with EC2 instance capacity on physical servers dedicated for your use. For more information on how to optimize your Amazon EC2 spend, visit the Amazon EC2 Cost and Capacity page.

AWS Free Tier includes 750 hours of Linux and Windows t2.micro instances, ( t3.micro for the regions in which t2.micro is unavailable) each month for one year. To stay within the Free Tier, use only EC2 Micro instances.


https://aws.amazon.com/s3/pricing/
Pay only for what you use. There is no minimum fee. There are four cost components to consider when deciding on which S3 storage class best fits your data profile – storage pricing, request and data retrieval pricing, data transfer and transfer acceleration pricing, and data management features pricing.

As part of the AWS Free Tier, you can get started with Amazon S3 for free. Upon sign-up, new AWS customers receive 5GB of Amazon S3 storage in the S3 Standard storage class; 20,000 GET Requests; 2,000 PUT, COPY, POST, or LIST Requests; and 15GB of Data Transfer Out each month for one year.
Your usage for the free tier is calculated each month across all AWS Regions except the AWS GovCloud Region and automatically applied to your bill; unused monthly usage will not roll over. Restrictions apply; see offer terms for more details.

-----------aws resource termination

https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/HowToDeleteDistribution.html

https://theburningmonk.com/2019/06/aws-lambda-how-to-detect-and-stop-accidental-infinite-recursions/

https://aws.amazon.com/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/module-5/

1. Delete your app
2. Delete your Amazon Cognito user pool
3. Delete your serverless backend
	Lambda Function
	IAM Role
	DynamoDB Table
4. Delete your REST API
5. Delete your Cloudwatch log

------------aws cli config file
https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html#cli-config-cli_auto_prompt


------------creating iam roles for multiple users access from cli

NOTE: always make the access keys of users inactive before you
      log out from the aws console

https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html
> IAM
> Users
> Add user
	user name: agathMint
 	user name: agathWindows
	access type: programmatic acess
> set permissions
	select Add user to a group
	create group
		group name: admins
		filter policy: admi
		Tick AdministratorAccess
		click Create group
	Tick admins group
	create user



---------------regional plans
https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-region.html

Being that US East 1 (North Virginia) Region was one of the first Regions that was up and running, it is pretty much the cheapest Region in AWS. In fact, the cloud giant refers to it as US Standard. In general, it also has the most services available on the platform, as Amazon usually prefers initial rollout here.


https://forums.aws.amazon.com/thread.jspa?threadID=281273
I can think of Resource Group. Under the Resource Group select "Tag Editor" and Select all the regions and All the resource. This would show consolidate list of all the resources running across all the regions.

If you signed up for an AWS account on or after May 17, 2017, the default
region when you access a resource from the AWS Management Console is US East
(Ohio) (us-east-2); for older accounts, the default region is either US West
(Oregon) (us-west-2) or US East (N. Virginia) (us-east-1). For more
information, see :

---------------regions and endpoints. 
https://docs.aws.amazon.com/general/latest/gr/rande.html

For the list of regions and endpoints supported by Amazon EMR, see Regions and Endpoints in the Amazon Web Services General Reference. 

Some AWS features are available only in limited regions. For example, Cluster Compute instances are available only in the US East (N. Virginia) region, and the Asia Pacific (Sydney) region supports only Hadoop 1.0.3 and later.


---------------autocomplete_aws_cli
https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-parameters-prompting.html

F3		#documentation for the current command

Command completion
Parameter completion
Resource completion
Shorthand completion
File completion
Region completion
Profile completion
Fuzzy searching
History		#To view and run previously used commands in auto-prompt mode,press CTRL+R

https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html#cli-config-cli_auto_prompt
Auto-prompt modes
	Full-mode		cli_auto_prompt = on
	Partial-mode		cli_auto_prompt = on-partial



---------------configure auto-prompt
To configure auto-prompt you can use the following methods in order of precedence:
    >Command line options enable or disable auto-prompt for a single command. Use 
--cli-auto-prompt  		to call auto-prompt and 
--no-cli-auto-prompt 		to disable auto-prompt.
    >Environment variables use the aws_cli_auto_prompt variable.
    >Shared config files use the cli_auto_prompt setting.

---------------pattern matching
https://vim.fandom.com/wiki/Search_patterns
https://regexr.com/



aws ec2 describe-key-pairs		#shows all the key pairs
aws ec2 describe-key-pairs --key-name MyKeyPair

--------------access key id
aws iam list-access-keys
aws iam update-access-key --access-key-id AKIAIOSFODNN7EXAMPLE --status Inactive --user-name Bob

---------------speed up the aws cli

https://dzone.com/articles/how-i-made-aws-cli-300-faster-full-disclosure


---------------aws global infrasturcture

https://aws.amazon.com/about-aws/global-infrastructure/

Determining lowest latency AWS location for custom usage
https://stackoverflow.com/questions/6339990/how-could-i-determine-which-aws-location-is-best-for-serving-customers-from-a-pa



-------------------- serverless

https://aws.amazon.com/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/module-5/

https://blog.lawrencemcdaniel.com/serve-a-django-app-from-an-aws-lambda-function/
https://github.com/bodycalc/bodycalc.io

https://thenewstack.io/what-aws-lambdas-performance-stats-reveal/

https://cloudacademy.com/blog/zappa-or-how-to-go-serverless-with-django/

https://www.serverless.com/dynamodb

Here are a few serverless solutions we’ve written about recently that use DynamoDB as their primary datastore:

    Event-driven Serverless processing system with DynamoDB Streams
    A Serverless Python REST API with Flask and DynamoDB
    A Serverless GraphQL API with DynamoDB
    A Serverless chat application with AWS AppSync and DynamoDB

If you want to speed up delivery of your web content, you can use Amazon CloudFront, the AWS content delivery network (CDN). ... If you want to use your own domain name, use Amazon Route 53 to create an alias record that points to your CloudFront distribution


------------------- which language for backend

https://www.quora.com/Which-is-good-for-backend-machine-learning-Django-or-Node-js

https://www.quora.com/Is-it-possible-Python-with-Machine-Learning-Library-in-Node-JS-Web-Application

https://www.quora.com/How-do-I-combine-my-Node-js-app-to-a-machine-learning-algorithm-written-in-a-different-language

https://www.quora.com/Should-I-learn-Java-Spring-Hibernate-or-JS-Node-Express

My advices is that if your looking to do “new” development in more of a startup type of environment - go the Node/JS route. If your looking to go to a (probably) more stable company and do more maintenance and tweaks to an existing system - go with Java/Spring as more “established” companies are more likely to stay with their existing stack - such as a PhP/Java or .Net stack than ‘experiment’ with newer tech. (again, generalizing a bit, cause some startups use Java and some older/establish companies are jumping on the node route).

We use Java EE, because we create huge government financial system, with a lot of integrations with other government systems. There are about 80k Java and .xhtml files, which divided into 16 Maven projects. This is Enterprise. And I can’t imagine, how to handle the project like this in pure Javascript (MEAN stack).


"One of the (hundreds of) cool things about working for Google is that they let teams experiment, as long as it's done within certain broad and well-defined boundaries. One of the fences in this big playground is your choice of programming language. You have to play inside the fence defined by C++, Java, Python, and JavaScript."
"The thing is, Google's decision to limit the number of languages allowed for production work is actually pretty smart.


Node js and JS is better if you want easy cross platform integration and want to deal more in real time data and relatively less complex schema(architecture and modelling). JS is blazing fast especially when combined with nosql DB and express framework with a reverse proxy for protection

JS doesn't fare well with massive data queries and really isn't the option if you want to get into machine learning & AI which deal with tons and tons of data just to begin with. Also if you want to get into IOT, JS lacks behind and doesn't have native code to interact with devices, generally wrappers and/or cpp bindings which is actually quite a tedious task setting up.

Python and Django is a very versatile combo. Django comes pre loaded with a lot of features out of the box and is in itself easy to setup and get going towards a production ready framework. Python is a powerful language with extensive support and a massive online community. Python and Django are perfect for sql based DB, thus good for dealing with gigantic datasets and massive querries, which comes in handy qhen your getting into AI. Also python with the help of opencv comes bundled with native hardware controls for easy to implement functions and usages.

So you need to decide on what you are getting into before selecting your language set. See what you want to be doing ahead and how you want to get out the features you have in mind or the industry you want to pursue. Rest is up to you and your imagination. Regardless of what you choose, you will have to learn a lot and will get extensive support from our ever growing online community! Best of luck



-------------------lambda function

https://stackify.com/aws-lambda-with-python-a-complete-getting-started-guide/

-------------------



2021-02-23-ag-website



exports.handler = async (event) => {
    // TODO implement
    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello from Lambda!'),
    };
    return response;
};


 https://9p05mhxid7.execute-api.us-east-1.amazonaws.com/test


You are about to give API Gateway permission to invoke your Lambda function:
arn:aws:lambda:us-east-1:xxxxxxxxxxx:function:get_weather




Resource-based policy

{
  "Version": "2012-10-17",
  "Id": "default",
  "Statement": [
    {
      "Sid": "adfaefa-asf-4bdfadff7-931341320-faf48c656b07e5",
      "Effect": "Allow",
      "Principal": {
        "Service": "apigateway.amazonaws.com"
      },
      "Action": "lambda:InvokeFunction",
      "Resource": "arn:aws:lambda:us-east-1:xxxxxxxxxxx:function:get_weather",
      "Condition": {
        "ArnLike": {
          "AWS:SourceArn": "arn:aws:execute-api:us-east-1:xxxxxxxxxxx:afadfwefdsf/*/POST/"
        }
      }
    }
  ]
}





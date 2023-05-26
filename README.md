# TDFTechnicalChallenge
# Created by Nishant Tripathi
Repostiory contains file needed to complete TDF Technical Challenge

To run the data pipeline/challenge, just upload the file into cloudformation and create the stack. Necessary roles, permissions, lambda function and s3 bucket required, will be created from the same .yaml file. 

Assumptions that were considered while completing the challenge:
    1. Name of the bucket remains unique, as in no one else has the same name for their bucket. 
    2. Person/account evaluating the data pipe does have access to IAM service from aws. 
    3. The task was to only perform ingestion of data into s3 bucket and not verify/format it into any particular format. 
    4. Lambda function does give a DeprecationWarning due to 'botocore.vendored.requests' library. To use request library, a lambda layer needs to be created and attaching it to lambda function will lead to complexities that were beyond the scope of the challenge. 
    5. Older python version is used for accessing 'botocore.vendored.requests' library.
    6. Data in s3 is overwritten, by the lambda function on each execution.
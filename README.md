### DEMO
[Automation Test Report](http://automation-test-report.s3-website-us-east-1.amazonaws.com/#)

## Set up AWS
1. IAM role
2. AWS CLI

## Postman
1. Write test script
2. Export to json file
    > collect.json

    > environment.json

## AWS Repository
1. Creating a git repository with AWS CodeCommit
    - AWS Console > Developer Tools > CodeCommit > Create Repository
2. Creating a Buildspec file
3. Creating an AWS CodeBuild project
    - AWS Console > Developer Tools > CodeBuild
    - Source Provider: CodeCommit) and Repository
4. Bringing it together with AWS CodePipeline
    - AWS Console > Developer Tools > CodePipeline > Set Source provider
    - source stage: CodeCommit
    - build stage: CodeBuild
    - deploy stage: Skip
5. Create AWS CodeBuild triggers
    - CodeBuild -> Build daily triggers: `Cron expression 0 1 ? * * *`

## S3
- Run source of test script
    > Update collect.json and environment.json into S3/Bucket/postman/
- Set up the static website
    1. Properties > Static website hosting
        > index.html
    2. Permissions > Block public access > Set off
    3. Permissions > Bucket policy
        > policy.json
    4. Permissions > Cross-origin resource sharing
        > cors.json
- Auto save report after codepipe end
    > S3/Bucket/postman/postman-report/


